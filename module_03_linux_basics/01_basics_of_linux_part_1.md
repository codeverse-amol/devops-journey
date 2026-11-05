# Module 3 – Linux Basics: Part 1 (Notes, fact-checked)

## 1. What is Linux?

- **Linux is a kernel, not a complete OS.**
- **Kernel** = program that allocates and controls hardware resources (CPU, memory, disk) and bridges hardware ↔ software.
- **Linux distribution** = Linux kernel + GNU tools/OS → properly called **GNU/Linux**.

## 2. History

| Year | Event |
|------|-------|
| 1969 | **Unix** created at AT&T Bell Labs by **Ken Thompson and Dennis Ritchie** (after Bell Labs left the Multics project) |
| ~1972 | Unix rewritten in **C** (earliest versions were in assembly) |
| 1983–84 | GNU project started by Richard Stallman |
| 1991 | **Linus Torvalds**, a Helsinki student, starts the Linux kernel; first release Sept 1991 (version 0.01) |
| 1994 | Kernel 1.0 released |

- Unix goals: **simplicity, recyclable code, written in C** (portable, unlike assembly).
- The name "Linux" is commonly explained as Linus + Unix.
- The slide's "12,000 users in 1993" figure could not be verified. Treat it as the lecturer's number.

## 3. Linux is Free (Free Software)

- Anyone can download, compile and study the source.
- Free = "free as in freedom", not only free of cost.
- The GNU **four essential freedoms**:
  0. Run the program for any purpose.
  1. Study how it works and change it (needs source code).
  2. Redistribute copies.
  3. Distribute your modified versions.
- The PDF says "four freedoms" but lists only three (it merges 2 and 3).

## 4. Kernel Versioning

- Format: **Major.Minor.Patchlevel**
- **Old scheme (up to 2.4/2.5):** odd minor = development, even minor = stable. E.g. `2.4.20` stable, `2.5.67` development.
- **Ended in Dec 2003** with 2.6.0. Since then every release is stable and development is time-based.
- Version 3.0 came after 2.6.39. The number change is arbitrary and doesn't signal a major rewrite.
- New releases come roughly every **9–10 weeks**.
- **Exam tip:** if the question is based on this lecture, answer with the odd/even rule. In real life, it no longer applies.

## 5. Kernel Development

- Led by Linus Torvalds.
- The slide says "a few hundred developers". That is outdated. Roughly **1,000+ developers contribute to each release**, and 5,000+ over a 15-month period (Linux Foundation, 2016). Over 13,500 have contributed in total.

## 6. GNU GPL (General Public License)

- Created by the Free Software Foundation to keep GNU software free via **copyleft**.
- Modified versions you **distribute** must also be licensed under the GPL, and the **source code must be made available**.
- Private or internal modifications **don't** have to be released. The lecture slide oversimplifies this.
- Prevents proprietary versions of GPL code.
- **Linux is released under the GPL.**
- Criticised as restrictive (per the slide).

## 7. Why Use Linux?

- **Servers:** performance, price, stability.
- **Developers:** many free tools (compilers, debuggers, libraries); scriptable CLI.
- **Desktop:** it's fun.
- **Career:** cloud, DevOps, sysadmin.

## 8. Advantages

- **Free** (no license fees, free updates).
- Learning Linux means learning **UNIX** concepts.
- **Open-source auditability** → faster fixes for vulnerabilities.
- **Active community** plus corporate support available.

## 9. Disadvantages

- Steeper learning curve (command line) than Windows.
- Manual hardware configuration in some cases; some hardware unsupported.
- Some commercial software (Adobe, MS Office) unavailable; fewer AAA games.
- The slide's "lacks automated installation tools" is **outdated**. Modern distros have graphical installers.

## 10. Famous Distros

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
- **CentOS Linux 8 reached end of life on 31 Dec 2021.**
- **CentOS Linux 7 reached end of life on 30 Jun 2024.**
- It was replaced by **CentOS Stream**, which is upstream of RHEL, not a drop-in replacement.
- RHEL-compatible alternatives are **Rocky Linux** and **AlmaLinux**.
- It still appears on the lecture slide, so know it for the exam.

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
| `/usr` | User programs and data (secondary hierarchy) |
| `/var` | Variable data: logs, spools, caches |

- The lecture slide says `/etc` is "can't think of any other place to put it". That is a joke. It's for configuration.

## 12. Basic Commands

*These are standard Linux commands and were not re-checked online.*

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

> The lecture links a command cheat sheet (GitHub gist by Talha-Altair, on the "Basic Linux Commands for All Users" slide).

## 13. Quick Revision

- Linux = **kernel**; GNU/Linux = full OS.
- **Unix 1969 → Linux 1991** (Linus Torvalds).
- Licensed under the **GPL (copyleft)**.
- Filesystem root is **`/`**.
- Odd/even kernel rule is historical (ended 2003).
- Strengths: free, stable, secure, server-dominant. Weakness: learning curve.

## Not verified online

- "Linux/UNIX is the largest server platform."
- The 12,000-users-in-1993 figure.
- Basic command descriptions (standard knowledge).

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
- [Red Hat – FHS overview](https://mirror.apps.cam.ac.uk/pub/doc/redhat/redhat9/rhl-rg-en-9/s1-filesystem-fhs.html)
- [History of Linux – Wikipedia](https://en.wikipedia.org/wiki/History_of_Linux)