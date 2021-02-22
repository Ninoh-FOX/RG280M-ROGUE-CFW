# RG280M-ROGUE-CFW
Rogue CFW for RG280M

<p align="center"><img class="center" src ="https://raw.githubusercontent.com/Ninoh-FOX/RG280M-ROGUE-CFW/main/rg280m.png"></p>

ROGUE firmware for RG280M, same feactures that RG350

# INSTALLATION

If it is the first time you install the ROGUE CFW, please do not update from STOCK or another base system, use the sd_image.bin and burned in a new microsd (recommended a 16Gb of good speed), because if you can not have system failures.

If you need to update your ROGUE CFW, then use the update .opk packages.

# COMPILATION

first check that your linux system has the packages installed:

bison flex gettext texinfo wget cpio python unzip mercurial subversion libncurses5-dev libc6-dev-i386 bzr libssl-dev g ++ - multilib rsync java-wrappers mtools gcj-4.9-jdk

clone the repository with the command:

git clone --recursive https://github.com/Ninoh-FOX/toolchain


If you don't have the GCW0 build environment installed on your system there are two steps.

if you have debian 9, just download the binarion package at:

https://github.com/Ninoh-FOX/toolchain/releases

and extract this in /opt/gcw0-toolchain

If you have a different Linux distribution, run the rebuild.sh script that is inside the toolchain folder to create the correct / opt / gcw0-toolchain for your system.

Once all this is configured, the steps to compile the system are:

~/toolchain $ make rg280m_defconfig

~/toolchain $ make -f Makefile.rg280m -j4

When the whole process is finished you can create the installation packages or the sd_imagen.bin with the following commands:

~/toolchain/updaters $ ./create_kernel_rg280m.sh (this creates a kernel update package)

~/toolchain/updaters $ ./create_updater_rg280m.sh (this creates a complete system update package)

~/toolchain/updaters/imager_rg280m $ sudo ./create_sdimage.sh (this creates the sd_image.bin file)
