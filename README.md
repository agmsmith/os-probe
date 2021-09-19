# os-probe for the Haiku Computer Operating System

Linux "os-probes" file to detect Haiku OS and to automatically
add it to the GRUB boot menu.

Copy the 83haiku file to your Linux system in the os-probes subdirectory,
usually (in Fedora at least) it will be /usr/libexec/os-probes/mounted/83haiku
Perhaps use a slightly different file name and don't overwrite 83haiku if you
want to keep the functionality to boot older Haiku.  You can find older 83haiku
versions in the https://github.com/agmsmith/os-probe history.

Then regenerate the GRUB boot configuration file.  This will happen
automatically the next time your kernel is updated.  For old school MBR BIOS
boot computers, the command is `grub2-mkconfig --output /boot/grub2/grub.cfg`.
Computers using the newer EFI boot system have a slightly different path to
grub.cfg.

The original seems to have come from Debian, though that's not certain, have a
look at https://packages.debian.org/search?keywords=os-prober  I stuck on a
GNU GPL3 license since that's closest to what Debian seems to use.

Updated in 2021 by agmsmith@ncf.ca to handle detection of the package based
Haiku OS, R1 Beta 3.

