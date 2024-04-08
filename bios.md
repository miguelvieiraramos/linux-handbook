# Red Hat - BIOS

Gostei muito da explicação da red hat em relação a BIOS. Então copiei o conteúdo para caso um dia eles excluam página.

# F.2.1.1. BIOS-based x86 Systems

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s1-boot-init-shutdown-process#s2-boot-init-shutdown-bios

The Basic Input/Output System (BIOS) is a firmware interface that controls not only the first step of the boot process, but also provides the lowest level interface to peripheral devices. On x86 systems equipped with BIOS, the program is written into read-only, permanent memory and is always available for use. When the system boots, the processor looks at the end of system memory for the BIOS program, and runs it.

Once loaded, the BIOS tests the system, looks for and checks peripherals, and then locates a valid device with which to boot the system. Usually, it checks any optical drives or USB storage devices present for bootable media, then, failing that, looks to the system's hard drives. In most cases, the order of the drives searched while booting is controlled with a setting in the BIOS, and it looks on the master IDE on the primary IDE bus or for a SATA device with a boot flag set. The BIOS then loads into memory whatever program is residing in the first sector of this device, called the Master Boot Record (MBR). The MBR is only 512 bytes in size and contains machine code instructions for booting the machine, called a boot loader, along with the partition table. Once the BIOS finds and loads the boot loader program into memory, it yields control of the boot process to it.

This first-stage boot loader is a small machine code binary on the MBR. Its sole job is to locate the second stage boot loader (GRUB) and load the first part of it into memory. 


# E.2.1. GRUB and the Boot Process on BIOS-based x86 Systems

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s1-grub-whatis#s2-grub-whatis-booting-bios

This section describes the specific role GRUB plays when booting a BIOS-based x86 system. For a look at the overall boot process, refer to Section F.2, “A Detailed Look at the Boot Process”.

GRUB loads itself into memory in the following stages:

1. The Stage 1 or primary boot loader is read into memory by the BIOS from the MBR [16]. The primary boot loader exists on less than 512 bytes of disk space within the MBR and is capable of loading either the Stage 1.5 or Stage 2 boot loader.

BIOS cannot read partition tables or file systems. It initializes the hardware, reads the MBR, then depends entirely on the stage 1 bootloader to continue the boot process.

2. The Stage 1.5 boot loader is read into memory by the Stage 1 boot loader, if necessary. Some hardware requires an intermediate step to get to the Stage 2 boot loader. This is sometimes true when the /boot/ partition is above the 1024 cylinder head of the hard drive or when using LBA mode. The Stage 1.5 boot loader is found either on the /boot/ partition or on a small part of the MBR and the /boot/ partition.

3. The Stage 2 or secondary boot loader is read into memory. The secondary boot loader displays the GRUB menu and command environment. This interface allows the user to select which kernel or operating system to boot, pass arguments to the kernel, or look at system parameters.

4.  The secondary boot loader reads the operating system or kernel as well as the contents of /boot/sysroot/ into memory. Once GRUB determines which operating system or kernel to start, it loads it into memory and transfers control of the machine to that operating system. 

The method used to boot Linux is called direct loading because the boot loader loads the operating system directly. There is no intermediary between the boot loader and the kernel.
The boot process used by other operating systems may differ. For example, the Microsoft Windows operating system, as well as other operating systems, are loaded using chain loading. Under this method, the MBR points to the first sector of the partition holding the operating system, where it finds the files necessary to actually boot that operating system.

GRUB supports both direct and chain loading boot methods, allowing it to boot almost any operating system. 

