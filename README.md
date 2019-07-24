Name of this project: tno-pki-m (Trust No One - Public Key Infrastructure - Manager)

Goal of this system: Create and back-up private keys of PGP and X509 on an air-gapped system (system 
without any network connection) without any storage to reduce the risk of leaking private key material
to a minimum.

A sub-goal is to document te procedures for renewing, revoking and modifying the keys. Many projects
describe well how to setup the keys but lack the steps for the more critical functions which one
will need over time.

Requirements is this system:

	- CPU: Intel Pentium Pro and up
	- RAM: 265 MB
	- Storage: CD/DVD Reader
	- A keyboard and monitor (no mouse since nu Windows manager is installed)

This live-boot image can be modified using the files in this git-repository. Some points of attention:

	- When booting de live iso on an air-gapped system make sure at least the date of the system
	  is correct since PGP or x509 keys have an expiration period need to set. If possible set the
	  time and date in the bios of the computer and you're good to go. If not use the 'date'
	  command after booting.
	- Always use 'lb clean --purge' when changing architectures. The clean command removes all 
	  default files and directories except the one below.
	- <projectdir>/auto/config: The general configuration for buildng the .iso.
	- <projectdir>/config/bootloaders/isolinux (in this case): The bootloader configuration.
	- <projectdir>/config/package-lists/my.list.chroot: Debian packages are added to the .iso.
	- <projectdir>/config/includes.chroot/etc/skel: Add default content to the homefolder like 
	  '.bashrc with aliasses and .gnupg/gpg.conf including rights) of the created user.
	- <projectdir>/config/packages.chroot/: Add custom packages outside Debian repositories.

Instructions for using this repository:

	- Have a Debian strechts up-to-date system, prefereably a VM.
	- sudo apt-get install live-build debootstrap
	- create project directory in your home-dir
	- from the project-dir do a git-pull of this project

