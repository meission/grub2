# grub2
gnu.grub2 

https://www.gnu.org/software/grub/grub-download.html
>Obtaining GRUB
>GRUB 2 is now available via ftp. You can download releases from the ftp site ftp://ftp.gnu.org/gnu/grub.

>All the development is done through a Git repository. If you are interested in the cutting-edge version of GNU GRUB, for example, to test a newer version or to add new features, we strongly recommend giving the latest repository version a try. You can obtain the latest GRUB source from the GIT:
>```
>git clone git://git.savannah.gnu.org/grub.git
>```
>For developers with write access via ssh, use:
>```
>git clone <membername>@git.sv.gnu.org:/srv/git/grub.git
>```
>You can also use HTTP if needed.


    http://www.gnu.org/software/grub/
    http://lists.gnu.org/archive/html/grub-devel/2012-06/msg00093.html

Hello, all

I'm proud to announce the release of GNU GRUB version 2.00.

Since this version has a round number it has been paid special attention
to, and hopefully, represents higher quality.

This is the first time we include an official theme (starfield).

This version also includes EHCI driver.

Support for using GRUB as firmware on Yeeloong was added in GRUB 1.99,
and for 2.00 this support has been extended to Fuloong2F as well.

This is also the first time we release itanium and SGI mips port. Later
is experimental due to problems encountered with its firmware.

The release file is bigger than it should be because of autogeneration
issues. Other than the size these issues have no impact but their fixing
is scheduled for next release.

GRUB, also known as the GRand Unified Bootloader, is a modular, portable
bootloader that supports a number of platforms, including standard
BIOS-based PCs, EFI-based x86 (32-bit and 64-bit) and itanium systems,
IEEE-1275 platforms (such as the OLPC and some PowerPC/Sparc64
hardware), coreboot, the free (as in freedom) pre-boot initialization
framework, Yeeloong (laptop) and Fuloong2F (mini-box), free (as in
freedom) Loongson-2F-based (MIPS compliant CPU) systems, big-endian mips
ARCS systems (SGI), as well as bare i386 and mips (either endian) qemu.

Other major improvements include (extract from NEWS file):


* Appearence:
  * Official theme for gfxmenu (starfield)
  * Menu is organised with submenus.
  * Better default video mode selection using EDID.

* New platforms:
  * Itanium port.
  * Fuloong2F support (including GRUB as firmware)
  * Fuloong2E support (except GRUB as firmware)
  * ARCS (SGI machines) port.
  * qemu -M mips port.

* grub-mount to mount filesystems using GRUB FS drivers and FUSE.

* Changed security default so entries are locked by default if any
superuser is
  defined.

* New drivers:
  * EHCI.
  * AHCI.
  * ESCC serial.
  * IEEE1275 serial.
  * EFI serial.
  * Network stack for BIOS, IEEE1275, EMU and EFI, including TFTP, HTTP
and DNS.
  * VBE on coreboot support.

* New filesystem, filters and disks formats:
  * DVH partition map.
  * Plan9 partition map.
  * Big-endian mdraid.
  * Big-endian cpio.
  * ODC and NEWC cpio.
  * ExFAT.
  * Minix3fs.
  * Big-endian minixfs.
  * RomFS.
  * Squash4.
  * Support non-512B disk blocks.
  * LUKS and GELI support.
  * LDM read support (no install yet).
  * LZOP.

* Improved filesystem and disks formats support:
  * HFS+ label support.
  * Improved reiserfs support.
  * multidevice, mirrored and raidz(2,3) ZFS support.
  * RAID LVM (internal RAIDing) support.
  * ZFS crypto support.
  * ZLE and GZIP on ZFS support.
  * Support ZFS up to 33.
  * HFS string is now treated like mac-roman and not UTF-8
  * HFS mtime support.
  * Improved AFFS and SFS support.
  * LZO-compressed btrfs support.
  * cpio and tar symlinks support.
  * Better FS detection to reduce false positives.

* New boot protocols:
  * Ability to load another coreboot payload when on coreboot.
  * Plan9.
  * Freedos.
  * Ntldr/bootmgr (to load Windows bootloader).
  * chainloader --bpb support to patch FAT or NTFS BPB in memory to correct
    wrong partition offset.
  * PXE chainloading support.
  * Darwin 11 (Mac OS X Lion) protocol support.

* Boot protocol improvements:
  * Multiple initrd support.
  * Basic illumos and xnu autoconfig.

* Testing and debugging:
  * New grub-fstest commands: cat, zfsinfo, testload xnu_uuid
  * grub-fstest recursive directory compare for quickly checking that
    a directory is read correctly.
  * Backtace on crash (if gdb module is loaded, x86 only)
  * Disk cache statistics gathering.
  * GDB stub and GDB support script.
  * "make check" and "make bootcheck" expanded to almost all platforms
    (except i386-ieee1275, mips-arc, sparc64-ieee1275, ia64-efi and emu)
  * New `time' command.

* Performance:
  * Lazy scanning to avoid accessing devices which aren't really used.
    This avoids boot delay due to slow device scanning.
  * Use CPU cache when accessing video memory.
  * Search hints to first try the most likely device when searching for a
    device with given UUID. This avoids slow scanning in most cases.

* Internationalisation:
  * Updated to Unicode 6.0.
  * $"..." syntax for translation in grub scripting language. This
allows easy
    translation of grub.cfg at runtime.
  * Translations to many languages included in official distribution.

* Scripting:
  * $grub_cpu and $grub_platform variables for conditioning grub.cfg on
platform
    at runtime.
  * $feature_* variables to condition scripts on available features.
  * Use of ids to identify menu entries.
  * all_video module which is empty but depends on all video modules thus
    allowing easy loading of all of them.

* Installation:
  * grub-mknetdir script for easy creation of netbootable GRUB directory.
  * Itanium and mips support in grub-mkrescue.
  * grub-install support for all platforms except emu.
  * PreP partition install support.
  * No files conflict between flavours (except grub-mkrescue for ppc). This
    allows easy install of GRUB for several platforms.
  * grub-mkstandalone script for easy creating of image including all
modules
    for platforms with generous limit on image size.
  * program-transform-name now functions according to usual conventions.
    Use --grubdir and --bootdir to get old behaviour.

* ADLER32 and CRC64 support (for XZ and hashsum).

* ofconsole renamed to console

* Experimental support for compiling with Apple toolchain.

* grub-mkdevicemap removed. Now all devices are detected on invocation of
  any grub utility.


  <http://www.gnu.org/software/grub/>

A source tarball for the new release can be found at:

  http://ftp.gnu.org/gnu/grub/grub-2.00.tar.gz

or

  http://ftp.gnu.org/gnu/grub/grub-2.00.tar.xz


and its GPG detached signature [*]:

  http://ftp.gnu.org/gnu/grub/grub-2.00.tar.gz.sig

or

  http://ftp.gnu.org/gnu/grub/grub-2.00.tar.xz.sig


[*] You can use either of the above signature files to verify that
the corresponding file (without the .sig suffix) is intact.  First,
be sure to download both the .sig file and the corresponding tarball.
Then, run a command like this:

  gpg --verify grub-2.00.tar.gz.sig

If that command fails because you don't have the required public key,
then run this command to import it:

  gpg --keyserver keys.gnupg.net --recv-keys E82E4209

and rerun the `gpg --verify' command.

This release was bootstrapped with the following tools:
  Autoconf 2.69
  Automake 1.11.5

GCC 4.7 is the recommended version for building it, although any version
starting with 4.1.3 is supported in this release.

I hope you enjoy using GRUB as much as we enjoyed developing it.



-- 
Regards
Vladimir 'φ-coder/phcoder' Serbinenko
