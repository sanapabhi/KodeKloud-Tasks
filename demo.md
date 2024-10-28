Here’s a list of over 50 Linux troubleshooting interview questions covering essential skills and problem-solving areas for a Linux administrator role:

**1. Basic Troubleshooting
How do you check the system's current uptime and load average?
What command do you use to check available disk space on the system?
How do you check the memory usage on a Linux system?
How would you identify large files that are consuming disk space?
How can you list all open ports on a Linux system?
How do you change the hostname of a Linux system?


1. Checking System Uptime and Load Average

To check the system's current uptime and load average, use the uptime command:

uptime


2. Checking Available Disk Space

To check the available disk space on the system, use the df -h command:


df -h


3. Checking Memory Usage

To check memory usage on a Linux system, use the free -h command:


free -h


4. Identifying Large Files Consuming Disk Space

To identify large files consuming disk space, use the du command:


du -sh * | sort -h


This command lists files and directories, sorted by size in human-readable format.

5. Listing Open Ports

To list open ports on a Linux system, use the netstat command:


netstat -tulpn


6. Changing the Hostname

To change the hostname of a Linux system, edit the /etc/hostname file:


sudo nano /etc/hostname


Replace the current hostname with the desired new hostname.

Then, update the /etc/hosts file:


sudo nano /etc/hosts


Replace the old hostname with the new hostname in the appropriate line.

Finally, restart the system for the changes to take effect:


sudo reboot

---------------------------------------------------------------------------------------------------

**2. System Boot Issues
What do you do if a Linux system fails to boot?
How do you troubleshoot a system stuck in "grub" rescue mode?
How do you recover a forgotten root password?
What are the main logs to check if a Linux system fails to boot?
How do you change the runlevel in a system using systemd?
Explain how to configure and troubleshoot GRUB bootloader issues.

**3. File System & Disk Management
What commands would you use to manage disk partitions in Linux?
How do you mount and unmount a file system in Linux?
How do you add a new disk to the system and make it available?
Explain how to check and repair filesystem corruption using fsck.
How do you increase the size of a logical volume?
How do you troubleshoot "read-only filesystem" errors?

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



