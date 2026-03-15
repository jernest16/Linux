Resetting the Root Password on RHEL
From the GRUB menu:
1.	Press e to edit the boot entry.
2.	Append rd.break to the kernel line.
3.	Press Ctrl + X to boot into emergency mode.
After entering emergency mode:
1.	Remount the sysroot filesystem in read-write mode:
mount -o remount,rw /sysroot
2.	Change root into the sysroot environment:
chroot /sysroot
3.	Reset the root password:
passwd
4.	Create the SELinux autorelabel file:
touch /.autorelabel
5.	Exit the environment and continue reboot:
exit
exit
