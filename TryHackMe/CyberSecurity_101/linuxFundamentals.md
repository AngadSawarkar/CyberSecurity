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


