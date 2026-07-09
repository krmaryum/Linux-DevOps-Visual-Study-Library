# Linux File System Study Notes

## 1. What is the Linux File System?

The Linux file system is a hierarchical tree structure that starts from the root directory `/`.

Unlike Windows, Linux does not use drive letters such as `C:` or `D:`. Everything begins from `/`.

In Linux, everything is treated like a file:

- Regular files
- Directories
- Devices
- Processes
- Sockets
- Pipes

## 2. Why is it important?

Understanding the Linux file system helps you:

- Navigate the system confidently
- Find configuration files
- Troubleshoot logs and services
- Manage users and permissions
- Monitor disk usage
- Understand how Linux organizes data

## 3. Linux Directory Quick Reference

| Directory | Purpose |
|---|---|
| `/` | Root directory. The base of the entire file system. |
| `/bin` | Essential user commands like `ls`, `cp`, `mv`, `cat`. |
| `/sbin` | System administration commands like `reboot`, `fsck`, `shutdown`. |
| `/boot` | Boot loader and kernel files. |
| `/dev` | Device files such as disks, terminals, random devices. |
| `/etc` | System-wide configuration files. |
| `/home` | User home directories. |
| `/lib` | Shared libraries required by system binaries. |
| `/lib64` | 64-bit shared libraries. |
| `/media` | Mount point for removable media. |
| `/mnt` | Temporary mount point. |
| `/opt` | Optional third-party software. |
| `/proc` | Virtual file system for process and kernel information. |
| `/root` | Root user's home directory. |
| `/run` | Runtime data since boot. |
| `/srv` | Data for services provided by the system. |
| `/sys` | System and hardware information. |
| `/tmp` | Temporary files. Usually cleared on reboot. |
| `/usr` | User programs and shared data. |
| `/var` | Variable data such as logs, cache, spool, and mail. |

## 4. Common Commands

### Print current directory

```bash
pwd
```

### List files

```bash
ls
ls -l
ls -la
```

### Change directory

```bash
cd /etc
cd ~
cd ..
```

### Create files and directories

```bash
touch file.txt
mkdir myfolder
```

### Copy, move, and remove

```bash
cp file1 file2
mv oldname newname
rm file.txt
rmdir emptydir
```

### Find files

```bash
find /etc -name "sshd_config" 2>/dev/null
```

### Check disk space

```bash
df -h
```

### Check directory size

```bash
du -sh /var/log
```

## 5. File Types in Linux

When you run:

```bash
ls -l
```

The first character tells you the file type.

| Symbol | File Type |
|---|---|
| `-` | Regular file |
| `d` | Directory |
| `l` | Symbolic link |
| `c` | Character device |
| `b` | Block device |
| `p` | Named pipe |
| `s` | Socket |

## 6. Real-World Examples

### Find where SSH config is located

```bash
find / -name "sshd_config" 2>/dev/null
```

### Check large directories

```bash
du -ah / | sort -rh | head -n 10
```

### Monitor log folder size

```bash
du -sh /var/log
```

### Check mounted file systems

```bash
df -h
```

### Check file details

```bash
stat file.txt
```

### Identify file type

```bash
file script.sh
```

## 7. Common Mistakes

| Mistake | Why it is dangerous |
|---|---|
| Deleting files from `/bin` or `/sbin` | Can break important commands. |
| Editing `/etc` files without backup | Can break services or login access. |
| Removing files from `/tmp` carelessly | Some apps may be using temporary files. |
| Filling up `/var` | Logs can consume disk and crash services. |
| Using `rm -rf /` | Extremely dangerous and destructive. |

## 8. Best Practices

- Always back up config files before editing.
- Use `df -h` and `du -sh` regularly.
- Keep `/var/log` monitored.
- Avoid working as root unless required.
- Be careful with `rm -rf`.
- Learn the purpose of each important directory.
- Follow the Linux Filesystem Hierarchy Standard.

## 9. Troubleshooting

| Problem | Command |
|---|---|
| Disk full | `df -h` |
| Large directory | `du -sh /*` |
| File not found | `find / -name "filename" 2>/dev/null` |
| Permission issue | `ls -l filename` |
| Unknown file type | `file filename` |
| Check file metadata | `stat filename` |

## 10. Summary

The Linux file system is the foundation of Linux administration.

If you understand where files are stored and why, you can troubleshoot faster, manage systems better, and become more confident as a Linux or DevOps engineer.
