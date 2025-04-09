Make sure you have provided the following information:

 - [x] link to your code branch cloned from keybase shim-review repo
 - [x] completed README.md file with the necessary information
 - [x] shim.efi to be signed
 - [x] public portion of your certificate(s) embedded in shim (the file passed to VENDOR_CERT_FILE)
 - [x] binaries, for which hashes are added do vendor_db ( if you use vendor_db and have hashes whitelisted )
 - [x] any extra patches to shim via your own git tree or as files
 - [x] build logs


###### What organization or people are asking to have this signed:
    HP Inc.

###### What product or service is this for:
    ThinPro for PC (an Ubuntu based Linux variant).  This is not our first linux release.  We have built and signed shim in the past.

###### What is the origin and full version number of your shim?
    https://github.com/rhboot/shim/tree/16.0

###### What's the justification that this really does need to be signed for the whole world to be able to boot it:
    Previous ThinPro are only released with HP hardwares support.  The next ThinPro release is targeted for not just HP's machines, but also general PC from other vendors.  We need our bootloader to be signed by MS UEFI key for it to be bootable there.

###### How do you manage and protect the keys used in your SHIM?
    The cert and keys are protected by HP's signing infrastructure.  Developer doesn't have direct access to the key.

###### Do you use EV certificates as embedded certificates in the SHIM?
    No

###### If you use new vendor_db functionality, are any hashes whitelisted, and if yes: for what binaries ?
    N/A

##### Were your old SHIM hashes provided to Microsoft ?
    Yes

##### Did you change your certificate strategy, so that affected by CVE CVE-2020-10713 grub2 bootloaders can not be verified ?
    Yes

###### If your SHIM launches any other components, please provide further details on what is launched
    It launches grub2 and fwupd

###### How do the launched components prevent execution of unauthenticated code?
    Full set of grub2 fixes, fwupd will not execute unauthenticated code.

###### Does your SHIM load any loaders that support loading unsigned kernels (e.g. GRUB)?
    No, our shim and grub will not load any unsigned binary when the system boots under
    secure boot mode.

###### What kernel are you using? Which patches does it includes to enforce Secure Boot?
    6.12.2

###### What changes were made since your SHIM was last signed?
    Update 15 to 16.0

###### What is the hash of your final SHIM binary?
Step 12/13 : RUN sha256sum shimx64.efi
68623a6d9364a4ce57795921abeafa017436edbf8597b0fd50ed5867c8ced50e  shimx64.efi
Step 13/13 : RUN sha1sum shimx64.efi
73373bcf58406899179b19a636ae517f66b9104b  shimx64.efi

