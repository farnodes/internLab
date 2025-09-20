📝 Basic Linux Topics

1. Introduction to Linux

```bash
What is Linux?: Open-source operating system based on Unix.

Linux Distributions: Ubuntu, CentOS, Debian, Fedora, etc.

Linux vs Windows vs Unix: Differences in architecture, file system, and permissions.

File System Hierarchy: /, /home, /etc, /var, /tmp, /root, /dev, etc.
```
2. Basic Commands

```bash
pwd – Show current directory.

ls – List files and directories.

cd – Change directory.

mkdir / rmdir – Create/remove directories.

touch – Create empty files.

cp / mv / rm – Copy, move, remove files.

cat, less, more, head, tail – View file contents.
```
3. File Permissions & Ownership

```bash
Permissions: Read (r), Write (w), Execute (x).

chmod – Change file permissions.

chown / chgrp – Change file owner/group.
```

4. Links in Linux

```bash
Hard Links – Point to the same inode.

Soft (Symbolic) Links – Shortcut or reference to another file.
```

5. User & Group Management

```bash
whoami, id – Identify current user and groups.

useradd, usermod, userdel – Add/modify/delete users.

groupadd, groupdel – Add/remove groups.

passwd – Change user password.
```

6. Navigation & File System Management

```bash
Absolute vs Relative Paths.

Understanding Linux directory structure (/, /home, /etc, /var, /tmp, /root, /dev).
```

7. Input/Output Redirection

```bash
> – Redirect output to a file (overwrite).

>> – Redirect output to a file (append).

< – Redirect input from a file.

| – Pipe output of one command to another.

tee – Redirect output to both file and console.
```

8. Process Management

```bash
ps, top, htop – View running processes.

kill, killall – Terminate processes.

jobs, fg, bg – Manage background/foreground jobs.
```

9. Package Management

```bash
Debian-based: apt, dpkg.

RedHat-based: yum, dnf, rpm.
```

10. Disk Management

```bash
df – Show disk space usage.

du – Show directory size.

mount / umount – Mount/unmount drives.

fsck – File system check.
```

11. Archiving & Compression

```bash
tar – Archive files.

gzip / gunzip – Compress/uncompress files.

zip / unzip – Compress/uncompress files.
```

12. Networking Basics

```bash
ifconfig / ip – View network interfaces.

ping – Test connectivity.

netstat / ss – Show network connections.

scp, ssh – Securely transfer files or login remotely.

wget, curl – Download files from the web.
```

13. Editors in Linux

```bash
nano, vi / vim – Text editors.
```

14. Crontab & Scheduling

```bash
cron – Schedule recurring jobs.

at – Schedule one-time jobs.
```

15. Log Files & Monitoring

```bash
Logs are usually in /var/log.

tail -f /var/log/syslog – Monitor logs in real-time.
```

16. Shell Basics

```bash
Types of shells: bash, sh, zsh.

Environment variables: env, export.

Aliases – Shortcuts for commands.
```
