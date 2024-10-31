# Tasks

● A Comprehensive List of Basic and Advanced Linux Commands

# Basic Commands:

1. Navigation and File Management:

cd: Change directory
ls: List files and directories
pwd: Print working directory
mkdir: Make directory
rmdir: Remove directory (empty)
rm: Remove files
mv: Move or rename files
cp: Copy files
touch: Create or update a file's timestamp
cat: Concatenate and print files

2.Text Processing:

grep: Search for patterns in files
sed: Stream editor for text manipulation
awk: Text processing tool for extracting, filtering, and formatting data
cut: Cut out selected columns from a file
paste: Merge lines of files

3. File Permissions and Ownership:

chmod: Change file permissions
chown: Change file ownership
chgrp: Change file group ownership

4. System Information:

uname: Print system information (kernel name, node name, release version, version, machine hardware name)
whoami: Print the current user name
id: Print user and group IDs
date: Display the current date and time
cal: Display a calendar

5. Process Management:

ps: Process list
kill: Kill a process
top: Display system processes
htop: Interactive process viewer

6. Package Management (Debian/Ubuntu):

apt-get: Package management tool
apt-cache: Search package information

7. Package Management (Red Hat/CentOS):

yum: Package management tool
dnf: Package manager (newer than yum)

8. User Management:

useradd: Add a new user
userdel: Delete a user
passwd: Change a user's password
sudo: Execute commands with superuser privileges
---------------------------------------------------------------------------------------------
# Advanced Commands:

1. Disk and File System Management:

df: Display disk usage
du: Display disk usage by file and directory
fsck: File system check and repair
mkfs: Make a filesystem
umount: Unmount a filesystem

2. Networking:

ifconfig: Configure network interfaces
ip: Advanced network configuration
ping: Send ICMP echo requests
traceroute: Trace route to a host
nslookup: Query DNS nameservers
telnet: Remote login
ssh: Secure Shell

3. System Logging:

tail: Display the last part of a file
head: Display the first part of a file
less: View files one page at a time
grep: Search for patterns in files
logrotate: Log file rotation

4. Shell Scripting:

bash: Bourne Again Shell
sh: Bourne Shell

5. Text Processing Tools:

sed: Stream editor
awk: Text processing language
grep: Search for patterns in files
cut: Cut out selected columns from a file
paste: Merge lines of files

6. Archiving and Compression:

tar: Archive files
gzip: Compress files
unzip: Unzip compressed files
bzip2: Compress files with bzip2
xz: Compress files with xz

7. Security:

iptables: Configure the firewall
fail2ban: Ban repeated login failures

8. Remote Access:

ssh: Secure Shell
scp: Secure Copy

9. Disk Partitioning:

fdisk: Partition disk drives
parted: Partition disk drives (more advanced)

10. System Boot and Startup:

chkconfig: Manage system services
systemctl: Systemd service manager



--------------------------------------------------------------------------------------------

Advanced Troubleshooting Commands in Linux
Here are some advanced Linux commands that can be useful for troubleshooting system issues:

● System Information and Monitoring:
dmesg: Displays kernel ring buffer messages, useful for boot errors and hardware issues.
last: Displays the last logged-in users and their login/logout times.
lastb: Displays the last failed login attempts.
w: Displays information about currently logged-in users and system load.
vmstat: Provides statistics about virtual memory usage.
iostat: Provides statistics about I/O device usage.
sar: System Activity Reporter, provides various system performance metrics.
top: Dynamically displays system processes.
htop: Enhanced version of top with more features.


● File System and Disk Usage:
lsof: Lists open files.
lsof +D /dev/sda1: Lists processes using a specific device.
lsof +D /dev/sda1 | grep delete: Lists processes holding a delete lock on a file system.
lsof | grep deleted: Lists processes holding deleted files.
find / -xdev -size +100M: Finds files larger than 100MB.
du -sh * | sort -h: Displays disk usage for each directory, sorted by size.

● Network Troubleshooting:
netstat: Displays network connections.
ss: A more powerful alternative to netstat.
tcpdump: Network packet analyzer.
ping: Sends ICMP echo requests to a host.
traceroute: Traces the route packets take to a destination.
nslookup: Queries DNS nameservers.

● Process Management:
ps auxf: Lists all running processes with extensive information.
kill: Terminates a process.
pkill: Kills processes based on name or other criteria.
renice: Changes the priority of a process.
strace: Traces system calls and signals.
ltrace: Traces library function calls.

● Log File Analysis:
tail -f /var/log/messages: Monitors the system log file in real-time.
grep "error" /var/log/messages: Searches for error messages in the system log.
grep "warning" /var/log/apache2/error.log: Searches for warning messages in the Apache error log.

● Troubleshooting Scripting:
Shell scripting (Bash, etc.): Automate tasks and create custom scripts.
Python: Powerful scripting language for automation and system administration.
Perl: General-purpose scripting language.




