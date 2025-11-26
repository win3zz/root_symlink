# Symlink Test Repo

This repository contains a **single symbolic link** used for testing how symlinks behave when cloned by different tools, environments, and platforms.

The purpose of this repository is solely to observe:

- How symlinks are handled when cloned from Git
- How various systems treat symlinks pointing outside the repository directory
- Whether symlink metadata is preserved across platforms

## Structure

`root  →  /`

The `root` entry is simply a symbolic link referencing the system root (`/`).  

## Creation Commands

```sh
mkdir myproject
ln -s / myproject/root
cd myproject
git init
git add root
git commit -m "add symlink"
git branch -M main
git remote add origin <your_repo_url>
git push -u origin main
```

## Usage Example

```console
root@win3zz:/tmp# git clone https://github.com/win3zz/root_symlink.git
Cloning into 'root_symlink'...
remote: Enumerating objects: 10, done.
remote: Counting objects: 100% (10/10), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 10 (delta 0), reused 3 (delta 0), pack-reused 0 (from 0)
Receiving objects: 100% (10/10), done.
root@win3zz:/tmp# cat root_symlink/root/etc/passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
[...]
```

> [!NOTE]
> Research and testing only, not designed for malicious use

## Author
Bipin ([win3zz](https://medium.com/@win3zz))
