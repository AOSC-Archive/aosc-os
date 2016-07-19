# To install AOSC OS... on an array...

Here is a simple yet complete guide on installation of AOSC OS.

## Know what you are getting into...

You have a system with no hardware RAID support, or you do not plan on using such hardware support with your
installation special steps are necessary for the system to install, and boot properly.

## Drive setup

It is reasonably easy to setup a MD-based (`mdadm`) RAID array on any hard disk drives. Here's a list of what
you need to do/have.

- [ ] > 1 partitions ready (it is a good practice to have all your array members ready).
- [ ] `mdadm` utility ready to run in the installation environment.
- [ ] A cup of coffee for your mental state.
- [x] That's it.

### Partitioning

Although not a requirement, the walk-through guide here will be presented, assuming that you have two or more
hard disk drives available for array setup.

Create your partitions on the drives pending for an array, and use `fdisk` (MBR) or `gdisk` (GPT/GUID) to change
the member partitions' types.

- **0xDA** for MBR/msdos partition tables (non-FS data, as recommended by [kernel.org](https://kernel.org).
- **FD00** for GPT/GUID partition tables (Linux RAID Member).

Notes:

- **Partitions should not be formatted before the array is set up.**
- **Copy, or mimick the partition table from the first drive to the next if you are setting up a RAID-1 array.**

Now, time to set up the arrays.

- For a RAID-0 setup, `mdadm --create --level=0 --raid-devices=2 /dev/md0 /dev/sdXY /dev/sdXY`.
- For a RAID-1 setup, `mdadm --create --level=1 --raid-devices=2 /dev/md0 /dev/sdXY /dev/sdXY`.

And so on...

Get the idea? Create your arrays with commands, with `mdX` representing a conjunction (that is, a md-RAID array
device) and the series of partitions to be used for the array. For other parameters, please refer to `man mdadm`
for more details, the parameters listed above is really what you would need.

If you are using RAID-1 or any array that involves drive mirroring/syncing, the arrays will start to do so
immediately. However, operations to the array is possible during the process, with degraded performance, and
of course, degraded security.

### Formatting

Now, we can format the array with...

`mkfs.${FS} /dev/mdX`

Where `X` is a integer representative to the numbering of the arrays.

## Tarballs

A tarball is the basic and main way we ship AOSC OS as, a "tarball" literally means a system all packed in a 
`tar.xz` archive. It is probably the fastest way to "physically" install a copy of AOSC OS on your device.

Get your tarballs from https://aosc.io (currently a temporary portal for downloads, pick the one that suites).

**All tarballs are ready to install and boot on MD-RAID arrays.**

### First things first

Be prepared for installation from tarballs.

- Download the tarball, and checksum the file to make sure everything's in order.
- Make yourself `root`.
- Mount the array conjunction device somewhere (represented as `$MOUNT` in the guide).

### Un-tar!

The shell code below shows how it is been done.

```bash
cd ${MOUNT}
tar pxf /path/to/tarball.tar.xz
# add "v" to paramenter for a much more exciting experience.
```

### Post-installation configuration

Some basic post-installation configuration needed for the un-tar-ed system to run.

#### Initrd (mandatory), preparation

A initrd/initramfs is required for a system on an array to boot successfully, however, changes to 
`dracut` configuration is required for the generated initrd/initramfs to be usable in this scenario.

Using your preferred text editor, open `/etc/dracut` for changes, and add the following lines to the file.

```bash
# For MD-RAID support modules
add_dracutmodules+=" mdraid "
# Use generated mdadm.conf
mdadmconf="yes"
```

#### mdadm.conf

First of all, do all needed mounts.

```bash
cd ${MOUNT}

# Regular mounts, binding the virtual file systems.
for i in dev proc sys; do
  mount --bind /$i $i
done

# EFI system, mount ESP partition. $ESP represents a device name with full path.
mount $ESP ${MOUNT}/efi
```

Then, chroot into the system.

```bash
chroot ${MOUNT} /bin/bash
```

And finally, generate mdadm.conf with the following command.

```bash
mdadm --detail --scan >> /etc/mdadm.conf
```

#### Initrd (mandatory), generation

You are now ready to generate the initrd/initramfs for the system to boot.

With package `dracut`'s trigger system, it is possible to generate initramfs in chroot.

```bash
. /var/ab/triggered/dracut
```

#### GRUB

Install GRUB.

```bash
# MBR system. /dev/sda here represents the MBR location, change as needed.
# However, on sync-based arrays like RAID-1, you will need to install GRUB on all member disks.
grub-install --target=i386-pc /dev/sda
# grub-install --target=i386-pc /dev/sdb
# grub-install --target=i386-pc /dev/sdc
# grub-install --target=i386-pc /dev/sdd
# ...

# EFI x64 install.
grub-install --target=x86_64-efi --bootloader-id=AOSC-GRUB --efi-directory=/efi

# EFI x32 install, needed for some old Bay Trail tablets/devices.
grub-install --target=i386-efi --bootloader-id=AOSC-GRUB --efi-directory=/efi
```

Before you configure GRUB, kernel parameter is needed for the md-RAID array to be automatically assembled,
therefore making it possible for the system to boot through initrd/initramfs.

To configure kernel parameters, open `/etc/default/grub` with your preferred text editor.

On the line starting with `GRUB_CMDLINE_LINUX_DEFAULT`, add `rd.auto rd.auto=1` inside of the quotation marks,
and save the file on exit.

And finally configure GRUB.

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

#### Passwords

The default "normal" user `aosc` has `anthon` as password.

And `root` has the same.
