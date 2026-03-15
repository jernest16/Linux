# HOW TO RESET PASSWORD FOR A ROOT ACCOUNT IN RHEL
# During the booting process
1. Press  `ESCAPE` key to bring the GRUB menu

## From the GRUB menu

1. Press `e` to edit the boot entry.
2. At the end of the line that starts with `Linux`, append `rd.break` to the kernel line.
3. Press `Ctrl + X` to boot into emergency mode.

## After entering into the emergency mode

1. Remount the `sysroot` filesystem into the read-write mode:

   ```bash
   mount -o remount,rw /sysroot
   
2. Change `root` into the sysroot environment:

   ```bash
   chroot /sysroot

3. Reset the `root` password:

   ```bash
   passwd root

4. Create SELinux autorelabel file:

   ```bash
   touch /.autorelabel

5. Type `exit` twice to exit the emergency environment and continue with the reboot process:

   ```bash
   exit
   exit
