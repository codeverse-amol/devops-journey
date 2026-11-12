# Module 3 – Linux Basics: Part 1

## 1. What is Linux?

- **Linux is a kernel, not a complete operating system.**
- **Kernel** = the core program that allocates and controls hardware resources (CPU, memory, disk) and acts as the bridge between hardware and software.
- **Linux distribution (distro)** = Linux kernel + GNU tools and other software. Strictly called **GNU/Linux**.

## 2. History

| Year | Event |
|------|-------|
| 1969 | **Unix** created at AT&T Bell Labs by **Ken Thompson and Dennis Ritchie** |
| ~1972 | Unix rewritten in **C** (earliest versions were in assembly) |
| 1983–84 | GNU project started by Richard Stallman |
| 1991 | **Linus Torvalds**, a Helsinki student, starts the Linux kernel (first release Sept 1991, version 0.01) |
| 1994 | Kernel 1.0 released |

- Unix design goals: **simplicity, reusable code, portability (written in C)**.
- "Linux" is commonly explained as Linus + Unix.

## 3. Linux is Free (Free Software)

- Anyone can download, compile, study and modify the source code.
- "Free" means **freedom**, not only zero cost.
- The four essential freedoms (GNU):
  0. Run the program for any purpose.
  1. Study how it works and change it (needs source code).
  2. Redistribute copies.
  3. Distribute your modified versions.

## 4. Kernel Versioning

- Format: **Major.Minor.Patchlevel** (e.g. `2.4.20`).
- **Old scheme (up to 2.4/2.5):** odd minor = development, even minor = stable. E.g. `2.4.x` stable, `2.5.x` development.
- **Ended in Dec 2003** with 2.6.0. Since then every release is stable and development is time-based.
- 3.0 followed 2.6.39. The change was arbitrary, not a major rewrite.
- New kernel releases come roughly every **9–10 weeks**.

## 5. Kernel Development

- Led by Linus Torvalds.
- Roughly **1,000+ developers contribute to each release**. Over 5,000 contributed in a single 15-month period (Linux Foundation report, 2016).

## 6. GNU GPL (General Public License)

- Created by the Free Software Foundation to keep software free via **copyleft**.
- If you **distribute** a modified version, it must also be under the GPL and the **source code must be made available**.
- Private or internal modifications don't have to be released.
- Prevents proprietary versions of GPL code.
- **Linux is released under the GPL.**
- Critics call it restrictive, since it forces derived works to stay open.

## 7. Why Use Linux?

- **Servers:** performance, stability, low cost.
- **Developers:** many free tools (compilers, debuggers, libraries) and a scriptable command line.
- **Learning:** builds Unix and operating system fundamentals.
- **Career:** cloud, DevOps and sysadmin roles.

## 8. Advantages

- **Free**: no license fees, free updates.
- **Open-source auditability**: vulnerabilities found and fixed faster.
- **Stable and secure**: can run for long periods without reboot.
- **Large community** plus commercial support (e.g. Red Hat, Canonical).

## 9. Disadvantages

- Steeper learning curve (command line) than Windows.
- Some hardware or drivers may need manual setup or be unsupported.
- Some commercial software (Adobe, MS Office) is unavailable natively; open-source alternatives exist.
- Fewer AAA games than Windows.

## 10. Popular Distros

| Distro | Known for |
|--------|-----------|
| Ubuntu | Beginner-friendly |
| Debian | Stability |
| Kali | Ethical hacking / security |
| RHEL | Enterprise reliability |
| CentOS | See note below |
| Fedora | Latest features |
| Arch | Advanced users |
| Alpine | Lightweight, containers |

**CentOS note:**
- **CentOS Linux 8 reached end of life on 31 Dec 2021**, and **CentOS Linux 7 on 30 Jun 2024**.
- It was replaced by **CentOS Stream**, which sits upstream of RHEL and is not a drop-in replacement.
- RHEL-compatible alternatives are **Rocky Linux** and **AlmaLinux**.

## 11. File System Hierarchy (FHS)

- Single tree starting at root **`/`**; **no drive letters** (unlike Windows).

| Directory | Purpose |
|-----------|---------|
| `/boot` | Kernel and boot files |
| `/bin` | Essential command binaries |
| `/dev` | Device files |
| `/etc` | Host-specific system configuration |
| `/home` | Users' home directories |
| `/lib` | System libraries |
| `/mnt` | Temporarily mounted filesystems |
| `/proc` | Virtual filesystem: kernel and process info |
| `/root` | Root user's home |
| `/sbin` | Essential system binaries (admin) |
| `/usr` | User programs and data |
| `/var` | Variable data: logs, spools, caches |

## 12. Basic Commands

**Navigation and files**

| Command | Use |
|---------|-----|
| `ls` | List files |
| `cd` | Change directory |
| `pwd` | Show current path |
| `mkdir` | Create folder |
| `touch` | Create empty file |
| `cp` | Copy |
| `mv` | Move / rename |
| `rm` | Delete |

**Permissions**

- `r` read, `w` write, `x` execute, applied to **owner, group, others**.
- `chmod` changes permissions; `chown` changes ownership.

**Package managers**

- `apt` → Debian/Ubuntu
- `dnf` (older: `yum`) → Red Hat family
- `pacman` → Arch

**System info**

| Command | Shows |
|---------|-------|
| `uname -a` | Kernel info |
| `df -h` | Disk usage |
| `free -h` | Memory (RAM + swap) |
| `top`, `ps aux` | Running processes |

## 13. Quick Revision

- Linux = **kernel**; GNU/Linux = full OS.
- **Unix 1969 → Linux 1991** (Linus Torvalds).
- Licensed under the **GPL (copyleft)**.
- Filesystem root is **`/`**.
- Odd/even kernel numbering is historical (ended 2003).
- Strengths: free, stable, secure, widely used on servers. Weakness: learning curve.

## Sources

- [LINFO – Kernel Version Numbering](https://linfo.org/kernel_version_numbering.html)
- [LWN – odd/even practice ended with 2.6](https://lwn.net/Articles/822909/)
- [Linux Foundation – kernel version numbering](https://www.linuxfoundation.org/blog/the-voices-in-linus-head-say-time-for-2-8/)
- [Linux Foundation 2016 report (via ADT Mag)](https://adtmag.com/articles/2016/08/23/linux-kernel-development.aspx)
- [GNU – four essential freedoms](https://www.gnu.org/p/)
- [GNU GPL FAQ](https://ftp.gwdg.de/pub/gnu/www/licenses/gpl-faq.html)
- [Choose a License – GPLv2](https://choosealicense.com/licenses/gpl-2.0/)
- [CentOS Linux & CentOS Stream timeline](https://www.stackscale.com/blog/centos-linux/)
- [CentOS EOL – DEV Community](https://dev.to/endoflifeai/centos-is-dead-centos-7-eol-june-2024-centos-8-eol-dec-2021-your-migration-options-4ppn)
- [Filesystem Hierarchy Standard](https://specifications.freedesktop.org/fhs/latest-single)
- [History of Linux – Wikipedia](https://en.wikipedia.org/wiki/History_of_Linux)