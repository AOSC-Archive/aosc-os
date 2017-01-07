# To install AOSC OS on KVM...

Here is a simple guide for installation of AOSC OS on Kernel-based Virtual Machine (aka KVM). 

## Tarballs

A tarball is the basic and main way we ship AOSC OS as, a "tarball" literally means a system all packed in a `tar.xz` archive. It is probably the fastest way to "physically" install a copy of AOSC OS on your device.

Get your tarballs from https://www.anthonos.org (currently a temporary portal for downloads, pick the one that suites).

### First things first

Be prepared for installation from tarballs.

- Download the tarball, and checksum the file to make sure everything's in order.
- Make yourself `root`.

### Prepare the VM harddisk image

Create an empty harddisk image called `aosc.img` with the size of `20GiB`.

```bash
qemu-img create -f raw aosc.img 20G
```

Partition the aosc.img file.

```
$ fdisk aosc.img

Welcome to fdisk (util-linux 2.28.2).
Changes will remain in memory only, until you decide to write them.
Be careful before using the write command.

Device does not contain a recognized partition table.
Created a new DOS disklabel with disk identifier 0xd683cfec.

Command (m for help): n
Partition type
   p   primary (0 primary, 0 extended, 4 free)
   e   extended (container for logical partitions)
Select (default p): p
Partition number (1-4, default 1): 1
First sector (2048-41943039, default 2048): 
Last sector, +sectors or +size{K,M,G,T,P} (2048-41943039, default 41943039): 

Created a new partition 1 of type 'Linux' and of size 20 GiB.

Command (m for help): w
The partition table has been altered.
Syncing disks.
```

Show the partition table. 

```
$ fdisk -l aosc.img
Disk aosc.img: 20 GiB, 21474836480 bytes, 41943040 sectors
Units: sectors of 1 * 512 = 512 bytes
Sector size (logical/physical): 512 bytes / 512 bytes
I/O size (minimum/optimal): 512 bytes / 512 bytes
Disklabel type: dos
Disk identifier: 0xd683cfec

Device     Boot Start      End  Sectors Size Id Type
aosc.img1        2048 41943039 41940992  20G 83 Linux
```

Create a loop device. In this example, /dev/loop0.

Offset is `start * sectorsize`. And sizelimit is `sectors * sectorsize`. So

```bash
losetup --offset $((2048*512)) --sizelimit $((512*41940992)) --show --find aosc.img /dev/loop0
```

Format it

```bash
mkfs.ext4 /dev/loop0
```

Mount the loop device. For example, under /mnt.

```bash
mount /dev/loop0 ${MOUNT}
```

### Un-tar!

The shell code below shows how it is been done.

```bash
cd ${MOUNT}
tar pxvf /path/to/tarball.tar.xz
# add "v" to paramenter for a much more exciting experience.
```

Now you can umount your image.

```bash
umount ${MOUNT}
losetup -d /dev/loop0
```

### Bootloader!

Here comes the most interesting part. Boot configuration is needed for the un-tar-ed system to run.

This part require you to have a working VM. To chroot on your physical system simply won't work as expected.

Before continue with following steps, create a VM with the prepared harddisk file, and boot the VM from a LiveCD. Now you need to work on the VM with the Live system.

#### GRUB

First of all, do all needed mounts.

```bash
cd ${MOUNT}

# Regular mounts, binding the virtual file systems.
for i in dev proc sys; do
  mount --bind /$i $i
done
```

Then, chroot into the system.

```bash
chroot ${MOUNT} /bin/bash
```

With package `dracut`'s trigger system, it is possible to generate initramfs in chroot.

```bash
. /var/ab/triggered/dracut
```

Install GRUB.

```bash
# MBR system. /dev/sda here represents the MBR location, change as needed.
grub-install --target=i386-pc /dev/sda

```

And finally configure GRUB.

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```
If you have chosen to split `/home` or whatever to another partition, remember to write a valid `/etc/fstab` file.

Now you are done. Remove the LiveCD and reboot to enjoy your AOSC OS virtual machine!

## Passwords

The default "normal" user `aosc` has `anthon` as password.

And `root` has the same.

## FAQ

Q: I am seeing annoying warnings like
```
[TTM] Buffer eviction failed
qxl 0000:00:02.0: object_init failed for (4026540032, 0x00000001)
[drm:qxl_alloc_bo_reserved [qxl]] *ERROR* failed to allocate VRAM BO
```
A: Please change your Video model of the VM from QXL to Virtio.
