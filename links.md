<!-- Last updated: 2026-03-11 | Total links: 51 | Pro tip: ctrl+F 'COBOL' for 80s nostalgia or 'sysctl' for firewall wins. -->

# Link Dump — Everything Tom Is Learning
*Curated by ResearchBuddy. Every link tied to a real session topic.*

---

## 1. Git — Remote Setup & Pushing to GitHub

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | About Remote Repositories | https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories | GitHub's own explanation of SSH vs HTTPS remotes and how they work. |
| [OFFICIAL] | Managing Remote Repositories | https://docs.github.com/en/get-started/getting-started-with-git/managing-remote-repositories | How to add, change, and switch remote URLs with `git remote`. |
| [OFFICIAL] | Error: Permission denied (publickey) | https://docs.github.com/en/authentication/troubleshooting-ssh/error-permission-denied-publickey | Fix the most common SSH push failure — step by step from GitHub. |
| [TUTORIAL] | Push from Linux to GitHub using SSH Key | https://www.geeksforgeeks.org/git/push-codes-from-linux-ubuntu-to-github-using-ssh-key/ | Linux-specific walkthrough: key generation, GitHub setup, first push. |
| [TUTORIAL] | How to Use an SSH Key with GitHub | https://www.ionos.com/digitalguide/websites/web-development/ssh-key-with-github/ | Practical SSH key setup guide from zero to first successful push. |
| [VIDEO] | Git SSH GitHub Push Tutorials | https://www.youtube.com/results?search_query=git+ssh+github+push+tutorial | Search YouTube for visual walkthroughs of SSH + git push. |

---

## 2. UFW Firewall — Hardening, Rate Limiting, Tailscale

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Use UFW to Lock Down a Server — Tailscale Docs | https://tailscale.com/kb/1077/secure-server-ubuntu | Official Tailscale guide: block all traffic except through your tailnet. |
| [OFFICIAL] | UFW Community Help Wiki — Ubuntu | https://help.ubuntu.com/community/UFW | Ubuntu's reference for all UFW syntax and common rules. |
| [TUTORIAL] | Set Up a Firewall with UFW on Ubuntu — DigitalOcean | https://www.digitalocean.com/community/tutorials/how-to-set-up-a-firewall-with-ufw-on-ubuntu | The most widely referenced beginner UFW tutorial. |
| [TUTORIAL] | UFW Essentials: Common Firewall Rules — DigitalOcean | https://www.digitalocean.com/community/tutorials/ufw-essentials-common-firewall-rules-and-commands | Reference for `ufw limit`, rate limiting, interface-specific rules. |
| [BLOG] | VPS Fortress with Tailscale and UFW — DEV Community | https://dev.to/binsarjr/turn-your-vps-into-an-impenetrable-fortress-how-to-make-your-public-server-private-using-tailscale-and-ufw-3841 | Hands-on: make a server reachable only through Tailscale using UFW. |
| [BLOG] | Restrict SSH Access Using Tailscale and UFW | https://supun.io/tailscale-ssh-restrict | Real-world tutorial with caveats to avoid getting locked out. |
| [VIDEO] | UFW Complete Guide — HackerSploit | https://www.youtube.com/results?search_query=UFW+complete+guide+hackersploit+linux+firewall | HackerSploit's widely recommended UFW series on YouTube. |

---

## 3. sysctl — Kernel Hardening

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | sysctl.conf Security Hardening — nixCraft | https://www.cyberciti.biz/faq/linux-kernel-etcsysctl-conf-security-hardening/ | Comprehensive list of kernel parameters for network, fs, and memory hardening. |
| [TUTORIAL] | Hardening the Linux Kernel with Sysctl — Reintech | https://reintech.io/blog/hardening-linux-kernel-sysctl-debian-12 | Step-by-step tutorial applying sysctl hardening on a Debian 12 server. |
| [TUTORIAL] | Linux Hardening with Sysctl Settings — Linux Audit | https://linux-audit.com/system-hardening/linux-hardening-with-sysctl/ | Explains what each setting protects against in plain English. |
| [BLOG] | Advanced Sysctl Security Techniques — CalCom | https://calcomsoftware.com/sysctl-configuration-hardening/ | Covers kernel pointers, IPv6, ASLR and advanced parameters. |
| [BLOG] | How-To-Secure-A-Linux-Server: sysctl Reference — GitHub | https://github.com/imthenachoman/How-To-Secure-A-Linux-Server/blob/master/linux-kernel-sysctl-hardening.md | Community-maintained annotated sysctl parameter reference. |
| [VIDEO] | Linux Kernel sysctl Hardening Tutorials | https://www.youtube.com/results?search_query=linux+sysctl+kernel+hardening+security+tutorial | YouTube search for sysctl hardening video walkthroughs. |

---

## 4. SSH Daemon Hardening — sshd_config, Key-Only Auth

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | sshd_config(5) — Linux Man Page | https://man7.org/linux/man-pages/man5/sshd_config.5.html | Every sshd_config directive explained — the authoritative reference. |
| [OFFICIAL] | SSH Hardening Guides — ssh-audit.com | https://www.sshaudit.com/hardening_guides.html | Tool-backed hardening with exact config lines per distro. |
| [TUTORIAL] | Harden OpenSSH on Ubuntu — DigitalOcean | https://www.digitalocean.com/community/tutorials/how-to-harden-openssh-on-ubuntu-20-04 | Step-by-step: disable passwords, restrict root, enable key-only. |
| [TUTORIAL] | SSH Hardening Best Practices — Linuxize | https://linuxize.com/post/ssh-hardening-best-practices/ | Concise, practical guide — the most impactful sshd_config changes. |
| [BLOG] | OpenSSH Security and Hardening — Linux Audit | https://linux-audit.com/ssh/audit-and-harden-your-ssh-configuration/ | Auditing an existing SSH config for weaknesses, then fixing them. |
| [BLOG] | Disable SSH Password Login on Linux — nixCraft | https://www.cyberciti.biz/faq/how-to-disable-ssh-password-login-on-linux/ | Focused tutorial: `PasswordAuthentication no` without locking yourself out. |
| [VIDEO] | SSH Hardening sshd_config Tutorials | https://www.youtube.com/results?search_query=ssh+hardening+sshd_config+linux+tutorial | YouTube search for SSH hardening video tutorials. |

---

## 5. Bash Scripting — Best Practices & Error Handling

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [TUTORIAL] | How to Use set and pipefail in Bash — How-To Geek | https://www.howtogeek.com/782514/how-to-use-set-and-pipefail-in-bash-scripts-on-linux/ | Beginner-friendly breakdown of every flag in `set -euo pipefail`. |
| [TUTORIAL] | Writing Safe Shell Scripts — MIT SIPB | https://sipb.mit.edu/doc/safe-shell/ | MIT's concise authoritative guide on defensive Bash scripting. |
| [BLOG] | Safer Bash Scripts with set -euxo pipefail — vaneyckt.io | https://vaneyckt.io/posts/safer_bash_scripts_with_set_euxo_pipefail/ | Walk-through of every flag, caveats, and `|| true` patterns. |
| [BLOG] | Make Bash Safe with set -euxo pipefail — LinuxTect | https://linuxtect.com/make-bash-shell-safe-with-set-euxo-pipefail/ | Annotated code examples showing each flag's real-world effect. |
| [Q&A] | set -e -u -o -x pipefail Explained — GitHub Gist | https://gist.github.com/mohanpedala/1e2ff5661761d3abd0385e8223e16425 | Highly referenced community gist — all flags, concise explanations. |
| [VIDEO] | Bash Error Handling set -euo pipefail | https://www.youtube.com/results?search_query=bash+scripting+set+euo+pipefail+error+handling | YouTube search for bash error handling tutorials. |

---

## 6. Rust — Async Programming with Tokio & reqwest

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Tokio Tutorial — tokio.rs | https://tokio.rs/tokio/tutorial | The official Tokio tutorial: spawning, async/await, channels, I/O. |
| [OFFICIAL] | tokio — Rust API Docs | https://docs.rs/tokio | Official API reference for every Tokio crate, macro, and module. |
| [OFFICIAL] | Async and Await — Rust Async Book | https://rust-lang.github.io/async-book/part-guide/async-await.html | How async/await works and how runtimes like Tokio plug in. |
| [TUTORIAL] | Making HTTP Requests in Rust with reqwest — LogRocket | https://blog.logrocket.com/making-http-requests-rust-reqwest/ | Practical: Tokio + reqwest for async HTTP calls in Rust. |
| [BLOG] | Practical Guide to Async Rust and Tokio — Medium | https://medium.com/@OlegKubrakov/practical-guide-to-async-rust-and-tokio-99e818c11965 | Real-world async patterns with Tokio and proper error handling. |
| [Q&A] | Async/await and Multi-thread Tokio Runtime — Rust Forum | https://users.rust-lang.org/t/async-await-and-multi-thread-tokio-runtime/110107 | Community Q&A on runtime config and multi-threading in Tokio. |
| [VIDEO] | Rust Tokio Async Programming Tutorials | https://www.youtube.com/results?search_query=rust+tokio+async+await+programming+tutorial | YouTube search for Rust async Tokio tutorials. |

---

## 7. Tailscale — Setup & Configuration on Linux

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Install Tailscale on Linux — Tailscale Docs | https://tailscale.com/docs/install/linux | Official per-distro install instructions and one-line install script. |
| [OFFICIAL] | Tailscale Quickstart — Tailscale Docs | https://tailscale.com/kb/1017/install | Quickstart: install, `tailscale up`, verify device in tailnet. |
| [OFFICIAL] | Tailscale CLI Reference | https://tailscale.com/docs/reference/tailscale-cli | All `tailscale` CLI commands for managing connections on Linux. |
| [TUTORIAL] | How to Use Tailscale: Step-by-Step for Beginners — LearnLinux.tv | https://www.learnlinux.tv/how-to-use-tailscale-step-by-step-setup-guide-for-beginners/ | Beginner-friendly written guide with accompanying YouTube video. |
| [TUTORIAL] | Setting Up Tailscale on Ubuntu — Pi My Life Up | https://pimylifeup.com/ubuntu-tailscale/ | Practical Ubuntu walkthrough from install through connecting devices. |
| [BLOG] | Tailscale — ArchWiki | https://wiki.archlinux.org/title/Tailscale | Install, systemd service setup, and subnet routing on Arch/Linux. |
| [VIDEO] | Tailscale Setup Linux Tutorials | https://www.youtube.com/results?search_query=tailscale+setup+linux+tutorial+beginners | YouTube search for Tailscale Linux setup tutorials. |

---

## 8. Linux Server Security — General Hardening

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Linux Server Hardening Best Practices — Netwrix | https://netwrix.com/en/resources/guides/linux-hardening-security-best-practices/ | Enterprise reference: access control, auditing, patch management, CIS. |
| [TUTORIAL] | 40 Linux Server Hardening Tips — nixCraft | https://www.cyberciti.biz/tips/linux-security.html | The classic 40-step checklist with real commands for each step. |
| [TUTORIAL] | Linux System Hardening: Top 10 Tips — TuxCare | https://tuxcare.com/blog/linux-hardening/ | Modern 2025-focused overview: SSH, UFW, sysctl, and monitoring. |
| [BLOG] | How-To-Secure-A-Linux-Server — GitHub | https://github.com/imthenachoman/How-To-Secure-A-Linux-Server | One of the most referenced Linux hardening guides anywhere. |
| [BLOG] | The Practical Linux Hardening Guide — GitHub | https://github.com/trimstray/the-practical-linux-hardening-guide | Deep-dive guide referencing OpenSCAP, CIS, and STIG standards. |
| [BLOG] | Linux Server Hardening: Most Important Steps — Linux Audit | https://linux-audit.com/linux-server-hardening-most-important-steps-to-secure-systems/ | Prioritised checklist from a dedicated Linux security auditing site. |
| [VIDEO] | Linux Server Security Hardening 2025 | https://www.youtube.com/results?search_query=linux+server+security+hardening+tutorial+2025 | YouTube search for current Linux server hardening video tutorials. |
