Name of this project: tno-pki-m (Trust No One - Public Key Infrastructure - Manager)

Goal of this system: Create and back-up private keys of PGP and X509 on an air-gapped system (system 
without any network connection) and without any storage to reduce the risk of leaking private keys
to a minimum.

Requirements is this system:

	- CPU: Intel Pentium Pro and up
	- RAM: 265 MB
	- Storage: CD/DVD Reader
	- A keyboard and monitor (no mouse since nu Windows manager is installed)

This live-boot image can be modified using the files in this git-repository. Some points of attention:

	- When booting de live iso on an air-gapped system make sure at leaste the date of the system
	  is correct since PGP or x509 keys have an expiration period need to set. If possible set the
	  time and date in the bios of the computer and you're good to go.
	- Always use 'lb clean --purge' when changing architectures. The clean command removes all 
	  default files and directories except the ones below.
	- The generalconfiguration for buildng the .iso is done in <projectdir>/auto/config
	- The bootloader is configured in <projectdir>/config/bootloaders/isolinux (in my case).
	- Debian packages are added from <projectdir>/config/package-lists/my.list.chroot
	- Default content of homefolder (.bashrc with aliasses and .gnupg/gpg.conf including rights) of 
	  the created user is put in <projectdir>/config/includes.chroot/etc/skel/
	- Custom packages outside the Debian repository will be added in the future to <projectdir/
	  config/packages.chroot/.
                                                                                                   
