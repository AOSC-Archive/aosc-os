Raspberry Pi 2/3
================

So yes, Raspberry Pi 2 and 3 shares the same installation process (in fact, they
even share the same distribution). So let's crack on, shall we?

Distribution formats
--------------------

Currently AOSC OS for Raspberry Pi only comes in the form of tarballs, we are
expecting SD card images to roll-in in relatively short order. This guide will
focus on the installation with tarballs.

You may get tarballs for Raspberry Pi (and soon images as well) on our
[Community Portal](https://aosc.io/).

Preparing the SD card
---------------------

Raspberry Pi only supports booting from a SD card with at least two partitions,
listed below:

- A VFAT (FAT32) partition for /boot;
- A Linux-capable partition for / (we recommend ext4);

Using `parted`, `cfdisk`, `gparted`, or anything available or to your preference
for partitioning is fine.

Now format the two partitions (assuming the device file to your SD card is
/dev/mmcblk0):

```
# mkfs.vfat -F 32 /dev/mmcblk0p1
# mkfs.ext4 /dev/mmcblk0p2
```

Mounting the partitions
-----------------------

Let's get started by mounting the SD card partitions in `/mnt`.

Mounting the root (`/`) partition.

```
# mount /dev/mmcblk0p2 /mnt
```

Then, create a mount point for the boot (`/boot`) partition, and mount the
partition there.

```
# mkdir /mnt/boot
# mount /dev/mmcblk0p1 /mnt/boot
```

Unpacking system tarball
------------------------

Now we are ready to deploy the tarball. Let's do that all at once.

```
# cd /mnt
# tar pxf /path/to/tarball/tarball.tar.xz
```

Just to make sure.

```
# sync
```

You may unmount the partitions now.

```
# umount /mnt/boot
# umount /mnt
```

Et voila, you are good to go.
