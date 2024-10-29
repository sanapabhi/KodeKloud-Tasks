









Here’s a list of over 50 Linux troubleshooting interview questions covering essential skills and problem-solving areas for a Linux administrator role:

**1. Basic Troubleshooting
How do you check the system's current uptime and load average?
What command do you use to check available disk space on the system?
How do you check the memory usage on a Linux system?
How would you identify large files that are consuming disk space?
How can you list all open ports on a Linux system?
How do you change the hostname of a Linux system?

-------------------------------------------------

1. Checking System Uptime and Load Average

To check the system's current uptime and load average, use the uptime command:

** uptime


2. Checking Available Disk Space

To check the available disk space on the system, use the df -h command:


** df -h


3. Checking Memory Usage

To check memory usage on a Linux system, use the free -h command:


** free -h


4. Identifying Large Files Consuming Disk Space

To identify large files consuming disk space, use the du command:


** du -sh * | sort -h


This command lists files and directories, sorted by size in human-readable format.

5. Listing Open Ports

To list open ports on a Linux system, use the netstat command:


** netstat -tulpn


6. Changing the Hostname

To change the hostname of a Linux system, edit the /etc/hostname file:


** sudo nano /etc/hostname


Replace the current hostname with the desired new hostname.

Then, update the /etc/hosts file:


sudo nano /etc/hosts


Replace the old hostname with the new hostname in the appropriate line.

Finally, restart the system for the changes to take effect:


sudo reboot

or 

hostnamectl set-hostname **name of host

---------------------------------------------------------------------------------------------------

**2. System Boot Issues
What do you do if a Linux system fails to boot?
How do you troubleshoot a system stuck in "grub" rescue mode?
How do you recover a forgotten root password?
What are the main logs to check if a Linux system fails to boot?
How do you change the runlevel in a system using systemd?
Explain how to configure and troubleshoot GRUB bootloader issues.
-------------------------------------------------
1. What to Do if a Linux System Fails to Boot
● Check Hardware: Ensure all hardware components are connected properly (e.g., hard drive, RAM, power supply).
● Inspect BIOS/UEFI: Enter BIOS/UEFI settings to confirm the correct boot device is selected.
● Use Recovery Media: Boot from a live CD/USB to access the filesystem for repairs.
● Check Boot Options: Use boot options like “recovery mode” from the GRUB menu for troubleshooting.
● Filesystem Check: Run fsck to check and repair filesystem errors if booting from recovery media.

2. How to Troubleshoot a System Stuck in "GRUB" Rescue Mode
● Identify Partitions: Use ls to display available drives and partitions.
● Set Root and Prefix:

set root=(hd0,msdos1)  # Change based on your system
set prefix=/boot/grub
insmod normal
normal
● Boot into Recovery: If successful, select a recovery option or boot normally.
● Fix Configuration: Once booted, check and fix GRUB configuration by editing /etc/default/grub and running update-grub.

3. How to Recover a Forgotten Root Password
● Boot into Recovery Mode: At the GRUB menu, select recovery mode or edit boot parameters to append single or init=/bin/bash to the kernel line.
● Remount Filesystem:

mount -o remount● ,rw /
● Reset Password● :

● passwd root
● Reboot: After resetting, type exec /sbin/init or reboot to restart the system.


4. Main Logs to Check if a Linux System Fails to Boot
● /var/log/syslog: Contains general system messages, including boot logs.
● /var/log/boot.log: Specific messages from the boot process.
● dmesg: Displays kernel ring buffer messages; useful for hardware-related issues.
● /var/log/messages: General messages and errors, depending on the distribution.


5. How to Change the Runlevel in a System Using systemd

● Change Target: Use systemctl to change the runlevel (known as target in systemd).

systemctl isolate multi-user.target  # For non-graphical mode
systemctl isolate graphical.target    # For graphical mode

● Set Default Target: To change the default target at boot, use:

systemctl set-default multi-user.target


6. Configure and Troubleshoot GRUB Bootloader Issues
● Configuration: Edit /etc/default/grub to customize settings (e.g., timeout, default OS). After editing, run:

update-grub

● Check GRUB Installation: If GRUB fails to load, reinstall it using:

grub-install /dev/sdX  # Replace sdX with your boot drive
update-grub

● Examine Boot Logs: Check logs in /boot/grub/grub.cfg for syntax or configuration issues.
● Use Boot Repair Tool: For persistent issues, consider using a boot repair tool available in many live CD distributions.

---------------------------------------------------------------------------------------------------

**3. File System & Disk Management
What commands would you use to manage disk partitions in Linux?
How do you mount and unmount a file system in Linux?
How do you add a new disk to the system and make it available?
Explain how to check and repair filesystem corruption using fsck.
How do you increase the size of a logical volume?
How do you troubleshoot "read-only filesystem" errors?

1. What Commands Would You Use to Manage Disk Partitions in Linux?

● fdisk: Used for creating, deleting, and managing partitions on MBR disks.

sudo fdisk /dev/sdX  # Replace sdX with your disk

● parted: A more versatile tool for both MBR and GPT partitions.

sudo parted /dev/sdX

● lsblk: Lists block devices and their partition structure.

lsblk

● blkid: Displays the UUIDs of partitions.

blkid

2. How Do You Mount and Unmount a File System in Linux?
● Mounting a Filesystem:

sudo mount /dev/sdXn /mnt/mountpoint  # Replace sdXn with your partition
● Unmounting a Filesystem:

sudo umount /mnt/mountpoint
● View Mounted Filesystems:

mount | column -t
3. How Do You Add a New Disk to the System and Make It Available?
● Physically Connect the Disk: Install the new disk.
● Identify the Disk: Use lsblk or fdisk -l to find the new disk (e.g., /dev/sdb).
● Partition the Disk:

sudo fdisk /dev/sdX  # Create partitions as needed
● Format the Partition:

sudo mkfs.ext4 /dev/sdXn  # Replace with your partition
● Create a Mount Point:

sudo mkdir /mnt/newdisk
● Mount the Disk:

sudo mount /dev/sdXn /mnt/newdisk
● Add to /etc/fstab for Automatic Mounting (optional):

echo '/dev/sdXn /mnt/newdisk ext4 defaults 0 2' | sudo tee -a /etc/fstab


4. Explain How to Check and Repair Filesystem Corruption Using fsck.

● Check Filesystem:

sudo fsck /dev/sdXn  # Replace with your partition

● Repair Filesystem: You can use the -y option to automatically answer "yes" to prompts.

sudo fsck -y /dev/sdXn

● Unmount Before Running: Ensure the filesystem is unmounted before checking or repairing, or use fsck in a recovery environment.

5. How Do You Increase the Size of a Logical Volume?
● Check Current Volume:

sudo lvdisplay
● Extend the Logical Volume:

sudo lvextend -L +10G /dev/vg_name/lv_name  # Increase by 10GB
● Resize the Filesystem: For ext4 filesystems:

sudo resize2fs /dev/vg_name/lv_name
6. How Do You Troubleshoot "Read-Only Filesystem" Errors?
● Check Filesystem Status: Use dmesg to check for kernel messages regarding the filesystem.

dmesg | grep "read-only"
● Remount the Filesystem:

sudo mount -o remount,rw /mountpoint

● Run fsck: If the issue persists, check for filesystem corruption using fsck.
● Review System Logs: Check /var/log/syslog or /var/log/messages for additional errors.
● Hardware Issues: Consider checking for hardware problems (e.g., bad sectors on the disk).

**4. User Management & Permissions
How do you create a new user and grant them specific permissions?
How would you troubleshoot a "permission denied" error for a user?
What is the difference between SUID, SGID, and sticky bit?
How can you manage and troubleshoot expired passwords for users?
Explain how to give a user sudo privileges.
How do you troubleshoot "too many open files" error?

**5. Process Management
What command shows running processes and their resource usage?
How would you kill a process that is not responding?
Explain how to set and manage process priorities using nice and renice.
What are "zombie" processes, and how can you eliminate them?
How do you investigate and resolve a high CPU usage problem?

**6. Network Troubleshooting
How do you check network connectivity to another server?
How do you display and manage IP addresses on Linux?
How do you troubleshoot a DNS resolution issue?
What commands can you use to test if a specific port is open on a server?
How do you troubleshoot network latency issues?
What is the purpose of iptables, and how do you check firewall rules?

**7. Service & Daemon Management
How do you start, stop, and restart services in Linux?
How do you check the status of a service using systemctl?
What would you do if a service fails to start?
Explain how to configure a service to start automatically on boot.
How would you troubleshoot "port already in use" errors?

**8. Package Management & Dependency Issues
How do you install, remove, and update packages on Linux?
What would you do if a package installation fails due to dependencies?
Explain how to troubleshoot missing shared library issues.
How do you list the files installed by a specific package?
How can you downgrade a package to an earlier version?

**9. Logs & Monitoring
How do you view system logs in Linux?
What are the key logs for troubleshooting kernel errors?
How would you analyze and troubleshoot high disk I/O activity?
How do you monitor real-time system performance in Linux?
What tools do you use to monitor network activity?

**10. Configuration Management & Security
How do you troubleshoot a "permission denied" error in SELinux?
How would you disable SELinux temporarily or permanently?
Explain how to configure SSH to allow key-based authentication only.
How do you troubleshoot SSH login failures?
How would you enforce password policies for users?
What is a "chroot" environment, and how is it used in troubleshooting?

**11. Advanced Troubleshooting
How do you identify and troubleshoot memory leaks?
What steps do you take to troubleshoot kernel panics?
How do you troubleshoot segmentation faults in applications?
Explain how to troubleshoot and resolve a deadlock in Linux.
How do you perform a kernel upgrade, and what checks do you perform after?



