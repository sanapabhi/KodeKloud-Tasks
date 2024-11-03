1. How do you check the system's current uptime and load average?
Answer: Use the uptime or top command. Both commands display the system's uptime and load average, which indicates CPU load over the last 1, 5, and 15 minutes.

uptime
top

2. What command do you use to check available disk space on the system?
Answer: Use the df -h command. The -h option provides human-readable output, showing disk usage in gigabytes or megabytes.

df -h


3. How do you check the memory usage on a Linux system?
Answer: Use the free -m command, which displays memory usage in megabytes. You can also use top or htop for real-time memory monitoring.

free -m


4. How would you identify large files that are consuming disk space?
Answer: Use the du command. For example:

du -sh /* | sort -rh | head -10
This command shows the top 10 largest directories in the root file system.


5. How can you list all open ports on a Linux system?
Answer: Use the netstat command with -tuln or ss -tuln to list open TCP and UDP ports.

netstat -tuln
# or
ss -tuln


6. How do you troubleshoot a system stuck in "grub" rescue mode?
Answer: Use ls to list available partitions and then locate the correct boot partition. Set the root, load the linux and initrd images, and boot.

set root=(hd0,1)
linux /boot/vmlinuz root=/dev/sda1
initrd /boot/initrd.img
boot


7. How do you recover a forgotten root password?
Answer: Boot into single-user mode:
Reboot the system and edit the GRUB entry.
Add single or init=/bin/bash to the kernel line.
After booting, use the passwd command to reset the root password.

passwd


8. How do you add a new disk to the system and make it available?
Answer: Use the following steps:
Partition the new disk using fdisk.
Format the partition with mkfs.
Mount it to a directory.
Update /etc/fstab for persistence.

fdisk /dev/sdb
mkfs.ext4 /dev/sdb1
mount /dev/sdb1 /mnt
echo "/dev/sdb1 /mnt ext4 defaults 0 0" >> /etc/fstab


9. How do you troubleshoot a "permission denied" error for a user?
Answer: Check file and directory permissions using ls -l, as well as ownership with chown and permissions with chmod. Also, check if SELinux or AppArmor is blocking access.

ls -l /path/to/file
chown user:group /path/to/file
chmod 755 /path/to/file


10. How do you troubleshoot DNS resolution issues?
Answer: Use ping or nslookup to test DNS resolution.
Check /etc/resolv.conf for DNS server entries.
Use dig or host to verify the DNS response.

nslookup example.com
dig example.com
cat /etc/resolv.conf


11. What do you do if a Linux system fails to boot?
Answer: Check the following:
Inspect GRUB configuration by entering GRUB's command-line interface.
Use recovery mode to see where it fails.
Check /boot for missing kernel files or initramfs.
Boot with a Live CD to access and repair the root file system.


12. How do you check and repair filesystem corruption using fsck?
Answer: Unmount the filesystem and run fsck with the appropriate options.

umount /dev/sdX1
fsck -y /dev/sdX1


13. How do you troubleshoot SSH login failures?
Answer: Check the following:
SSH service status: systemctl status sshd.
Network connectivity to the server.
Correct SSH port in sshd_config.
Verify permissions for .ssh directory and files.
Look at /var/log/auth.log or /var/log/secure for errors.


14. How do you perform a kernel upgrade, and what checks do you perform after?
Answer: Use the package manager (e.g., yum or apt) to upgrade the kernel. Afterward, reboot and check with uname -r to ensure the new kernel is running. Also, confirm that all necessary drivers and services are working correctly.

sudo apt update && sudo apt upgrade -y
uname -r


15. What is a "chroot" environment, and how is it used in troubleshooting?
Answer: chroot changes the root directory for a set of processes, isolating them from the





You said:
more
ChatGPT said:
ChatGPT
Here are additional troubleshooting answers to common Linux administrator interview questions:

16. How do you troubleshoot high CPU usage on a Linux system?
Answer: Use tools like top, htop, or ps to identify the processes consuming high CPU.

top
htop
ps -eo pid,ppid,cmd,%mem,%cpu --sort=-%cpu | head
Check for runaway processes and analyze logs to understand the root cause. strace and lsof can also provide more detailed process insights.

17. What are "zombie" processes, and how can you eliminate them?
Answer: Zombie processes are defunct processes that have completed execution but still occupy an entry in the process table. They are usually removed when their parent process reads their exit status.
Solution: Identify the parent process using ps -el | grep Z, then kill or restart the parent process to clear zombie entries.


18. How do you troubleshoot a "Too many open files" error?
Answer: Increase the open file limit using ulimit -n for a session or set it globally in /etc/security/limits.conf.

ulimit -n 65535
Restart the application or service after updating limits. To check open files in use, use:

lsof | wc -l


19. How do you mount and unmount a file system in Linux?
Answer: Use mount to mount and umount to unmount.

mount /dev/sdX1 /mnt
umount /mnt
Add entries in /etc/fstab for persistent mounts.


20. How do you configure a service to start automatically on boot?
Answer: Use systemctl enable <service_name> to enable the service at startup.

systemctl enable sshd
You can verify the status with:

systemctl is-enabled sshd


21. How do you troubleshoot a high disk I/O issue?
Answer: Use tools like iostat, iotop, or dstat to check for processes generating high I/O.

iostat -xz 1
iotop
dstat -d
Review specific logs and examine processes and applications that may be writing or reading heavily from the disk.


22. How would you troubleshoot slow DNS resolution?
Answer: Start by using dig or nslookup to query the DNS server and assess response times.

dig google.com
nslookup google.com
Check /etc/resolv.conf to ensure the DNS server settings are correct, and review /etc/hosts to verify there are no conflicting entries.


23. How do you set and manage process priorities using nice and renice?
Answer: Use nice to start a process with a specific priority, and renice to change the priority of an existing process.

nice -n 10 command
renice 5 -p <PID>
Lower nice values have higher priority, while higher values reduce priority.


24. How would you troubleshoot "Port already in use" errors?
Answer: Use netstat -tuln or ss -tuln to identify which process is using the port.

netstat -tuln | grep <port_number>
Kill or reconfigure the process using the port if it conflicts with the service you intend to start.


25. How do you list all running services in Linux?
Answer: Use systemctl list-units --type=service to list all active services.

systemctl list-units --type=service


26. How do you troubleshoot file permission errors when copying files?
Answer: Check file permissions with ls -l and ensure you have write permissions to the destination directory.

ls -l /path/to/file
If permission errors persist, check for restrictive SELinux or AppArmor settings using getenforce or aa-status.


27. How do you configure SSH to allow key-based authentication only?
Answer: Modify the SSH configuration file /etc/ssh/sshd_config, setting PasswordAuthentication no and PubkeyAuthentication yes.

sudo nano /etc/ssh/sshd_config
# Set these values
PasswordAuthentication no
PubkeyAuthentication yes
Restart the SSH service: systemctl restart sshd.


28. How do you analyze and troubleshoot high memory usage on Linux?
Answer: Use free -m, top, or htop to monitor memory usage.
Use ps aux --sort=-%mem | head to list processes consuming the most memory.

ps aux --sort=-%mem | head
Consider using smem or vmstat for deeper analysis.

29. How do you find and terminate processes listening on a specific port?
Answer: Use netstat or ss to locate the process by port, then kill the process ID.

netstat -tuln | grep <port_number>
kill -9 <PID>


30. How do you configure and troubleshoot iptables firewall rules?
Answer: Use iptables -L -v -n to list all active rules. You can add, delete, or modify rules using iptables commands, and persist rules in /etc/sysconfig/iptables.

iptables -A INPUT -p tcp --dport 80 -j ACCEPT
iptables-save > /etc/sysconfig/iptables


31. How would you investigate a segmentation fault in an application?
Answer: Check dmesg for kernel messages or use strace to trace system calls and pinpoint the fault.

dmesg | grep segfault
strace -o output.log <application>

32. How do you set file or directory permissions using chmod and chown?
Answer: Use chmod to set permissions (e.g., chmod 755 file) and chown to change ownership (e.g., chown user:group file).

chmod 755 /path/to/file
chown user:group /path/to/file

33. How do you monitor real-time system performance in Linux?
Answer: Use tools like top, htop, vmstat, and iostat to observe real-time CPU, memory, and disk I/O.

vmstat 1
iostat 1

34. How do you install and remove packages on a Debian-based system?
Answer: Use apt to manage packages:

sudo apt update
sudo apt install <package_name>
sudo apt remove <package_name>

35. How do you troubleshoot kernel panics in Linux?
Answer: Check logs in /var/log/kern.log, /var/log/messages, or /var/log/syslog (depending on the distro). You can also enable kdump to capture core dumps for post-mortem analysis.

36. How do you perform a disk speed test in Linux?
Answer: Use dd to measure disk read/write speeds:

dd if=/dev/zero of=/tmp/test1.img bs=1G count=1 oflag=dsync
Tools like hdparm and fio also provide advanced benchmarking options.

37. How would you resolve dependency issues when installing packages?
Answer: Use apt-get -f install on Debian-based systems to fix broken dependencies, or yum check on RHEL/CentOS systems. Sometimes manually installing specific dependencies can also resolve conflicts.

38. How do you troubleshoot high swap usage?
Answer: Check if processes are consuming excessive memory using top or free -m. You can increase physical memory or tune the swappiness value in /proc/sys/vm/swappiness to reduce swap usage.

39. How do you set up persistent environment variables in Linux?
Answer: Add variables to /etc/environment or /etc/profile for system-wide persistence, or to ~/.bashrc or ~/.bash_profile for individual users.

40. How do you identify which process is using the most disk I/O?
Answer: Use iotop to view real-time disk I/O by process.

iotop -o
