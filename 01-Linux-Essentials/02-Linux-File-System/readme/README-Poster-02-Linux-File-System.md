# Linux File System Poster

This poster explains the Linux file system from `/` root to important directories, commands, file types, permissions basics, troubleshooting, and real-world administration use cases.

## 📌 What This Poster Covers

- Linux file system hierarchy
- Root directory `/`
- Important system directories
- Common Linux file system commands
- File types
- Basic permissions
- Disk usage commands
- Real-world use cases
- Common mistakes
- Best practices
- Troubleshooting
- Interview questions

## 🧠 Key Learning Points

- Linux does not use drive letters like `C:` or `D:`.
- Everything starts from `/`.
- Everything in Linux is treated like a file.
- System configuration files are usually stored in `/etc`.
- User home directories are stored in `/home`.
- Logs and variable data are stored in `/var`.
- Temporary files are commonly stored in `/tmp`.
- Virtual system information is available in `/proc` and `/sys`.

## 🛠️ Important Commands

```bash
pwd
ls
ls -l
ls -la
cd
mkdir
touch
cp
mv
rm
rmdir
find
du
df
file
stat
```

## 💼 Real-World Use Cases

### Check disk usage

```bash
df -h
```

### Find large directories

```bash
du -ah / | sort -rh | head -n 10
```

### Search for a configuration file

```bash
find /etc -name "sshd_config" 2>/dev/null
```

### Check log directory size

```bash
du -sh /var/log
```

### List mounted file systems

```bash
df -h
```

## ⚠️ Common Mistakes

- Deleting files from `/bin` or `/sbin`
- Editing `/etc` files without backup
- Removing active files from `/tmp`
- Mounting devices in the wrong location
- Ignoring disk usage until the server becomes full

## ✅ Best Practices

- Always back up important configuration files before editing.
- Monitor disk usage regularly.
- Follow Linux Filesystem Hierarchy Standard concepts.
- Use `du` and `df` to troubleshoot storage issues.
- Be careful when using `rm -rf`.

## ❓ Interview Questions

1. What is the root directory in Linux?
2. What is the difference between `/bin` and `/sbin`?
3. Where are user home directories stored?
4. What is the purpose of `/proc`?
5. What is the difference between `/mnt` and `/media`?
6. How do you check disk usage in Linux?
7. How do you find large files or directories?
8. What is stored inside `/etc`?
9. Why is everything considered a file in Linux?
10. What are the risks of editing system directories without backup?

## 📂 Part of This Series

This poster is part of the **Linux & DevOps Visual Study Library**.

| # | Topic |
|---|-------|
| 01 | Linux Search & Text Processing |
| 02 | Linux File System |
| 03 | File Permissions & ACL |
| 04 | Users & Groups |
| 05 | Process Management |

Happy Learning. Keep practicing Linux.
