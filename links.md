<!-- Last updated: 2026-04-08 | Total links: 203 | Pro tip: ctrl+F 'COBOL' for 80s nostalgia or 'sysctl' for firewall wins. -->

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

---

## 17. Linux Server Hardening — sysctl, UFW, Tailscale, Kernel Lockdown

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | sysctl man page | https://man7.org/linux/man-pages/man8/sysctl.8.html | Full reference for sysctl — flags, file format, --system behavior |
| [OFFICIAL] | sysctl.d man page | https://www.man7.org/linux/man-pages/man5/sysctl.d.5.html | How /etc/sysctl.d/ files are loaded and in what order |
| [OFFICIAL] | kernel.modules_disabled — Linux kernel docs | https://www.kernel.org/doc/html/latest/admin-guide/sysctl/kernel.html | Official docs on kernel.modules_disabled — what it does, when it takes effect |
| [OFFICIAL] | UFW man page | https://manpages.ubuntu.com/manpages/focal/man8/ufw.8.html | Full UFW command reference — rules, interface-specific allow, default policies |
| [OFFICIAL] | Linux sysfs network interface operstate | https://www.kernel.org/doc/Documentation/ABI/testing/sysfs-class-net | Explains /sys/class/net/<iface>/operstate values (up/down/unknown/dormant) |
| [OFFICIAL] | Tailscale docs — Linux installation | https://tailscale.com/kb/1031/install-linux | Official Tailscale setup on Linux, interface naming, subnet routing |
| [BLOG] | Linux Hardening Guide — madaidans-insecurities | https://madaidans-insecurities.github.io/guides/linux-hardening.html | Comprehensive hardening guide — sysctl, kernel modules, filesystem hardening |
| [BLOG] | ArchWiki — Security — Kernel hardening | https://wiki.archlinux.org/title/Security#Kernel_hardening | Practical sysctl settings with explanations, including net.ipv4 and kernel params |
| [DOCS] | UFW — community help | https://help.ubuntu.com/community/UFW | Ubuntu's UFW guide — interface rules, app profiles, logging |
| [Q&A] | net.ipv4.conf.all vs .default — what's the difference | https://serverfault.com/questions/431593/difference-between-sysctl-net-ipv4-conf-all-and-default | Explains why both all and default must be set for complete sysctl coverage |
| [BLOG] | Tailscale + UFW — locking down with Tailscale | https://tailscale.com/kb/1077/secure-server-ubuntu-18-04 | Official Tailscale guide for locking a server to Tailscale-only access via UFW |

---

## 18. Rust — Security Scripting Patterns

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | std::process::Command — Rust docs | https://doc.rust-lang.org/std/process/struct.Command.html | Full API for spawning processes — status(), output(), ExitStatus |
| [OFFICIAL] | std::process::ExitStatus | https://doc.rust-lang.org/std/process/struct.ExitStatus.html | How to check success() vs raw exit codes in Rust |
| [BLOG] | Rust sysfs reading patterns | https://doc.rust-lang.org/std/fs/fn.read_to_string.html | std::fs::read_to_string — simplest way to read /sys/ virtual files |

---

## 19. Local AI — Ollama, Phi-3, Self-Hosted LLMs

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Ollama — GitHub | https://github.com/ollama/ollama | Main repo: install, model library, API docs, Docker usage |
| [OFFICIAL] | Ollama REST API reference | https://github.com/ollama/ollama/blob/main/docs/api.md | Full /api/generate, /api/chat, streaming, logprobs params |
| [OFFICIAL] | Ollama Python library | https://github.com/ollama/ollama-python | Official Python client — chat(), generate(), streaming examples |
| [OFFICIAL] | Phi-3 Mini on Ollama | https://ollama.com/library/phi3 | Model card: context window, GGUF variants, memory requirements |
| [BLOG] | Running LLMs locally with Ollama | https://ollama.com/blog | Ollama blog — model releases, performance tips, hardware guides |
| [DOCS] | Gemma 2B model card | https://ollama.com/library/gemma | Alternative to Phi-3 for 8GB RAM — tradeoffs vs phi3:mini |

---

## 20. PyQt6 — GUI Development

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | PyQt6 documentation | https://www.riverbankcomputing.com/static/Docs/PyQt6/ | Full API reference — all widgets, signals, slots, threading |
| [OFFICIAL] | Qt6 QThread docs | https://doc.qt.io/qt-6/qthread.html | Official QThread API — worker pattern, signals, safe UI updates from threads |
| [OFFICIAL] | Qt6 QTextBrowser | https://doc.qt.io/qt-6/qtextbrowser.html | Rich text display widget — setHtml(), scrolling, cursor control |
| [OFFICIAL] | Qt6 QPalette / Fusion dark theme | https://doc.qt.io/qt-6/qpalette.html | How to build a dark palette with ColorRole — the right way |
| [TUTORIAL] | PyQt6 threading — worker pattern | https://www.pythonguis.com/tutorials/multithreading-pyqt6-applications-qthreadpool/ | QThread worker pattern for non-blocking UI — pyqtSignal, run(), emit() |
| [BLOG] | QApplication.setFont() cascade | https://doc.qt.io/qt-6/qapplication.html#setFont | How app-level font changes propagate to all widgets that don't override |

---

## 21. Hybrid Python + Rust Architecture

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Axum web framework | https://docs.rs/axum/latest/axum/ | Rust HTTP server used as sidecar — Router, handlers, State extractor |
| [OFFICIAL] | reqwest — Rust HTTP client | https://docs.rs/reqwest/latest/reqwest/ | Async HTTP with streaming body support — used to proxy Ollama |
| [OFFICIAL] | sha2 crate | https://docs.rs/sha2/latest/sha2/ | SHA-256 hashing in Rust — used for response cache keys |
| [BLOG] | Python subprocess vs localhost HTTP for Rust sidecars | https://pythonspeed.com/articles/faster-python-subprocess/ | When to use subprocess vs HTTP for calling native binaries from Python |
| [DOCS] | Docker multi-stage builds | https://docs.docker.com/build/building/multi-stage/ | How to build a Rust binary and copy it into a Python image cleanly |
| [DOCS] | Running PyQt6 GUI in Docker with X11 | https://wiki.ros.org/docker/Tutorials/GUI | xhost +local:docker, DISPLAY forwarding, /tmp/.X11-unix volume pattern |

---

## 22. Go — CLI Tools, Flags, Signal Handling

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Go flag package | https://pkg.go.dev/flag | Standard library flag parsing — StringVar, BoolVar, custom Usage, -flag and --flag both work |
| [OFFICIAL] | Go time.Duration | https://pkg.go.dev/time#Duration | ParseDuration syntax reference — 30s, 5m, 2m30s, 1h15m and how to handle bare integers |
| [OFFICIAL] | os/signal — Notify | https://pkg.go.dev/os/signal#Notify | How to catch SIGINT/SIGTERM in Go for graceful Ctrl+C handling |
| [OFFICIAL] | Go modules — go mod init | https://go.dev/ref/mod | Module system basics — go.mod, go mod init, go build without external deps |
| [DOCS] | ANSI escape codes — cursor & colour | https://gist.github.com/fnky/458719343aabd01cfb17a3a4f7296797 | \033[?25l hide cursor, \033[K erase line, \033[1;32m colour — all used in countdown |

---

## 23. Go — JSON, File I/O, Structs, os.Args

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | encoding/json package | https://pkg.go.dev/encoding/json | Marshal/Unmarshal, struct tags (`json:"key"`), MarshalIndent for pretty output |
| [OFFICIAL] | os.ReadFile / os.WriteFile | https://pkg.go.dev/os#ReadFile | Simple file read/write — no need to open/close handles for basic use cases |
| [OFFICIAL] | os.UserHomeDir | https://pkg.go.dev/os#UserHomeDir | Cross-platform home directory — better than $HOME env var |
| [OFFICIAL] | strconv.Atoi | https://pkg.go.dev/strconv#Atoi | Convert string → int with error handling — the standard way to parse CLI number args |
| [OFFICIAL] | sort.Slice | https://pkg.go.dev/sort#Slice | Sort any slice with a custom comparator — no need to implement sort interfaces |
| [BLOG] | Go struct tags explained | https://www.digitalocean.com/community/tutorials/how-to-use-struct-tags-in-go | What backtick annotations do and how json/db/yaml tags work |
| [OFFICIAL] | time.Time.Format reference | https://pkg.go.dev/time#Time.Format | Go's unusual reference time (Mon Jan 2 15:04:05 2006) — why it works this way |

---

## 24. Go — Project Layout, context, Channels, flag.Value

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | Standard Go project layout | https://github.com/golang-standards/project-layout | The cmd/ + internal/ directory convention — explains every folder's purpose |
| [OFFICIAL] | internal/ packages (Go spec) | https://pkg.go.dev/cmd/go#hdr-Internal_Directories | Why internal/ is enforced by the toolchain and when to use it |
| [OFFICIAL] | context package | https://pkg.go.dev/context | context.WithCancel, ctx.Done(), ctx.Err() — the standard way to cancel goroutines |
| [OFFICIAL] | flag.Value interface | https://pkg.go.dev/flag#Value | Implement String() + Set() to make custom flag types — used to detect "was this flag set?" |
| [BLOG] | Go channels explained | https://go.dev/tour/concurrency/2 | Tour of Go — buffered vs unbuffered channels, range over channel, close() |
| [BLOG] | Separation of concerns in Go | https://threedots.tech/post/introducing-clean-architecture-in-go/ | How to structure Go apps with clean layers — the pattern used in countdown-timer |
| [OFFICIAL] | io.Writer interface | https://pkg.go.dev/io#Writer | Why functions should accept io.Writer instead of writing to os.Stdout directly — testability |

---

## 25. Go — WebSocket, Goroutines, Multiplayer Games

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | gorilla/websocket | https://pkg.go.dev/github.com/gorilla/websocket | The standard Go WebSocket library — Upgrader, ReadMessage, WriteMessage, concurrent-write safety |
| [OFFICIAL] | sync.RWMutex | https://pkg.go.dev/sync#RWMutex | Read-write mutex for leaderboard — multiple readers OK, one writer at a time |
| [OFFICIAL] | sync.Once | https://pkg.go.dev/sync#Once | Safe one-time execution — used to prevent double-close panic on done channel |
| [OFFICIAL] | go:embed directive | https://pkg.go.dev/embed | Embed static files into the binary at compile time — one self-contained executable |
| [BLOG] | Server-authoritative game loop in Go | https://gafferongames.com/post/fix_your_timestep/ | Fixed timestep game loop — why 1/60s dt is correct and drift-free |
| [DOCS] | HTML5 Canvas 2D API | https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D | ctx.arc, ctx.fillRect, shadowBlur, setLineDash — everything used in the Pong renderer |
| [BLOG] | WebSocket protocol explained | https://developer.mozilla.org/en-US/docs/Web/API/WebSocket | Browser WebSocket API — onopen, onmessage, send, readyState |

---

## 26. Bash Scripting & Linux

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [DOCS] | rsync man page | https://linux.die.net/man/1/rsync | Full rsync flag reference — -a, -A, -X, --delete explained |
| [DOCS] | Crontab syntax reference | https://crontab.guru | Interactive cron expression builder and reference |
| [DOCS] | Bash set -euo pipefail | https://www.gnu.org/software/bash/manual/bash.html#The-Set-Builtin | Official bash manual for the set builtin |
| [TUTORIAL] | Safe crontab editing pattern | https://stackoverflow.com/questions/878600/how-to-create-a-cron-job-using-bash-automatically-without-the-interactive-editor | The (crontab -l; echo ...) | crontab - pattern explained |
| [DOCS] | mountpoint man page | https://linux.die.net/man/1/mountpoint | Check if a path is a mountpoint — used as backup drive guard before rsync |
| [TUTORIAL] | realpath for cron-safe paths | https://man7.org/linux/man-pages/man1/realpath.1.html | Resolves ~ to absolute path so cron can find your script |

---

## 27. Python / Terminal UI / rich

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | rich library docs | https://rich.readthedocs.io/en/stable/ | Full reference for rich Text, Live, Layout, Panel, markup |
| [OFFICIAL] | rich.live.Live | https://rich.readthedocs.io/en/stable/live.html | Live display class — screen=True uses alternate buffer, refresh_per_second |
| [OFFICIAL] | rich.text.Text | https://rich.readthedocs.io/en/stable/text.html | Text class with inline styles — used to layer Matrix rain with panel |
| [DOCS] | Python tty module | https://docs.python.org/3/library/tty.html | tty.setraw() for non-blocking single-keypress terminal input |
| [DOCS] | Python termios module | https://docs.python.org/3/library/termios.html | Save/restore terminal settings around setraw — essential for cleanup |
| [DOCS] | Python threading module | https://docs.python.org/3/library/threading.html | Thread + daemon threads for background key reading and backup execution |
| [DOCS] | Python queue.Queue | https://docs.python.org/3/library/queue.html | Thread-safe queue for passing keystrokes from reader thread to main loop |
| [BLOG] | Matrix digital rain in Python | https://realpython.com/python-rich/ | Real Python's rich library overview — styling, tables, live display |

---

## 28. Rust — Archive Streaming, zstd, tar, SQLite FTS5

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | zstd crate — docs.rs | https://docs.rs/zstd | Rust zstd bindings — Decoder for streaming decompression, Encoder for compression |
| [OFFICIAL] | tar crate — docs.rs | https://docs.rs/tar | TAR archive reading/writing in Rust — Archive::entries(), Entry::path(), streaming read |
| [OFFICIAL] | rusqlite — bundled + FTS5 | https://docs.rs/rusqlite | SQLite Rust bindings — bundled feature compiles SQLite with FTS5 included |
| [OFFICIAL] | SQLite FTS5 documentation | https://www.sqlite.org/fts5.html | Official FTS5 docs: virtual tables, tokenisers, auxiliary functions (highlight, snippet, bm25) |
| [OFFICIAL] | indicatif — wrap_read / ProgressBar | https://docs.rs/indicatif | Progress bars in Rust CLIs — wrap_read() transparently tracks bytes through any io::Read |
| [OFFICIAL] | comfy-table — dynamic tables | https://docs.rs/comfy-table | Terminal table rendering in Rust — auto-sizing columns, colours, alignment |
| [BLOG] | SQLite FTS5 contentless tables | https://www.sqlite.org/fts5.html#contentless_tables | When to use content="" — saves space by storing only the index, not the original text |
| [TUTORIAL] | Rust I/O traits: Read, Write, BufRead | https://doc.rust-lang.org/std/io/index.html | How Rust's composable I/O adapters work — the foundation of zero-copy streaming pipelines |
| [BLOG] | SQLite bulk insert performance (transactions) | https://avi.im/blag/2021/fast-sqlite-inserts/ | Why batched transactions are 500× faster than auto-commit — the definitive benchmark |

---

## 29. Rust — Data Fortress: Full-Stack Personal File Management System

| Type | Title | URL | Why It's Useful |
|------|-------|-----|-----------------|
| [OFFICIAL] | blake3 crate — docs.rs | https://docs.rs/blake3 | BLAKE3 hashing in Rust — streaming API, par_iter hashing, 64-char hex output |
| [OFFICIAL] | walkdir crate — docs.rs | https://docs.rs/walkdir | Recursive directory traversal — filter_entry pruning, same_file_system, follow_links |
| [OFFICIAL] | infer crate — docs.rs | https://docs.rs/infer | Magic-byte file type detection for 150+ formats — no system deps, pure Rust |
| [OFFICIAL] | mime_guess crate — docs.rs | https://docs.rs/mime_guess | Extension-to-MIME fallback when magic bytes are inconclusive |
| [OFFICIAL] | kamadak-exif crate — docs.rs | https://docs.rs/kamadak-exif | Pure-Rust EXIF reader — GPS DMS→decimal, camera make/model, date taken |
| [OFFICIAL] | pdf-extract crate — docs.rs | https://docs.rs/pdf-extract | Extract plain text from PDFs in pure Rust — no poppler/ghostscript required |
| [OFFICIAL] | calamine crate — docs.rs | https://docs.rs/calamine | Read Excel/XLSX/ODS files in pure Rust — iterate sheets and cells |
| [OFFICIAL] | quick-xml crate — docs.rs | https://docs.rs/quick-xml | Fast streaming XML parser — used to extract text from DOCX/PPTX ZIP internals |
| [OFFICIAL] | rayon crate — docs.rs | https://docs.rs/rayon | Work-stealing parallel iterators — par_iter() is drop-in for iter() |
| [OFFICIAL] | indicatif crate — docs.rs | https://docs.rs/indicatif | Progress bars and spinners for Rust CLIs |
| [OFFICIAL] | Streamlit multi-page apps | https://docs.streamlit.io/develop/concepts/multipage-apps/overview | Auto-discovering pages/ from numeric filename prefixes |
| [OFFICIAL] | st.cache_data — Streamlit docs | https://docs.streamlit.io/develop/api-reference/caching-and-state/st.cache_data | Memoising DB query results in Streamlit with TTL |
| [OFFICIAL] | assert_cmd crate — docs.rs | https://docs.rs/assert_cmd | Black-box CLI testing — cargo_bin(), .assert().success(), stdout inspection |
| [OFFICIAL] | SQLite WAL mode | https://www.sqlite.org/wal.html | How WAL allows concurrent readers while a writer is active |
| [OFFICIAL] | SQLite URI filenames | https://www.sqlite.org/uri.html | Open SQLite in read-only mode with file:path?mode=ro |
| [BLOG] | BLAKE3 — much faster than MD5/SHA | https://github.com/BLAKE3-team/BLAKE3 | BLAKE3 design paper and benchmarks — why it's ideal for dedup hashing |
| [BLOG] | Two-phase scan pattern for deleted file detection | https://www.sqlite.org/lang_update.html | mark_all_absent → walk → mark_present — elegant pattern using SQL UPDATE |
| [TUTORIAL] | Plotly Express in Python | https://plotly.com/python/plotly-express/ | High-level Plotly API — pie, bar, scatter, area charts with one function call |
| [DOCS] | humanize Python library | https://python-humanize.readthedocs.io/ | naturalsize(), naturaltime() — bytes and timestamps to human-readable strings |
| [DOCS] | subprocess.run — Python docs | https://docs.python.org/3/library/subprocess.html#subprocess.run | capture_output, text=True, timeout — the right way to shell out from Python |
| [OFFICIAL] | XDG Base Directory Specification | https://specifications.freedesktop.org/basedir-spec/latest/ | Where Linux apps should store data, config, and cache files |
| [OFFICIAL] | dirs crate — docs.rs | https://docs.rs/dirs | Rust crate for XDG_DATA_HOME, XDG_CONFIG_HOME resolution |
| [TUTORIAL] | Rust integration tests with assert_cmd | https://rust-cli.github.io/book/tutorial/testing.html | Black-box binary testing — TempDir, assert_cmd, predicates patterns |
