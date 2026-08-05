# MODULE 2

> Linux CML
    .whoami: Tells who u are on the system
    
    .echo: Output text which is provided
    
    .ls: lists what's in the folder
    
    .cd: Changes directory
    
    .pwd: print working directory
    
    .grep: Searches inside a file for texts(grep "text" file.txt)
    
    .find: Finds the file you want(find -name filename.txt)

    .&: Runs a command in the background so we can use other commands.

    .&&: Runs two commands bit waits for the first one to complete then the second one will run.

    .man: (man ls) will give description of the ls commands. Similarly we can know about the other commands.

    .touch: Creats a file

    .mkdir: creates folder

    .cp: copy a file or folder

    .mv: move a file or folder

    .rm: remove a file or folder

    .file: determine the type of file.

    .ls -lh: list permission of the files in the directory.

    .su: Switch User.

    ./etc: This root directory is one of the most important root directories on your system. The etc folder (short for etcetera) is a commonplace location to store system files that are used by your operating system.

    ./var: The "/var" directory, with "var" being short for variable data,  is one of the main root folders found on a Linux install. This folder stores data that is frequently accessed or written by services or applications running on the system.

    ./root: Unlike the /home directory, the /root folder is actually the home for the "root" system user. There isn't anything more to this folder other than just understanding that this is the home directory for the "root" user. 
    `   
    ./tmp: This is a unique root directory found on a Linux install. Short for "temporary", the /tmp directory is volatile and is used to store data that is only needed to be accessed once or twice. Similar to the memory on your computer, once the computer is restarted, the contents of this folder are cleared out.

    .wget: This command allows us to download files from the web via HTTP -- as if you were accessing the file in your browser.
        eg: wget http://192.24.13.4/file.txt

    .python3 -m http.server: Python helpfully provides a lightweight and easy-to-use module called "HTTPServer". This module turns your computer into a quick and easy web server that you can use to serve your own files 

    .scp:   Copy files & directories from your current system to a remote system 
                        scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
            Copy files & directories from a remote system to your current system
                        scp ubuntu@192.168.1.30:/home/ubuntu/documents.txt notes.txt 
            Uses SSH Protocol which provides authentication and encryption.
    
    ./nano: Opens a text editor to write text.


        > SSH:
    stands for secure shell scripting allows us to remotely execute commands on another device remotely. Data sent is encrypted when in the network.

    eg: ssh tryhackme@ip address

        >VIM: An advanced text editor
            .let you create your own controls.
            .Syntax highlighting.
            .Works on every terminal.

# Linux Processes – Quick Notes

## What is a Process?

* A **process** is a running program.
* Managed by the **kernel**.
* Every process has a unique **PID (Process ID)**.
* PIDs increase as new processes start.

## Viewing Processes

```bash
ps
```

* Shows processes running in your current session.

```bash
ps aux
```

* Shows **all** processes (including system and other users).

```bash
top
```

* Displays real-time process statistics (CPU, RAM, PID, etc.).
* Refreshes automatically.

## Managing Processes

Kill a process:

```bash
kill <PID>
```

Common Signals:

* **SIGTERM** - Gracefully terminate (allows cleanup).
* **SIGKILL** - Force kill immediately.
* **SIGSTOP** - Pause/Suspend a process.

## Process Startup

* **PID 0**: First kernel process during boot.
* **systemd (init)**: Starts after boot and manages system services.
* Most programs are **child processes** of `systemd`.

## Managing Services (systemctl)

Format:

```bash
systemctl <option> <service>
```

Common commands:

```bash
systemctl start apache2
systemctl stop apache2
systemctl enable apache2
systemctl disable apache2
systemctl status apache2
```

Options:

* `start`
* `stop`
* `enable` (start on boot)
* `disable`
* `status` 

## Foreground & Background Processes

**Foreground:** Runs in the terminal and occupies it.

**Background:** Runs while you continue using the terminal.

Run in background:

```bash
command &
```

Pause/Background current process:

```text
Ctrl + Z
```

Bring process back to foreground:

```bash
fg
```

## Important Commands

```bash
ps          # Current session processes
ps aux      # All running processes
top         # Live process monitor
kill PID    # Terminate process
systemctl start <service>
systemctl stop <service>
systemctl enable <service>
systemctl disable <service>
systemctl status <service>
command &   # Run in background
fg          # Bring background process to foreground
Ctrl + Z    # Suspend/background current process
```


# Linux Cron & Crontab – Quick Notes

## What is Cron?

* **Cron** is a service that runs scheduled tasks automatically.
* It starts during system boot.
* It executes tasks defined in a **crontab**.

## What is Crontab?

* A **crontab** is a file that stores scheduled jobs (cron jobs).
* Each job is written on a single line.

## Crontab Format

```text
MIN HOUR DOM MON DOW CMD
```

| Field | Description                     |
| ----- | ------------------------------- |
| MIN   | Minute (0–59)                   |
| HOUR  | Hour (0–23)                     |
| DOM   | Day of Month (1–31)             |
| MON   | Month (1–12)                    |
| DOW   | Day of Week (0–7, 0/7 = Sunday) |
| CMD   | Command to execute              |

## Wildcards

* `*` → Any value (every minute, hour, day, etc.)

Example:

```text
0 */12 * * * cp -R /home/user/Documents /var/backups/
```

* Runs **every 12 hours** at **minute 0**.

## Special Cron Keyword

```text
@reboot
```

* Runs the command **once every time the system starts**.

## Managing Crontabs

Edit your crontab:

```bash
crontab -e
```

View your crontab:

```bash
crontab -l
```

## Important Commands

```bash
crontab -e    # Edit cron jobs
crontab -l    # List cron jobs
```

# Linux Packages & Repositories – Quick Notes

## Package Repository

* A **repository (repo)** is an online storage of software packages.
* Ubuntu uses **APT (Advanced Package Tool)** to manage packages.
* You can use **official** or **third-party/community** repositories.

## APT Commands

Update package list:

```bash
sudo apt update
```

Install software:

```bash
sudo apt install <package>
```

Remove software:

```bash
sudo apt remove <package>
```

## Adding a Repository

Add a repository:

```bash
sudo add-apt-repository <repository>
```

Or manually:

1. Add the **GPG key** (verifies software authenticity).
2. Add the repository to `/etc/apt/sources.list.d/`.
3. Run:

```bash
sudo apt update
```

4. Install the package:

```bash
sudo apt install <package>
```

## Removing a Repository

Remove repository:

```bash
sudo add-apt-repository --remove <repository>
```

Or delete its file from:

```text
/etc/apt/sources.list.d/
```

Then remove the package:

```bash
sudo apt remove <package>
```

## Important Commands

```bash
sudo apt update
sudo apt install <package>
sudo apt remove <package>
sudo add-apt-repository <repo>
sudo add-apt-repository --remove <repo>
```

# Linux Log Files – Quick Notes

## What are Log Files?

* Log files store information about **system activities, applications, and services**.
* Located in:

```text
/var/log
```

## Common Apache Logs

* **access.log** → Records every request made to the web server.
* **error.log** → Records server errors and issues.

## Common Commands

Go to log directory:

```bash
cd /var/log
```

View Apache logs:

```bash
cd /var/log/apache2
ls
sudo cat access.log
sudo cat error.log
```

## Apache Access Log

A typical entry:

```text
IP_ADDRESS - - [Date/Time] "GET /file HTTP/1.1" Status Size
```

* **1st field** → Client IP address.
* **GET /file** → File/page requested.
* **Status Code** → HTTP response (e.g., 200 = OK, 404 = Not Found).

## Important Logs

* `/var/log/apache2/access.log`
* `/var/log/apache2/error.log`
* `/var/log/auth.log` → Authentication/Login logs.
* `/var/log/syslog` → General system logs.

