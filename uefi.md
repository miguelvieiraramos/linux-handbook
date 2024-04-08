## Red Hat - UEFI

Eu gostei muito da explicação da red hat, então eu estou copiando o conteúdo que eles escreveram para caso um dia eles excluam a página.


# E.2.2. GRUB and the Boot Process on UEFI-based x86 Systems

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s2-grub-whatis-booting-uefi#doc-wrapper

This section describes the specific role GRUB plays when booting a UEFI-based x86 system. For a look at the overall boot process, refer to Section F.2, “A Detailed Look at the Boot Process”.

GRUB loads itself into memory in the following stages:

1. The UEFI-based platform reads the partition table on the system storage and mounts the EFI System Partition (ESP), a VFAT partition labeled with a particular globally unique identifier (GUID). The ESP contains EFI applications such as bootloaders and utility software, stored in directories specific to software vendors. Viewed from within the Red Hat Enterprise Linux 6.9 file system, the ESP is /boot/efi/, and EFI software provided by Red Hat is stored in /boot/efi/EFI/redhat/.
    
2. The /boot/efi/EFI/redhat/ directory contains grub.efi, a version of GRUB compiled for the EFI firmware architecture as an EFI application. In the simplest case, the EFI boot manager selects grub.efi as the default bootloader and reads it into memory.

If the ESP contains other EFI applications, the EFI boot manager might prompt you to select an application to run, rather than load grub.efi automatically.

3. GRUB determines which operating system or kernel to start, loads it into memory, and transfers control of the machine to that operating system. 

Because each vendor maintains its own directory of applications in the ESP, chain loading is not normally necessary on UEFI-based systems. The EFI boot manager can load any of the operating system bootloaders that are present in the ESP. 

# F.2.1.2. UEFI-based x86 Systems

https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/6/html/installation_guide/s1-boot-init-shutdown-process#s2-boot-init-shutdown-uefi

The Unified Extensible Firmware Interface (UEFI) is designed, like BIOS, to control the boot process (through boot services) and to provide an interface between system firmware and an operating system (through runtime services). Unlike BIOS, it features its own architecture, independent of the CPU, and its own device drivers. UEFI can mount partitions and read certain file systems.

When an x86 computer equipped with UEFI boots, the interface searches the system storage for a partition labeled with a specific globally unique identifier (GUID) that marks it as the EFI System Partition (ESP). This partition contains applications compiled for the EFI architecture, which might include bootloaders for operating systems and utility software. UEFI systems include an EFI boot manager that can boot the system from a default configuration, or prompt a user to choose an operating system to boot. When a bootloader is selected, manually or automatically, UEFI reads it into memory and yields control of the boot process to it. 
