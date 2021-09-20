# os-probe for the Haiku Computer Operating System

Linux "os-probes" file to detect Haiku OS and to automatically
add it to the GRUB boot menu.

First make sure the Haiku volumes you want to boot are mounted in Linux.
Then copy the 83haiku file to your Linux system in the os-probes subdirectory,
usually (in Fedora at least) it will be /usr/libexec/os-probes/mounted/83haiku
You can find older 83haiku versions in the https://github.com/agmsmith/os-probe
history, though the latest should be able to detect older Haiku too.

Then regenerate the GRUB boot configuration file.  This will happen
automatically the next time your kernel is updated.  For old school MBR BIOS
boot computers, the command is `grub2-mkconfig --output /boot/grub2/grub.cfg`
Computers using the newer UEFI boot system have a EFI/HAIKU/BOOTX64.EFI file
that you manually install to your EFI partition, and booting is done
differently, so you don't need this 83Haiku file for it.

The original seems to have come from Debian, though that's not certain, have a
look at https://packages.debian.org/search?keywords=os-prober  I stuck on a
GNU GPL3 license since that's closest to what Debian seems to use.

Updated in 2021 by agmsmith@ncf.ca to handle detection of the package based
Haiku OS, R1 Beta 3.

