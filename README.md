# Symlink Test Repo

This repository contains a **single symbolic link** used for testing how symlinks behave when cloned by different tools, environments, and platforms.

The purpose of this repository is solely to observe:

- How symlinks are handled when cloned from Git
- How various systems treat symlinks pointing outside the repository directory
- Whether symlink metadata is preserved across platforms

## Structure

`root  →  /`

The `root` entry is simply a symbolic link referencing the system root (`/`).  

## Creation Command

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

> [!NOTE]
> Research and testing only, not designed for malicious use

## Author
Bipin ([win3zz](https://medium.com/@win3zz))
