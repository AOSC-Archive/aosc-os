The proprietary drama
=====================

Parallels Workstation is not community-based, nor is it open source in anyway.
There is a possibility that Parallels Workstation wouldn't be the perfect match
for AOSC OS - we always push the newest mainline kernels for AOSC OS.

Playing the game (Parallels Workstation 2016)
---------------------------------------------

For Parallels Workstation, it is to your best interest to choose the right
kernel version to match that of Parallels Workstation's.

For our first record, AOSC OS is installed successfully with Kernel version 4.5
on Parallels Workstation 2016 - but not on anything older than that.

Installing AOSC OS on Parallels Workstation takes all the normal procedures
(just like you do on a real x86_64 machine). So you might want to refer back to
the main [Installation Guide]](https://github.com/AOSC-Dev/aosc-os/blob/master/notes-for-md-raid.md)
before you proceed any further.

After the installation, you might find that AOSC OS is running with:

- Disgustingly low resolution;
- Sluggish cursor;
- No smooth integration of input devices;

And yes, you want a treatment from Parallels Tools now. First, install the
following packages to prime for the installation.

`sudo apt install gcc make dkms hplips multipath-tools`

Now, mount the Parallels Tools installation CD onto the virtual machine,
launch the installation program using the command below.

`sudo /mount/point/of/cd/install.sh`

Follow the on-screen instructions.

After the installation, you would need to append a kernel parameter to the GRUB
configuration in `/etc/default/grub` (using your favourite editor, as root).
And append the following to the line starting with `GRUB_CMDLINE_LINUX_DEFAULT`.

`iomem=relaxed`

So the line will look vaguely like something below.

`GRUB_CMDLINE_LINUX_DEFAULT="quiet rw splash iomem=relaxed"`

And finally, update your GRUB configuration with the following command.

`sudo grub-mkconfig -o /boot/grub/grub.cfg`

Reboot and you are good to go.

Locking kernel version
----------------------

As mentioned before, Parallels Workstation is quite specific with kernel
versions the virtual machine is running on, to prevent future complications, you
might want to lock your kernel version with the following command.

`sudo apt-mark hold linux+kernel`

And enjoy your year of subscription!
