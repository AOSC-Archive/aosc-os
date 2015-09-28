Give up while you can
=====================
The current state of Linux support on some of the Baytrail devices is to an extent, broken 
(nor it has never been in a satisfactory state). Extra steps needs to be taken after 
installing AOSC OS according to the 
[official guide](https://github.com/AOSC-Dev/aosc-os/blob/master/how-to-install.md).

The steps are not for the faint of heart, so prepare yourself for the procedures.

##Non-64 bit EFI
AOSC OS ships with a complete suite of `grub` that includes `i386-efi` platform support, this
is needed on most of the Baytrail-M devices. Check, or do your research to make sure.

If you are sure that your device ships with 32-bit EFI, install GRUB with the following.

```bash
# EFI system, mount ESP partition. $ESP represents a device name with full path.
mount $ESP ${MOUNT}/efi

# Chroot into the AOSC OS system root.
chroot ${MOUNT} /bin/bash

# EFI x32 install, needed for some old Bay Trail tablets/devices.
grub-install --target=i386-efi --bootloader-id=AOSC-GRUB --efi-directory=/efi
```

And finally configure GRUB.

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

##Initrd generation
It is required for devices using Realtek-based eMMC/SDIO controllers to generate an `initrd`
(an initialization RAM disk) for AOSC OS to detect the SD card/eMMC controller during the
boot. Without an `initrd` AOSC OS will fail to boot with such controllers. If you are sure
that you are not using a Realtek-based controller, you may skip this process as the Linux
kernel configuration has the support built in.

```bash
# find our the shipped kernel version
ls /usr/lib/module
# and "dracut" the initrd, with the kernel version you found, replace ${kernver} with the one you found
dracut ${kernver}
```

Workarounds and quirks
======================
Certain device specific operations may be required for a proper experience, too.

##1. System locks up after starting to boot with GRUB
On certain Baytrail-based devices it is possible that the device will freeze after starting
to boot the kernel, showing "loading initrd...". A workaround that is tested to work is to
go to the "boot manager" or "boot device menu" first when you powered on your device, then
select "AOSC-GRUB" from there.

##2. KMS doesn't work on Dell Venue 8 Pro
On a Dell Venue 8 Pro, it is possible that the KMS (kernel mode settings) will result in a
blank screen during the start up process. While you can specify `nomodeset` in the kernel
parameter to work around this issue, with no KMS available, desktops like Plasma and GNOME
will have really bad performance, and the touch screen will not work as well.

A proper way to work around this issue is to edit the `/etc/default/grub` file, in the lines
saying:

```
# Uncomment to disable graphical terminal
#GRUB_TERMINAL_OUTPUT=console
```

Uncomment the second line shown above, and regenerate your GRUB configuration with:

```bash
grub-mkconfig -o /boot/grub/grub.cfg
```

Will fix the issue with blank screen with KMS enabled.

##3. Slow Mo-o-o-o-tion
Sounds funny, but not funny when you use your device with slow motion I assume? This issue is
very easy to fix, as this is a misbehavior in clocksource detection by the kernel. To work 
around this issue, edit the `/etc/default/grub` file, in the line saying:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet rw"
```

Change it into:

```
GRUB_CMDLINE_LINUX_DEFAULT="quiet rw clocksource=tsc hpet=off"
```
