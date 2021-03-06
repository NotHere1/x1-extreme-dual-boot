# x1-extreme-dual-boot

This is a high level step by step instructions on how i setup dual boot (ubuntu/windows 10) for lenovo x1 extreme.

---

## shrink but not remove windows partition

I did not removed windows entirely because Lenovo included several very useful hardware and software diagnostics tools specifically for X1 in the windows OS.

Given the x1 that i received has only 256GB SSD, using windows default disk management shrinkage is not an ideal solution, since it will only yield half of what's available (126GB of free space) for ubuntu. If you have at least 500GB, then the default disk mgnt shinkage will be more than suffice.

Considering i will not be using windows that often, i wanted to shrink it to its bare bone.

1. [create a recovery drive for windows](https://www.pcmag.com/feature/362167/how-to-revive-windows-10-with-a-recovery-drive)
2. [do all these](https://superuser.com/questions/1017764/how-can-i-shrink-a-windows-10-partition)
3. uninstall all unnecessary apps shipped together with windows (spotify, candy crush, ...)
4. clear storage and defrag the disk (i managed to get windows 10 C drive down to around 17GB)
5. [install MiniTool Partition Wizard](https://www.partitionwizard.com/free-partition-manager.html)
6. use the partition wizard and shrink the windows partition to (C drive current used space) + (just in case space ~ mine 13GB)

At the end of step 6, i have freed up 215GB of memory in the SSD for ubuntu and windows 10 only take up 30GB in total.

---

## pre-install ubuntu

1. disable fastboot (in windows), secureboot (via uefi/bios)
2. enable csm(via uefi/bios)

---

## install ubuntu

1. [download ubuntu](https://www.ubuntu.com/download/desktop/thank-you?country=US&version=18.04.2&architecture=amd64)
2. [install rufus](https://rufus.ie/)
3. [create bootable usb ubuntu using rufus](https://tutorials.ubuntu.com/tutorial/tutorial-create-a-usb-stick-on-windows#0)
4. boot into usb ubuntu from windows 
   1. (windows key + i)
   2. choose (update & security)
   3. choose recovery sidetab
   4. choose advanced option restart
   5. choose usb fd
5. [ubuntu installation](https://tutorials.ubuntu.com/tutorial/tutorial-install-ubuntu-desktop#3)

---

## post install ubuntu

since x1 extreme comes with a nvidia gpu, ubuntu at first will use open sourced nouveau driver for the xorg server display. but this could potentially caused ubuntu to hang after login.

[do this immediately when GRUB menu pops up after installation restart](https://itsfoss.com/fix-ubuntu-freezing/)

then once login into ubuntu, update and replace nouveau nvidea custom driver

