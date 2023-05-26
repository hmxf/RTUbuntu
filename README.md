# RT Ubuntu

This Document is a RT Kernel Build Guide from Bare Metal UPSquared Series Development Board, but theoretically useful for all situations if you need to build a kernel with Preempt-RT support for Ubuntu.

If you encounter a problem that is not mentioned in the documentation of this project on UPSquared Series Development Board, please check the official documentation [here](https://github.com/up-board/up-community/wiki/Ubuntu), because this project is also based on the official documentation. If problems occured on other platforms, you're basically on your own :(

----
## Pre-Steps

### Download System Image

- Choose [Ubuntu 18.04 LTS Image](https://releases.ubuntu.com/18.04.6/ubuntu-18.04.6-live-server-amd64.iso) for combination use with ROS Melodic.
- Choose [Ubuntu 20.04 LTS Image](https://cdimage.ubuntu.com/releases/focal/release/inteliotg/ubuntu-20.04-live-server-amd64+intel-iot.iso) for combination use with ROS Noetic.
- Download and Flash System Image to your UP Board with a USB Thumbdrive.

### System Flashing and Pre-configure

- Connect Display, Network and Keyboard Cable to your Board.
- Connect USB Thumbdrive with System Image and then Power on your Board.
- If you want to change BIOS settings of your Board, press DEL before LOGO vanished.
- BIOS Password is empty, when asked, just press ENTER.
- Install System with steps the same as what you were doing on PC or Server.
- After install, follow guides below to compile and install RT kernel:

## Build and install Guide

[Ubuntu 18.04 LTS RT Kernel Build and Install Guide](./18.04/ubuntu18.04-kernel-build-guide.md)

[Ubuntu 20.04 LTS RT Kernel Build and Install Guide](./20.04/ubuntu20.04-kernel-build-guide.md)

## Reference scripts

*Scripts should be Used for Documents' References, and, **READ THEM BEFORE EXECUTE**, Execute them in Order after your Modification.*

*Every Script Ends with a Reboot Operation, so **REBOOT** your board when scripts ended its execution with a "Finished!" message.*

### UP, UP 4000, UP Squared, UP Squared V2, UP Core, UP Core Plus, UP Xtreme, UP Squared Pro

These platforms can install Ubuntu 18.04 or 20.04, and use AAEON's kernel source to add driver support, or build our own kernel. If you are going to install Ubuntu 18.04 on these platforms, the full order of scripts need to be run are shown as below and have been tested under UP Squared + Ubuntu 18.04.

<ul>
<li>18.04/1.post-install.sh</li>
<li>18.04/2.update-up-kernel.sh</li>
<li>18.04/3.build-and-install-RT-Kernel.sh</li>
</ul>

Since 18.04 and 20.04 shares the same 5.4 kernel on these development boards, so users who use these models of development boards and expect to install Ubuntu 20.04 should install Ubuntu kernel 5.4.0 from AAEON's PPA source with [18.04/2.update-up-kernel.sh](./18.04/2.update-up-kernel.sh) and [18.04/3.build-and-install-RT-Kernel.sh](./18.04/3.build-and-install-RT-Kernel.sh) instead of [20.04/2.build-and-install-RT-Kernel.sh](./20.04/2.build-and-install-RT-Kernel.sh), which means the full order of scripts need to be run are shown as below.

<ul>
<li>20.04/1.post-install.sh</li>
<li>18.04/2.update-up-kernel.sh</li>
<li>18.04/3.build-and-install-RT-Kernel.sh</li>
</ul>

### UP Xtreme i11 and UP Squared 6000

These platforms can only install Ubuntu 20.04 or 22.04. Ubuntu 18.04 is not supported on these platforms. After my test on UP Squared 6000, the more obvious abnormalities include that the 2.5GbE network card cannot be recognized, the display resolution cannot be automatically adapted and difficult to adjust, etc. The full order of scripts need to be run are shown as below and have been tested under UP Squared 6000 + Ubuntu 20.04.

<ul>
<li>20.04/1.post-install.sh</li>
<li>20.04/2.build-and-install-RT-Kernel.sh</li>
</ul>
