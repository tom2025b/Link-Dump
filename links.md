<!-- Last updated: 2026-04-02 | Total links: 96 | Pro tip: ctrl+F 'COBOL' for 80s nostalgia or 'sysctl' for firewall wins. -->

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

---

## 9. Certifications & Call Center Tech (Chapter 4)

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | CompTIA A+ Certification — CompTIA | https://www.comptia.org/en-us/certifications/a/ | Official CompTIA page: exam objectives, exam codes (220-1101/1102), pricing, and study tools. |
| [TUTORIAL] | Free Study Guide for CompTIA A+ Core Series (Updated 2026) | https://uniontestprep.com/comptia-a-core-series-exam/study-guide | Free, beginner-friendly study guide covering all exam domains — no cost to access. |
| [OFFICIAL] | Microsoft Credentials — All Certifications | https://learn.microsoft.com/en-us/credentials/ | Microsoft Learn's central hub for all role-based certs including Azure and the MCT path. |
| [OFFICIAL] | MCT Renewal and Reinstatement — Microsoft Learn | https://learn.microsoft.com/en-us/credentials/certifications/mct-renewal-reinstatement | Official requirements and steps to become or renew as a Microsoft Certified Trainer (MCT). |
| [BLOG] | Giving Inmates a Second Chance as Prison Call Center Agents — TechTarget | https://www.techtarget.com/searchcustomerexperience/feature/Giving-inmates-a-second-chance-as-prison-call-center-agents | In-depth feature on prison call center programs, skills gained, and reentry outcomes. |
| [TUTORIAL] | CompTIA A+ Study Tips for Working Professionals | https://prepsaret.com/comptia/comptia-a-study-tips-for-working-professionals | Targeted advice for studying while working a demanding job — scheduling, pacing, burnout avoidance. |

---

## 10. Rust TUI — crossterm, Terminal Animation

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | crossterm — Rust API Docs | https://docs.rs/crossterm | Full API reference for crossterm: raw mode, alternate screen, cursor, colors, events. |
| [OFFICIAL] | crossterm GitHub — Crossterm.rs | https://github.com/crossterm-rs/crossterm | Source, examples, and CHANGELOG — essential for checking syntax changes between versions. |
| [TUTORIAL] | Building a Terminal UI in Rust with crossterm — Ratatui Guide | https://ratatui.rs/concepts/backends/crossterm/ | Explains the crossterm backend model and how raw mode + alternate screen work together. |
| [BLOG] | Rust Terminal Animation with crossterm — LogRocket | https://blog.logrocket.com/rust-and-tui-building-a-command-line-interface/ | Practical guide to building interactive terminal UIs with Rust and crossterm. |
| [Q&A] | crossterm Color::Rgb Syntax — Rust Users Forum | https://users.rust-lang.org/t/crossterm-color-rgb/92777 | Community thread on struct vs tuple syntax for Color::Rgb — a common gotcha. |
| [OFFICIAL] | clap — Command Line Argument Parser for Rust | https://docs.rs/clap | API docs for clap with derive macros — how to add CLI flags with #[derive(Parser)]. |

---

## 11. Rust GUI — egui & eframe

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | egui — Immediate Mode GUI for Rust | https://docs.rs/egui | Full egui API reference: widgets, Painter, Color32, Layout, Key, input handling. |
| [OFFICIAL] | eframe — egui App Framework | https://docs.rs/eframe | eframe API: how to set up a native window, the App trait, and run_native. |
| [OFFICIAL] | egui GitHub — emilk/egui | https://github.com/emilk/egui | Source and demos — best place to see how widgets are built and what changed between versions. |
| [TUTORIAL] | Writing a GUI app in Rust with egui — LogRocket | https://blog.logrocket.com/build-desktop-app-rust-egui/ | Step-by-step intro to building a real egui app from scratch. |
| [BLOG] | Immediate Mode vs Retained Mode GUI — egui Docs | https://github.com/emilk/egui?tab=readme-ov-file#why-immediate-mode | egui author's explanation of why immediate mode is simpler for animation-heavy apps. |
| [Q&A] | egui Painter and 2D Drawing — egui Discussions | https://github.com/emilk/egui/discussions/categories/q-a | Search for "Painter" here — community Q&A on custom drawing with egui's Painter API. |

---

## 12. Rust JSON — serde & serde_json

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | serde — Rust Serialization Framework | https://docs.rs/serde | API docs for serde: Serialize, Deserialize, derive macros, field attributes. |
| [OFFICIAL] | serde_json — Rust API Docs | https://docs.rs/serde_json | Full serde_json reference: from_str, from_reader, Value, error types. |
| [OFFICIAL] | Serde Guide — serde.rs | https://serde.rs/ | The official serde book: getting started, derive macros, custom serializers. |
| [TUTORIAL] | Working with JSON in Rust — LogRocket | https://blog.logrocket.com/json-and-rust-why-serde_json-is-the-top-choice/ | Practical guide to parsing and generating JSON with serde_json. |
| [BLOG] | Deserializing JSON in Rust — Zero to Production | https://www.lpalmieri.com/posts/serde-in-rust/ | Deep dive into serde's derive macros and handling optional/nested fields. |

---

## 13. Bash — rsync, Backup Scripts, notify-send

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | rsync Man Page — linux.die.net | https://linux.die.net/man/1/rsync | Complete rsync flag reference — -a, -A, -X, --delete, --backup-dir all explained. |
| [TUTORIAL] | rsync Backup Script on Linux — DigitalOcean | https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories | Most-cited rsync tutorial: flags, exclude patterns, dry-run, and incremental backups. |
| [TUTORIAL] | How to Use notify-send on Linux — LinuxHandbook | https://linuxhandbook.com/notify-send/ | Practical guide to desktop notifications from bash, including urgency and icons. |
| [BLOG] | Cron-Safe Bash Scripts — Bash Hackers Wiki | https://bash.cyberciti.biz/guide/Main_Page | Reference for bash scripting patterns including TTY detection and stdin handling. |
| [Q&A] | Detect If Script Is Running in Cron — Stack Overflow | https://stackoverflow.com/questions/3214935/detect-if-script-is-running-in-cron | Community answers on `[[ -t 0 ]]` and other cron-detection idioms. |
| [BLOG] | Using findmnt to Find Real Mountpoints — nixCraft | https://www.cyberciti.biz/tips/howto-find-linux-mount-point.html | How findmnt --target walks up the path to find the actual mountpoint. |

---

## 14. Linux Desktop — XDG .desktop Files, Cinnamon Launchers

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Desktop Entry Specification — freedesktop.org | https://specifications.freedesktop.org/desktop-entry-spec/latest/ | The authoritative XDG spec: every valid key, category, and type for .desktop files. |
| [OFFICIAL] | Desktop Files: A How-To — GNOME Developer Docs | https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html | GNOME's practical guide to integrating an app with the DE via a .desktop file. |
| [TUTORIAL] | Creating Application Launchers on Linux — MakeUseOf | https://www.makeuseof.com/how-to-create-desktop-entry-file-linux/ | Step-by-step: write, place, chmod, and verify a .desktop file on Linux Mint/Ubuntu. |
| [BLOG] | XDG Base Directory Spec — ArchWiki | https://wiki.archlinux.org/title/XDG_Base_Directory | Explains ~/.local/share/applications and the full XDG directory layout. |
| [Q&A] | .desktop File Not Showing in Menu — Ask Ubuntu | https://askubuntu.com/questions/306748/how-do-i-add-application-to-app-menu | Common fixes: wrong location, missing chmod +x, update-desktop-database command. |

---

## 15. Rust TUI / ratatui

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | ratatui docs | https://ratatui.rs | Widgets, layout, TableState, Sparkline API reference |
| [OFFICIAL] | ratatui 0.26 crate | https://docs.rs/ratatui/0.26.3 | Version-specific API — check here when docs.rs shows newer version |
| [OFFICIAL] | sysinfo crate | https://docs.rs/sysinfo/0.30 | CPU/RAM/disk/net/process APIs for system monitoring |
| [TUTORIAL] | ratatui book | https://ratatui.rs/tutorials/ | Step-by-step tutorials including counter app and JSON editor |
| [BLOG] | ratatui GitHub examples | https://github.com/ratatui/ratatui/tree/main/examples | Practical widget usage examples |

## 16. Rust — Axum HTTP Server & Shared State

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Axum 0.7 Docs | https://docs.rs/axum/0.7/ | Axum 0.7 router, handlers, JSON extractors — breaking changes from 0.6 |
| [OFFICIAL] | tokio::sync::watch | https://docs.rs/tokio/latest/tokio/sync/watch/ | Watch channel for broadcasting latest value to multiple receivers — zero-copy borrow() |
| [OFFICIAL] | ratatui Book | https://ratatui.rs/introduction/ | Official Ratatui guide for TUI apps |
| [OFFICIAL] | sysinfo 0.30 Docs | https://docs.rs/sysinfo/0.30/ | CPU/RAM/disk/net system metrics in Rust — process disk_usage() for I/O rates |
| [OFFICIAL] | crossterm Docs | https://docs.rs/crossterm/ | Cross-platform terminal control for raw mode, events, alternate screen |
| [BLOG] | Tokio spawn_blocking guide | https://tokio.rs/tokio/topics/bridging | Bridging sync/blocking code (TUI loops, raw terminal) in async Tokio apps |
