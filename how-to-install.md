# To install AOSC OS...

Here is a simple yet complete guide on installation of AOSC OS.

### Baytrail device users

You may want to read [Notes for Baytrail](https://github.com/AOSC-Dev/aosc-os/blob/master/notes-for-baytrail.md) after you have finished installing according to this guide for issue workarounds and tips.

### On an array

If you plan on installing AOSC OS on a MD-based RAID array (in other words, software RAID), please read the variant of guide - [Notes for MD-RAID Arrays](https://github.com/AOSC-Dev/aosc-os/blob/master/notes-for-md-raid.md) - designed for these set-ups.

## Tarballs

A tarball is the basic and main way we ship AOSC OS as, a "tarball" literally means a system all packed in a `tar.xz` archive. It is probably the fastest way to "physically" install a copy of AOSC OS on your device.

Get your tarballs from https://www.anthonos.org (currently a temporary portal for downloads, pick the one that suites).

### First things first

Be prepared for installation from tarballs.

- Download the tarball, and checksum the file to make sure everything's in order.
- Make yourself `root`.
- Make a sufficiently sized partition (refer to system requirement in download page), and format it to `ext4` or which ever file system you prefer.
- Mount the partition somewhere (represented as `$MOUNT` in the guide).

### Un-tar!

The shell code below shows how it is been done.

```bash
cd ${MOUNT}
tar pxfJ /path/to/tarball.tar.xz
# add "v" to paramenter for a much more exciting experience.
```

### Post-installation configuration

Some basic post-installation configuration needed for the un-tar-ed system to run.

#### GRUB

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

Note: if the system did not ship with an initrd, GRUB will not support UUID in configuration; if you would like to
use the UUID feature, you would need to generate one yourself with `dracut`.

With package `dracut`'s trigger system, it is possible to generate initramfs in chroot.

```bash
. /var/ab/triggered/dracut
```

Install GRUB.

```bash
# MBR system. /dev/sda here represents the MBR location, change as needed.
grub-install --target=i386-pc /dev/sda

# EFI x64 install.
grub-install --target=x86_64-efi --bootloader-id=AOSC-GRUB --efi-directory=/efi

# EFI x32 install, needed for some old Bay Trail tablets/devices.
grub-install --target=i386-efi --bootloader-id=AOSC-GRUB --efi-directory=/efi
```

And finally configure GRUB.

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

#### Multiple partition scenario

If you have chosen to split `/home` or whatever to another partition, remember to write a valid `/etc/fstab` file.

#### Passwords

The default "normal" user `aosc` has `anthon` as password.

And `root` has the same.

## Docker

// TODO

## BuildKit

BuildKit's installation (deployment) is strikingly similar to tarballs, the only difference is that you won't need a dedicated partition, or even bother configuring a boot loader.

For more details on deploying BuildKit, see [here](https://github.com/AOSC-Dev/aosc-os-abbs/wiki/Preparing-What-is-BuildKit).
