# Ansible-Tasks

### `Site`

# https://docs.ansible.com/users.html

# Ansible Commands Reference

## Table of Contents
1. [Basic Commands](#basic-commands)
2. [Advanced Commands](#advanced-commands)
3. [Production Level Commands](#production-level-commands)
4. [Troubleshooting Commands](#troubleshooting-commands)

## Basic Commands

---------------------------------------------------------------------------------------------------

### 1. `ansible`
Runs a command on a set of hosts.

``bash
			ansible all -m ping
Pings all hosts to check connectivity.

2. ansible-playbook
Runs an Ansible playbook.


			ansible-playbook site.yml
Executes the specified playbook.

3. ansible-galaxy
Manages Ansible roles.


			ansible-galaxy install username.role
Installs a role from Galaxy.

4. ansible-vault
Encrypts and decrypts sensitive data.


			ansible-vault create secrets.yml
Creates an encrypted file.

5. ansible-doc
Displays documentation for Ansible modules.


			ansible-doc -l
Lists all available modules.

6. ansible-inventory
Displays the current inventory.


			ansible-inventory --list
Shows all hosts in the inventory.

7. ansible-config
Displays Ansible configuration.


			ansible-config dump
Dumps current configuration settings.

8. ansible-pull
Pulls playbooks from a source control system.


			ansible-pull -U https://github.com/user/repo.git
Pulls and executes playbooks from a Git repository.

9. ansible-playbook --check
Runs a playbook in dry-run mode.


			ansible-playbook site.yml --check
Simulates playbook execution without making changes.

10. ansible all -m shell -a "command"
Executes a shell command on all hosts.


			ansible all -m shell -a "uptime"
Retrieves uptime information from all hosts.

---------------------------------------------------------------------------------------------------

# Advanced Commands

11. ansible-playbook --tags
Runs specific tags in a playbook.


			ansible-playbook site.yml --tags "install"
Executes only tasks marked with "install".

12. ansible-playbook --limit
Limits the execution to a subset of hosts.


			ansible-playbook site.yml --limit webservers
Runs playbook only on hosts in the "webservers" group.

13. ansible-playbook --extra-vars
Passes extra variables to a playbook.


			ansible-playbook site.yml --extra-vars "env=production"
Provides additional variables during execution.

14. ansible-playbook --inventory
Specifies a different inventory file.


			ansible-playbook -i my_inventory.ini site.yml
Uses the specified inventory file instead of the default.

15. ansible-vault encrypt
Encrypts a file.


			ansible-vault encrypt secrets.yml
Encrypts the specified file.

16. ansible-vault decrypt
Decrypts a file.


			ansible-vault decrypt secrets.yml
Decrypts the specified file.

17. ansible-vault edit
Edits an encrypted file.


			ansible-vault edit secrets.yml
Opens an encrypted file for editing.

18. ansible-galaxy init
Creates a new role structure.


			ansible-galaxy init my_role
Initializes a new role directory structure.

19. ansible all -m debug
Debugs variable values.

	
			ansible all -m debug -a "var=ansible_env"
Displays environment variables for all hosts.

20. ansible-playbook --diff
Shows differences in file changes.


			ansible-playbook site.yml --diff
Displays changes made to files during playbook execution.

---------------------------------------------------------------------------------------------------

# Production Level Commands

21. ansible-playbook --forks
Sets the number of parallel processes.


			ansible-playbook site.yml --forks 10
Executes tasks on multiple hosts in parallel.

22. ansible-playbook --timeout
Sets the connection timeout.


			ansible-playbook site.yml --timeout 30
Sets a timeout for host connections.

23. ansible all -m wait_for
Waits for a service to be available.


			ansible all -m wait_for -a "port=80 state=started"
Waits for port 80 to be open.

24. ansible all -m service
Manages services.


			ansible all -m service -a "name=httpd state=started"
Ensures the httpd service is running on all hosts.

25. ansible-playbook --become
Runs tasks with elevated privileges.


			ansible-playbook site.yml --become
Executes tasks as a different user (e.g., root).

26. ansible all -m yum
Installs packages using YUM.


			ansible all -m yum -a "name=httpd state=present"
Installs the httpd package on all hosts.

27. ansible all -m apt
Installs packages using APT.


			ansible all -m apt -a "name=nginx state=latest"
Ensures the latest version of nginx is installed.

28. ansible all -m copy
Copies files to remote hosts.


			ansible all -m copy -a "src=/local/file dest=/remote/file"
Copies a file from the local system to remote hosts.

29. ansible all -m template
Processes Jinja2 templates.


			ansible all -m template -a "src=template.j2 dest=/etc/config.conf"
Copies and processes a Jinja2 template on remote hosts.

30. ansible all -m fetch
Fetches files from remote hosts.


			ansible all -m fetch -a "src=/remote/file dest=/local/path"
Retrieves a file from remote hosts to the local machine.

---------------------------------------------------------------------------------------------------

# Troubleshooting Commands

31. ansible all -m ping
Tests connectivity to hosts.


			ansible all -m ping
Verifies that Ansible can reach the specified hosts.

32. ansible-playbook --check
Performs a dry run of the playbook.


			ansible-playbook site.yml --check
Simulates the playbook execution without making changes.

33. ansible all -m shell -a "echo $?"
Checks the exit status of commands.


			ansible all -m shell -a "echo $?"
Returns the exit status of the last command executed.

34. ansible-playbook -vvvv
Increases verbosity level.


			ansible-playbook site.yml -vvvv
Provides detailed output for troubleshooting.

35. ansible all -m debug
Prints debug information.


			ansible all -m debug -a "var=some_variable"
Displays the value of a variable for troubleshooting.

36. ansible-playbook --list-tasks
Lists all tasks in a playbook.


			ansible-playbook site.yml --list-tasks
Shows the tasks that will be executed in the playbook.

37. ansible-playbook --list-hosts
Lists all hosts targeted by the playbook.


			ansible-playbook site.yml --list-hosts
Displays all hosts that will be affected by the playbook.

38. ansible-playbook --syntax-check
Checks the syntax of a playbook.


			ansible-playbook site.yml --syntax-check
Validates the playbook for syntax errors.

39. ansible all -m setup
Gathers facts about hosts.


			ansible all -m setup
Retrieves system information and configurations from hosts.

40. ansible all -m command
Runs a command on remote hosts.


			ansible all -m command -a "ls -l"
Executes a command and returns the output.

---------------------------------------------------------------------------------------------------

# Additional Commands

41. ansible-playbook --tags
Specifies tags to run.


			ansible-playbook site.yml --tags "setup"
Executes only tasks marked with specific tags.

42. ansible all -m lineinfile
Manages lines in a file.


			ansible all -m lineinfile -a "path=/etc/hosts line='127.0.0.1 myhost'"
Ensures a specific line is present in a file.

43. ansible all -m user
Manages user accounts.


			ansible all -m user -a "name=newuser state=present"
Creates a new user on all hosts.

44. ansible all -m group
Manages groups.


			ansible all -m group -a "name=newgroup state=present"
Creates a new group on all hosts.

45. ansible all -m service
Manages services.


			ansible all -m service -a "name=nginx state=stopped"
Stops the nginx service on all hosts.

46. ansible all -m reboot
Reboots remote hosts.


			ansible all -m reboot
Reboots all specified hosts.

47. ansible all -m wait_for
Waits for ports to be open or services to start.


			ansible all -m wait_for -a "port=22 state=started timeout=300"
Waits for port 22 to be open, with a timeout of 300 seconds.

48. ansible all -m fetch
Fetches files from remote hosts.


			ansible all -m fetch -a "src=/var/log/syslog dest=~/logs/"
Retrieves syslog from remote hosts to local.

49. ansible all -m apt -a "update_cache=true"
Updates the APT cache.


			ansible all -m apt -a "update_cache=true"
Updates package cache on all Debian/Ubuntu hosts.

50. ansible all -m yum -a "name=package state=absent"
Removes a package.


			ansible all -m yum -a "name=httpd state=absent"
Uninstalls the httpd package from all hosts.

---------------------------------------------------------------------------------------------------

# Further Commands

51. ansible all -m cron
Manages cron jobs.


			ansible all -m cron -a "name='backup' minute='0' hour='1' job='tar -czf /backup.tgz /data'"
Creates a cron job for backups.

52. ansible all -m copy
Copies files from the control machine to the remote machines.


			ansible all -m copy -a "src=/local/file dest=/remote/path"
Copies a file to the specified path on all hosts.

53. ansible all -m unarchive
Extracts files from an archive.


			ansible all -m unarchive -a "src=/tmp/archive.tar.gz dest=/opt/"
Extracts the archive to the specified directory.

54. ansible all -m assemble
Assembles files from a directory.


			ansible all -m assemble -a "src=/path/to/files dest=/path/to/assembled_file"
Combines files into one.

55. ansible all -m debug -a "msg='Hello World'"
Displays a message.


			ansible all -m debug -a "msg='Hello World'"
Prints "Hello World" for all hosts.

56. ansible all -m ini_file
Manages INI-style configuration files.


			ansible all -m ini_file -a "path=/etc/my.cnf section=mysqld option=log_bin value=mysql-bin"
Adds or modifies INI file entries.

57. ansible all -m user -a "name=jdoe password=secret" --ask-pass
Creates a user with a password.


			ansible all -m user -a "name=jdoe password=secret" --ask-pass
Creates user 'jdoe' with a specified password.

58. ansible all -m uri
Interacts with web services.


			ansible all -m uri -a "url=http://example.com method=GET"
Makes a GET request to a specified URL.

59. ansible all -m firewalld
Manages firewall rules.


			ansible all -m firewalld -a "service=http permanent=true state=enabled"
Enables the HTTP service in the firewall.

60. ansible all -m command -a "systemctl restart httpd"
Restarts a service.

	
			ansible all -m command -a "systemctl restart httpd"
Restarts the httpd service on all hosts.

61. ansible all -m command -a "systemctl status httpd"
Checks the status of a service.


			ansible all -m command -a "systemctl status httpd"
Displays the status of the httpd service.

62. ansible all -m assemble
Combines multiple files into a single file.


			ansible all -m assemble -a "src=/path/to/files dest=/path/to/assembled_file"
Assembles files into a single output file.

63. ansible all -m git
Manages Git repositories.


			ansible all -m git -a "repo='https://github.com/user/repo.git' dest='/path/to/dir'"
Clones or updates a Git repository on remote hosts.

64. ansible all -m service
Starts or stops services.


			ansible all -m service -a "name=nginx state=started"
Ensures nginx is running.

65. ansible all -m package
Manages packages across different systems.


			ansible all -m package -a "name=git state=present"
Installs git on all hosts using the package manager.

66. ansible all -m win_shell
Runs a command on Windows hosts.


			ansible all -m win_shell -a "Get-Process"
Executes a PowerShell command on Windows hosts.

67. ansible all -m win_user
Manages user accounts on Windows.


			ansible all -m win_user -a "name=Administrator password='StrongPassword' state=present"
Creates or updates a Windows user.

68. ansible all -m win_feature
Manages Windows features.


			ansible all -m win_feature -a "name=Web-Server state=present"
Installs a Windows feature like IIS.

69. ansible all -m win_firewall_rule
Manages Windows firewall rules.


			ansible all -m win_firewall_rule -a "name='Allow HTTP' enable=yes direction=in action=allow localport=80"
Creates a firewall rule on Windows.

70. ansible all -m win_service
Manages Windows services.


			ansible all -m win_service -a "name=wuauserv state=started"
Ensures the Windows Update service is running.

---------------------------------------------------------------------------------------------------

# Summary of Key Concepts

**Playbook Structure**
		
  	A playbook is a YAML file containing plays. Each play defines a set of tasks to execute on specified hosts.

**Inventory**

	An inventory is a file that lists all the hosts Ansible will manage. It can be in INI, YAML, or dynamic formats.

**Variables**

	Ansible supports variables to make playbooks more dynamic. Variables can be defined in playbooks, inventory files, or external sources.

**Roles**

	Roles are a way to organize playbooks and tasks into reusable components. Each role has its own directory structure.

**Handlers**

	Handlers are special tasks that only run when notified by another task. This is useful for managing services.

**Facts**

	Ansible collects information about remote hosts, known as facts. These can be used to make decisions in playbooks.

**Templates**

	Ansible uses Jinja2 templates to dynamically create files based on variables.

**Vault**

	Ansible Vault is used to encrypt sensitive data, such as passwords or API keys, in your playbooks.

**Modules**

	Ansible has a wide range of modules for various tasks, including system management, cloud management, and more.

---------------------------------------------------------------------------------------------------



# Ansible Commands Reference

## Table of Contents
- [Basic Commands](#basic-commands)
- [Advanced Commands](#advanced-commands)
- [Troubleshooting Commands](#troubleshooting-commands)
- [Production Level Commands](#production-level-commands)
- [More Commands](#more-commands)

---------------------------------------------------------------------------------------------------

## Basic Commands

### 1. `ansible`
Run ad-hoc commands on managed nodes.

``bash
		ansible all -m ping
Explanation: Pings all hosts in the inventory to check connectivity.

2. ansible-playbook
Run a playbook.


		ansible-playbook site.yml
Explanation: Executes the playbook defined in site.yml.

3. ansible-galaxy
Manage Ansible roles.


		ansible-galaxy install username.role
Explanation: Installs a role from Ansible Galaxy.

4. ansible-vault
Encrypt or decrypt files.


		ansible-vault create secrets.yml
Explanation: Creates a new encrypted file secrets.yml.

5. ansible-config
View or modify Ansible configuration.


		ansible-config dump
Explanation: Dumps the current Ansible configuration.

6. ansible-inventory
Display the inventory.


		ansible-inventory --graph
Explanation: Shows the inventory as a graph structure.

7. ansible-playbook --syntax-check
Check for syntax errors in a playbook.


		ansible-playbook site.yml --syntax-check
Explanation: Validates the syntax of the playbook without executing it.

8. ansible-vault encrypt-string
Encrypt a single string.


		ansible-vault encrypt-string 'my_secret_password' --name 'my_password'
Explanation: Encrypts a string and outputs a variable definition.

9. ansible-doc
Show documentation for modules.


		ansible-doc -l
Explanation: Lists all available Ansible modules.

10. ansible-pull
Pull playbooks from a VCS repository.


		ansible-pull -U https://github.com/user/repo.git
Explanation: Runs Ansible playbooks pulled from a Git repository.

---------------------------------------------------------------------------------------------------

# Advanced Commands
11. ansible-playbook --check
Run a playbook in check mode.


		ansible-playbook site.yml --check
Explanation: Simulates the playbook execution without making any changes.

12. ansible-playbook --diff
Show differences in files.


		ansible-playbook site.yml --diff
Explanation: Displays changes made to files during the playbook run.

13. ansible-playbook --tags
Run specific tags in a playbook.


		ansible-playbook site.yml --tags "install"
Explanation: Executes only the tasks tagged with install.

14. ansible-playbook --limit
Limit execution to specific hosts.


		ansible-playbook site.yml --limit webservers
Explanation: Runs the playbook only on hosts in the webservers group.

15. ansible-pull --accept-host-key
Automatically accept SSH host keys.


		ansible-pull -U https://github.com/user/repo.git --accept-host-key
Explanation: Automatically accepts new host keys without manual intervention.

16. ansible-playbook -e
Pass extra variables.


		ansible-playbook site.yml -e "env=production"
Explanation: Passes extra variables to the playbook.

17. ansible-playbook --extra-vars
Specify extra variables from a file.


		ansible-playbook site.yml --extra-vars "@vars.yml"
Explanation: Loads extra variables from vars.yml.

18. ansible-playbook -K
Prompt for become password.


		ansible-playbook site.yml -K
Explanation: Prompts for the password to escalate privileges (sudo).

19. ansible-playbook --become
Run playbook with elevated privileges.


		ansible-playbook site.yml --become
Explanation: Executes tasks with elevated privileges.

20. ansible-playbook --force
Force execution of tasks even if they are skipped.


		ansible-playbook site.yml --force
Explanation: Overrides any task skipping conditions.

---------------------------------------------------------------------------------------------------

# Troubleshooting Commands

21. ansible-playbook --start-at-task
Resume playbook from a specific task.


		ansible-playbook site.yml --start-at-task="Task Name"
Explanation: Starts execution at the specified task.

22. ansible -m setup
Gather facts about the host.


		ansible localhost -m setup
Explanation: Collects and displays system information about the localhost.

23. ansible -m command
Run shell commands on remote hosts.


		ansible all -m command -a "whoami"
Explanation: Executes the whoami command on all hosts.

24. ansible-playbook --list-tasks
List tasks in a playbook without executing.


		ansible-playbook site.yml --list-tasks
Explanation: Displays all tasks defined in the playbook.

25. ansible-playbook --list-tags
List tags in a playbook.


		ansible-playbook site.yml --list-tags
Explanation: Shows all tags that can be used to limit execution.

26. ansible -m shell
Run shell commands on remote hosts.


		ansible all -m shell -a "echo $HOSTNAME"
Explanation: Executes a shell command on all hosts, allowing for shell features like variable expansion.

27. ansible-playbook --step
Execute playbook step-by-step.


		ansible-playbook site.yml --step
Explanation: Prompts before executing each task.

28. ansible-playbook --timeout
Set a timeout for SSH connections.


		ansible-playbook site.yml --timeout 30
Explanation: Sets a timeout of 30 seconds for SSH connections.

29. ansible -m raw
Run commands without a module.


		ansible all -m raw -a "uname -a"
Explanation: Executes a command directly on the host without using any modules.

30. ansible -m debug
Display debugging information.


		ansible all -m debug -a "var=ansible_hostname"
Explanation: Displays the value of the specified variable.

---------------------------------------------------------------------------------------------------

# Production Level Commands

31. ansible-playbook -i inventory.ini
Specify an inventory file.


		ansible-playbook -i inventory.ini site.yml
Explanation: Uses the specified inventory file for the playbook execution.

32. ansible-vault encrypt
Encrypt a file.


		ansible-vault encrypt my_secret.yml
Explanation: Encrypts my_secret.yml using Ansible Vault.

33. ansible-playbook --private-key
Use a specific SSH private key.


		ansible-playbook -i inventory.ini site.yml --private-key=my_key.pem
Explanation: Uses my_key.pem as the SSH key for authentication.

34. ansible-playbook --forks
Control parallelism.


		ansible-playbook site.yml --forks 10
Explanation: Runs up to 10 tasks in parallel.

35. ansible-playbook --limit
Run against specific groups.


		ansible-playbook site.yml --limit dev
Explanation: Limits execution to the dev group in the inventory.

36. ansible-playbook --vault-password-file
Use a file for vault password.


		ansible-playbook site.yml --vault-password-file .vault_pass
Explanation: Specifies a file that contains the password for Ansible Vault.

37. ansible-playbook --check --diff
Run in check mode with diff.


		ansible-playbook site.yml --check --diff
Explanation: Checks for changes while displaying differences.

38. ansible-vault decrypt
Decrypt a file.


		ansible-vault decrypt my_secret.yml
Explanation: Decrypts the specified file.

39. ansible-galaxy init
Create a new role skeleton.


		ansible-galaxy init my_new_role
Explanation: Initializes a new role directory structure.

40. ansible-playbook --become-user
Specify the user for privilege escalation.


		ansible-playbook site.yml --become-user=root
Explanation: Runs tasks as the specified user.

---------------------------------------------------------------------------------------------------

# More Commands
41. ansible-playbook --list-hosts
List the hosts that will be affected by the playbook.


		ansible-playbook site.yml --list-hosts
Explanation: Displays the list of hosts that the playbook will target.

42. ansible-vault view
View an encrypted file.


		ansible-vault view secrets.yml
Explanation: Displays the contents of an encrypted file.

43. ansible-playbook --timeout
Set the timeout for connecting to hosts.


		ansible-playbook site.yml --timeout 15
Explanation: Sets a 15-second timeout for connecting to hosts.

44. ansible-console
Open an interactive console for running Ansible commands.


		ansible-console
Explanation: Provides an interactive prompt for executing Ansible commands.

45. ansible-playbook -C
Check for changes without making any.


		ansible-playbook site.yml -C
Explanation: Performs a dry run to see what changes would be made.

46. ansible-playbook --module-path
Specify additional module paths.


		ansible-playbook site.yml --module-path /path/to/modules
Explanation: Adds a directory to search for Ansible modules.

47. ansible-playbook --skip-tags
Skip specific tags during execution.


		ansible-playbook site.yml --skip-tags "skip_this_task"
Explanation: Executes the playbook while skipping tasks tagged with skip_this_task.

48. ansible all -a
Run a command on all hosts.


		ansible all -a "uptime"
Explanation: Executes the uptime command on all hosts in the inventory.

49. ansible-playbook --become-method
Specify the method for privilege escalation.


		ansible-playbook site.yml --become-method=sudo
Explanation: Specifies the method of privilege escalation to use.

50. ansible -m win_ping
Ping Windows hosts.


		ansible windows -m win_ping
Explanation: Checks connectivity to Windows hosts using the win_ping module.

51. ansible-playbook --verbosity
Set the verbosity level.


		ansible-playbook site.yml --verbosity 2
Explanation: Increases the verbosity of the output to level 2.

52. ansible-playbook --list-plays
List plays in a playbook.


		ansible-playbook site.yml --list-plays
Explanation: Displays the list of plays defined in the playbook.

53. ansible -m lineinfile
Modify lines in a file.


		ansible all -m lineinfile -a "path=/etc/hosts line='127.0.0.1 localhost'"
Explanation: Ensures that the specified line exists in the target file.

54. ansible-playbook --force-handlers
Force handlers to run even if they are not notified.


		ansible-playbook site.yml --force-handlers
Explanation: Forces all handlers to run regardless of notifications.

55. ansible-vault rekey
Change the password for an encrypted file.


		ansible-vault rekey my_secret.yml
Explanation: Changes the password used to encrypt the specified file.

56. ansible-playbook -v
Run with increased verbosity.


		ansible-playbook site.yml -v
Explanation: Runs the playbook with verbose output.

57. ansible-galaxy search
Search for roles in Ansible Galaxy.


		ansible-galaxy search apache
Explanation: Searches for roles related to Apache in Ansible Galaxy.

58. ansible-galaxy remove
Remove a role.


		ansible-galaxy remove username.role
Explanation: Removes the specified role from the local system.

59. ansible-pull --update
Force update when pulling.


		ansible-pull -U https://github.com/user/repo.git --update
Explanation: Forces a pull of the latest changes from the repository.

60. ansible-playbook -u
Specify the remote user.


		ansible-playbook site.yml -u ubuntu
Explanation: Uses ubuntu as the remote user for SSH connections.

61. ansible-playbook --ask-become-pass
Prompt for privilege escalation password.


		ansible-playbook site.yml --ask-become-pass
Explanation: Prompts for the password needed to escalate privileges.

62. ansible-config view
View the current Ansible configuration.


		ansible-config view
Explanation: Displays the current configuration settings.

63. ansible-playbook --ignore-errors
Continue execution even if tasks fail.


		ansible-playbook site.yml --ignore-errors
Explanation: Ignores errors and continues running the playbook.

64. ansible-playbook --diff
Show diffs of changed files.


		ansible-playbook site.yml --diff
Explanation: Displays the differences for any modified files.

65. ansible all -m shell -a
Run a shell command and capture output.


		ansible all -m shell -a "ls -l"
Explanation: Executes the ls -l command on all hosts.

66. ansible-playbook -f
Specify the number of forks.


		ansible-playbook site.yml -f 5
Explanation: Sets the number of parallel tasks to 5.

67. ansible-vault edit
Edit an encrypted file.


		ansible-vault edit secrets.yml
Explanation: Opens the encrypted file in the default editor.

68. ansible-playbook --no-cache
Prevent caching of results.


		ansible-playbook site.yml --no-cache
Explanation: Disables caching for the current execution.

69. ansible -m user
Manage user accounts.


		ansible all -m user -a "name=test_user state=present"
Explanation: Creates a user account named test_user.

70. ansible -m apt
Manage packages with APT.


		ansible all -m apt -a "name=nginx state=present"
Explanation: Installs the nginx package on all Debian-based systems.

71. ansible -m service
Manage services.


		ansible all -m service -a "name=nginx state=started"
Explanation: Starts the nginx service on all hosts.

72. ansible -m copy
Copy files to remote hosts.


		ansible all -m copy -a "src=/local/file dest=/remote/file"
Explanation: Copies a file from the local machine to remote hosts.

73. ansible -m template
Deploy configuration files from templates.


		ansible all -m template -a "src=template.j2 dest=/etc/config"
Explanation: Uses a Jinja2 template to create a configuration file on remote hosts.

74. ansible -m fetch
Fetch files from remote hosts.


		ansible all -m fetch -a "src=/remote/file dest=/local/dir flat=yes"
Explanation: Downloads files from remote hosts to the local machine.

75. ansible -m lineinfile
Ensure a line is present in a file.


		ansible all -m lineinfile -a "path=/etc/hosts line='127.0.0.1 localhost'"
Explanation: Ensures that a specific line exists in the file.

76. ansible all -m command -a
Run a command with arguments.


		ansible all -m command -a "echo Hello World"
Explanation: Executes the command to print "Hello World" on all hosts.

77. ansible all -m user -a
Manage users and groups.


		ansible all -m user -a "name=newuser state=present"
Explanation: Creates a new user newuser on all managed nodes.

78. ansible all -m group -a
Manage groups.


		ansible all -m group -a "name=mygroup state=present"
Explanation: Creates a new group mygroup on all managed nodes.

79. ansible all -m authorized_key -a
Manage SSH authorized keys.


		ansible all -m authorized_key -a "user=someuser key='ssh-rsa AAA...'"
Explanation: Adds an SSH key for the specified user.

80. ansible all -m command -a
Run arbitrary commands.


		ansible all -m command -a "uname -r"
Explanation: Executes the command to get the kernel version on all hosts.

81. ansible all -m shell -a
Run shell commands.


		ansible all -m shell -a "cat /etc/os-release"
Explanation: Executes a shell command to display OS release information.

82. ansible all -m cron -a
Manage cron jobs.


		ansible all -m cron -a "name='backup' minute='0' hour='2' job='backup.sh'"
Explanation: Creates a cron job for daily backups at 2 AM.

83. ansible all -m systemd -a
Manage systemd services.


			ansible all -m systemd -a "name=nginx state=started"
Explanation: Ensures that the nginx service is running.

84. ansible all -m firewalld -a
Manage firewall rules.


		ansible all -m firewalld -a "service=http permanent=yes state=enabled"
Explanation: Enables the HTTP service in the firewall.

85. ansible all -m yum -a
Manage packages with YUM.


		ansible all -m yum -a "name=httpd state=present"
Explanation: Installs the httpd package on all Red Hat-based systems.

86. ansible all -m mount -a
Manage mounts.


		ansible all -m mount -a "path=/mnt/data src=/dev/sdb1 fstype=ext4 state=mounted"
Explanation: Mounts a filesystem at the specified path.

87. ansible all -m wait_for -a
Wait for a port to be open.


		ansible all -m wait_for -a "port=80 state=started timeout=10"
Explanation: Waits for port 80 to become available on all hosts.

88. ansible all -m unarchive -a
Unarchive files.


		ansible all -m unarchive -a "src=archive.tar.gz dest=/tmp"
Explanation: Extracts an archive on all managed nodes.

89. ansible all -m command -a
Run a command with arguments.


		ansible all -m command -a "df -h"
Explanation: Executes the command to display disk space usage.

90. ansible all -m shell -a
Run a shell command.

	
		ansible all -m shell -a "ls -la"
Explanation: Lists files in the current directory in detail.

91. ansible all -m git -a
Manage Git repositories.


		ansible all -m git -a "repo=https://github.com/user/repo.git dest=/path/to/repo"
Explanation: Clones a Git repository to the specified directory.

92. ansible all -m setup -a
Gather facts about the host.


		ansible all -m setup -a "filter=ansible_distribution"
Explanation: Collects specific facts about the operating system distribution.

93. ansible all -m user -a
Create a user account.


		ansible all -m user -a "name=myuser state=present"
Explanation: Creates a new user account myuser.

94. ansible all -m systemd -a
Manage systemd services.


		ansible all -m systemd -a "name=nginx state=stopped"
Explanation: Stops the nginx service on all hosts.

95. ansible all -m file -a
Manage file properties.


		ansible all -m file -a "path=/tmp/myfile state=touch"
Explanation: Touches a file, updating its timestamp.

96. ansible all -m debug -a
Display debug information.


		ansible all -m debug -a "var=ansible_hostname"
Explanation: Displays the hostname of the managed node.

97. ansible all -m fetch -a
Fetch files from remote nodes.


		ansible all -m fetch -a "src=/etc/passwd dest=/tmp/passwd"
Explanation: Downloads the /etc/passwd file from remote nodes.

98. ansible all -m shell -a
Run arbitrary shell commands.


		ansible all -m shell -a "echo Hello World > /tmp/hello.txt"
Explanation: Writes "Hello World" to a text file.

99. ansible all -m uri -a
Make HTTP requests.


		ansible all -m uri -a "url=http://example.com method=GET"
Explanation: Sends a GET request to the specified URL.

100. ansible all -m ping -a
Ping remote hosts.


		ansible all -m ping -a "data='pong'"
Explanation: Pings the hosts and expects a response.

---------------------------------------------------------------------------------------------------
