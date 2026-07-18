# Link Dump: Curated Learning Path

**Last complete audit:** 2026-07-18

**Repository evidence:** all 102 authenticated repositories owned by `tom2025b`, including private repositories, forks, the archived repository, and the empty repository

This is a curated path through the languages, libraries, interfaces, architecture, testing, data, performance, security, operations, developer tooling, and local-AI concepts used across Tom's projects. It is intentionally official-first, not official-only: a community resource remains only when it teaches something that the primary reference does not teach as well.

Every external resource was checked for reachability and manually assessed for title, authority, current relevance, and teaching role. A successful status code was not accepted as proof of quality, and bot-protected or unusual responses were reviewed separately.

## How to Use This Learning Path

Do not read this document from top to bottom unless you are deliberately surveying the whole stack. Pick a route below, read the section introduction, take the beginner resources in order, and move to intermediate or advanced material when a real project gives the details somewhere to attach.

### Metadata legend

| Field | Meaning |
|---|---|
| Type | `Official documentation`, `Article`, `Blog`, `Book`, `Video`, or `Reference`. Official-first does not mean that a specification is automatically the best first tutorial. |
| Title | The current resource title, checked against the destination. |
| URL | A direct HTTPS destination, never a generic search-results page. |
| Why this is valuable | What the resource uniquely teaches, when to use it, and important limits or safety context. |
| Difficulty | **Beginner** assumes little prior knowledge; **Intermediate** assumes working familiarity; **Advanced** focuses on internals, trade-offs, protocols, security, or performance. |
| Estimated time | A useful first pass through the relevant material. `Ongoing reference` means lookup is more appropriate than linear reading. |

### Suggested routes

| Goal | Recommended route |
|---|---|
| Linux operations | [Security and Linux Operations](#security-and-linux-operations) → [Git, GitHub, Automation, and Developer Tooling](#git-github-automation-and-developer-tooling) → [Error Handling and Reliability](#error-handling-and-reliability) → [Performance and Resource Efficiency](#performance-and-resource-efficiency) |
| Rust systems work | [Core Language Fundamentals](#core-language-fundamentals) → [Libraries and Frameworks](#libraries-and-frameworks-used-in-toms-projects) → [Error Handling](#error-handling-and-reliability) → [Testing](#testing-and-code-quality) → [Async](#async-programming-and-concurrency) → [Data](#data-storage-search-and-file-processing) → [Performance](#performance-and-resource-efficiency) |
| Go CLI and TUI work | [Core Language Fundamentals](#core-language-fundamentals) → [Libraries and Frameworks](#libraries-and-frameworks-used-in-toms-projects) → [CLI and TUI Development](#cli-and-tui-development) → [Testing](#testing-and-code-quality) → [Architecture](#architecture-and-design-patterns) |
| Python tooling | [Core Language Fundamentals](#core-language-fundamentals) → [Libraries and Frameworks](#libraries-and-frameworks-used-in-toms-projects) → [CLI and TUI Development](#cli-and-tui-development) or [GUI/Web](#gui-web-and-interactive-application-development) → [Data](#data-storage-search-and-file-processing) |
| Application architecture | [Libraries and Frameworks](#libraries-and-frameworks-used-in-toms-projects) → [GUI/Web](#gui-web-and-interactive-application-development) → [Architecture](#architecture-and-design-patterns) → [Testing](#testing-and-code-quality) → [Security](#security-and-linux-operations) |
| Local AI and agents | [Local AI and Related Tools](#local-ai-and-related-tools) → [Architecture](#architecture-and-design-patterns) → [Async](#async-programming-and-concurrency) → [Security](#security-and-linux-operations) → [Testing](#testing-and-code-quality) |

### Navigation

- [Core Language Fundamentals](#core-language-fundamentals)
- [Libraries and Frameworks Used in Tom's Projects](#libraries-and-frameworks-used-in-toms-projects)
- [CLI and TUI Development](#cli-and-tui-development)
- [GUI, Web, and Interactive Application Development](#gui-web-and-interactive-application-development)
- [Architecture and Design Patterns](#architecture-and-design-patterns)
- [Error Handling and Reliability](#error-handling-and-reliability)
- [Testing and Code Quality](#testing-and-code-quality)
- [Async Programming and Concurrency](#async-programming-and-concurrency)
- [Data, Storage, Search, and File Processing](#data-storage-search-and-file-processing)
- [Performance and Resource Efficiency](#performance-and-resource-efficiency)
- [Security and Linux Operations](#security-and-linux-operations)
- [Git, GitHub, Automation, and Developer Tooling](#git-github-automation-and-developer-tooling)
- [Local AI and Related Tools](#local-ai-and-related-tools)
- [Advanced and Cross-Cutting Topics](#advanced-and-cross-cutting-topics)
- [Career and Certification Resources](#career-and-certification-resources)
- [Resources Removed, Replaced, Updated, or Consolidated](#resources-removed-replaced-updated-or-consolidated)
- [Resources Added](#resources-added)
- [Future Educational Gaps](#future-educational-gaps)
- [Audit Notes](#audit-notes)

For the repository-by-repository evidence behind this path, see [repository-concepts.md](repository-concepts.md).

## Core Language Fundamentals

Build the language models that every later section assumes: ownership and traits in Rust, interfaces and modules in Go, Python's data model and typing, and precise shell quoting and expansion.

**Useful prerequisites:** Basic comfort editing files and running commands. Start here when a compiler error or shell expansion still feels mysterious.

**Project connection:** The 102-repository inventory found Rust in 37 repositories, Go in 16, Python in 12, and Shell in 27. These foundations feed nearly every CLI, TUI, service, and operations tool in the account.

**Suggested order:** Take one beginner language path first; then use its specification and standard-library references as lookups. Study Bash and POSIX distinctions before maintaining automation that must survive different shells.

**Continue with:** [Error Handling and Reliability](#error-handling-and-reliability), [Testing and Code Quality](#testing-and-code-quality).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Book | The Rust Programming Language | <https://doc.rust-lang.org/book/> | The canonical first path through ownership, borrowing, traits, iterators, modules, file I/O, and Cargo; it supplies the conceptual spine that API references assume. | Beginner | 12–16 hours |
| Official documentation | Rust By Example | <https://doc.rust-lang.org/rust-by-example/> | Runnable examples reinforce Rust syntax, ownership, modules, traits, iterators, error handling, and standard-library use after each corresponding Book chapter. | Beginner | 6–8 hours |
| Official documentation | A Tour of Go | <https://go.dev/tour/list> | The Go team’s interactive sequence introduces packages, methods, interfaces, generics, goroutines, and channels before the denser specification and package references. | Beginner | 4–6 hours |
| Official documentation | The Python Tutorial | <https://docs.python.org/3/tutorial/index.html> | Python’s own tutorial covers data structures, control flow, modules, classes, exceptions, generators, and standard-library orientation with fewer version-drift risks than third-party primers. | Beginner | 8–12 hours |
| Reference | std::fs::read_to_string | <https://doc.rust-lang.org/std/fs/fn.read_to_string.html> | The standard helper for bounded small text files such as sysfs attributes, including its UTF-8 and error semantics. Large, binary, changing, or untrusted files need a streaming or explicitly bounded alternative. | Beginner | 10 minutes |
| Reference | Go Modules Reference | <https://go.dev/ref/mod> | This is the authoritative source for `go.mod`, module paths, versions, workspaces, vendoring, and module-aware commands used across multi-repository Go work. | Intermediate | 2–3 hours |
| Official documentation | Organizing a Go module | <https://go.dev/doc/modules/layout> | Official, intentionally modest layout guidance replaces the misleading community “standard layout” and explains root packages, commands, and `internal` without prescribing unused folders. | Intermediate | 30 minutes |
| Reference | Standard library — Go Packages | <https://pkg.go.dev/std> | One maintained index replaces a cluster of tiny links while preserving direct access to `flag`, `time`, `os`, `encoding/json`, `strconv`, `sort`, and the rest of the versioned standard library. | Intermediate | Ongoing reference |
| Official documentation | Python Tutorial — Generators | <https://docs.python.org/3/tutorial/classes.html#generators> | The focused generator section explains `yield`, saved execution state, and generator expressions, filling a concept that broad Python introductions often mention only briefly. | Intermediate | 30 minutes |
| Reference | `typing` — Support for type hints | <https://docs.python.org/3/library/typing.html> | The standard-library reference documents protocols, generics, type aliases, narrowing, and gradual typing used to make Python tools maintainable without implying runtime enforcement. | Intermediate | 2–3 hours |
| Official documentation | Packaging Python Projects | <https://packaging.python.org/en/latest/tutorials/packaging-projects/> | The PyPA tutorial provides the current `pyproject.toml`, build, and publication path and avoids obsolete `setup.py`-first packaging advice. | Intermediate | 1–2 hours |
| Reference | The Rust Reference | <https://doc.rust-lang.org/reference/> | The primary language reference resolves exact questions about expressions, types, lifetimes, traits, and edition behavior without pretending to be an introductory tutorial. | Advanced | Ongoing reference |
| Reference | The Go Programming Language Specification | <https://go.dev/ref/spec> | The current normative reference defines Go syntax, types, interfaces, method sets, generics, and concurrency semantics when tutorial shorthand is insufficient. | Advanced | Ongoing reference |
| Reference | The Python Language Reference | <https://docs.python.org/3/reference/index.html> | The authoritative grammar and data-model reference is the right destination for precise questions about execution, expressions, imports, coroutines, and language semantics. | Advanced | Ongoing reference |
| Reference | Bash Reference Manual | <https://www.gnu.org/software/bash/manual/bash.html> | GNU’s complete manual is the source of truth for quoting, expansions, pipelines, redirections, functions, traps, options, and Bash-specific behavior. | Advanced | Ongoing reference |
| Reference | POSIX.1-2024 Shell Command Language | <https://pubs.opengroup.org/onlinepubs/9799919799/utilities/V3_chap02.html> | The current POSIX shell specification separates portable `sh` semantics from Bash extensions, especially for quoting, expansion, pipelines, redirection, and exit status. | Advanced | Ongoing reference |

## Libraries and Frameworks Used in Tom's Projects

Move from language syntax to the maintained crates, packages, and frameworks actually present in Tom's repositories, with direct API references and focused maintainer guides.

**Useful prerequisites:** Working familiarity with the relevant language and its package manager.

**Project connection:** The inventory repeatedly found Tokio, reqwest, Serde, clap, Ratatui, egui, Axum, rusqlite, Cobra, Bubble Tea, YAML, Rich, Requests, PyQt6, and related libraries.

**Suggested order:** Read the overview for the library you are about to use, build one small example, and keep the API reference nearby. Continue into architecture before allowing framework types to spread through a shared core.

**Continue with:** [Architecture and Design Patterns](#architecture-and-design-patterns), [Async Programming and Concurrency](#async-programming-and-concurrency).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | Overview — Serde | <https://serde.rs/> | Explains Serde's trait-based data model, derive workflow, attributes, and custom serialization used across Rust applications. | Beginner | 30 min |
| Official documentation | gopkg.in/yaml.v3 package documentation | <https://pkg.go.dev/gopkg.in/yaml.v3> | Direct reference for typed YAML decoding, field tags, strict-known-field handling, and encoding in Go tools. | Beginner | 25 min |
| Official documentation | sha2 crate documentation | <https://docs.rs/sha2/latest/sha2/> | Shows the RustCrypto digest API for incremental SHA-2 hashing and safe result handling. | Beginner | 15 min |
| Official documentation | exec.LookPath documentation | <https://pkg.go.dev/os/exec#LookPath> | Gives the standard contract for executable discovery without invoking a shell. | Beginner | 10 min |
| Official documentation | regexp.Compile documentation | <https://pkg.go.dev/regexp#Compile> | Shows fallible regular-expression compilation for user input and distinguishes it from panic-oriented MustCompile. | Beginner | 10 min |
| Official documentation | dirs crate documentation | <https://docs.rs/dirs/latest/dirs/> | Documents platform-specific config, data, cache, and state directory discovery, including optional results. | Beginner | 15 min |
| Official documentation | Generators — Python Functional Programming HOWTO | <https://docs.python.org/3/howto/functional.html#generators> | Explains lazy yield-based iteration, a core building block for streaming terminal and network output. | Beginner | 20 min |
| Reference | Ollama model library | <https://ollama.com/library> | Maintained model catalog for discovery without freezing model names or version-sensitive claims into the learning path. | Beginner | 10 min |
| Official documentation | reqwest crate documentation | <https://docs.rs/reqwest/latest/reqwest/> | Covers async and blocking clients, request builders, streaming bodies, TLS features, and error handling for Rust HTTP adapters. | Intermediate | 45 min |
| Official documentation | sysinfo crate documentation | <https://docs.rs/sysinfo/latest/sysinfo/> | Current API reference for refreshing and reading system, process, disk, network, CPU, and memory information. | Intermediate | 40 min |
| Official documentation | sync.RWMutex documentation | <https://pkg.go.dev/sync#RWMutex> | Defines Go's read/write lock semantics, memory-order guarantees, and non-reentrancy constraints. | Intermediate | 15 min |
| Official documentation | fuzzy-matcher crate documentation | <https://docs.rs/fuzzy-matcher/latest/fuzzy_matcher/> | Documents scoring and match-index APIs while making clear where application-level Unicode tests are still needed. | Intermediate | 20 min |
| Official documentation | tokio::sync::watch | <https://docs.rs/tokio/latest/tokio/sync/watch/> | Teaches a latest-value broadcast channel suited to server state and UI snapshots without unbounded history. | Intermediate | 30 min |
| Official documentation | Advanced Usage: Streaming Requests — Requests | <https://docs.python-requests.org/en/latest/user/advanced/#streaming-requests> | Covers stream=True, incremental iteration, and the connection-release obligations easy to miss in clients. | Intermediate | 25 min |
| Official documentation | syntect crate documentation | <https://docs.rs/syntect/latest/syntect/> | Reference for syntax sets, parsing state, scope stacks, themes, and lower-level highlighting control. | Advanced | 50 min |

## CLI and TUI Development

Design command-line and full-screen terminal programs that are composable, accessible, recover the terminal, emit useful errors, and remain testable without a live TTY.

**Useful prerequisites:** One language foundation plus familiarity with standard input, output, error, processes, and exit status.

**Project connection:** CLI design appeared in 38 repositories and terminal UI or rendering in 26. Ratatui, Crossterm, Bubble Tea, Rich, ANSI width, PTYs, and machine-readable output recur throughout the collection.

**Suggested order:** Start with general CLI conventions, streams, and exit behavior; add parsing and color policy; then study terminal modes, event loops, rendering, PTYs, and deterministic test backends.

**Continue with:** [Testing and Code Quality](#testing-and-code-quality), [Error Handling and Reliability](#error-handling-and-reliability).

### Project-derived concept notes

- No single durable primary guide yet covers screen-reader behavior across full-screen TUIs. Treat accessibility as a project-owned test matrix spanning keyboard-only use, reduced color, `NO_COLOR`, Unicode width, resize behavior, and at least one screen reader.
- POSIX PTY references cover the Linux model, but a comparable hands-on Windows ConPTY lifecycle, resize, signal, and teardown lab remains missing.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Article | Command Line Interface Guidelines | <https://clig.dev/> | A practical end-to-end guide to help, arguments, stdout and stderr, exit status, interactivity, signals, configuration, and humane errors. | Beginner | 1 hr 30 min |
| Official documentation | clap derive tutorial | <https://docs.rs/clap/latest/clap/_derive/_tutorial/> | Progressive maintainer tutorial for Parser derives, arguments, subcommands, defaults, and validation in Rust CLIs. | Beginner | 35 min |
| Official documentation | Working with Commands — Cobra | <https://cobra.dev/docs/how-to-guides/working-with-commands/> | Direct maintainer guidance for command trees, argument validation, RunE, error propagation, and exit behavior in Go CLIs. | Beginner | 30 min |
| Official documentation | fatih/color package documentation | <https://pkg.go.dev/github.com/fatih/color> | API reference for ANSI styling in Go, including terminal detection and explicit no-color control. | Beginner | 20 min |
| Reference | NO_COLOR | <https://no-color.org/> | Defines the cross-tool environment convention for disabling default ANSI color and clarifies precedence with user configuration. | Beginner | 10 min |
| Official documentation | Color in crossterm::style | <https://docs.rs/crossterm/latest/crossterm/style/enum.Color.html> | Direct enum contract for RGB, indexed, named, and reset colors without relying on stale Q&A syntax. | Beginner | 10 min |
| Official documentation | ratatui docs | <https://ratatui.rs/> | Current maintainer gateway to Ratatui tutorials, concepts, recipes, templates, and crate documentation. | Beginner | 15 min |
| Official documentation | Tutorials — Ratatui | <https://ratatui.rs/tutorials/> | Progressive maintained applications that connect the event loop, model state, rendering, and error handling. | Beginner | 1 hr 30 min |
| Official documentation | Bubble Tea | <https://github.com/charmbracelet/bubbletea> | Maintainer tutorial and examples for the Model, Update, View lifecycle and declarative terminal state in Go. | Beginner | 1 hr |
| Official documentation | Rich documentation | <https://rich.readthedocs.io/en/latest/> | Canonical guide to console output, styles, tables, panels, progress, logging, and renderables. | Beginner | 45 min |
| Official documentation | Markdown — Rich | <https://rich.readthedocs.io/en/latest/markdown.html> | Shows how to render structured Markdown in a terminal while retaining one output abstraction. | Beginner | 15 min |
| Official documentation | Go Wiki: TableDrivenTests | <https://go.dev/wiki/TableDrivenTests> | Direct Go pattern for compact behavior matrices that suit parsers, command semantics, and CLI edge cases. | Beginner | 20 min |
| Official documentation | crossterm crate documentation | <https://docs.rs/crossterm/latest/crossterm/> | Canonical API reference for terminal modes, cursor control, style, events, and cross-platform commands. | Intermediate | 45 min |
| Official documentation | crossterm GitHub — Crossterm.rs | <https://github.com/crossterm-rs/crossterm> | Maintainer source, examples, and changelog for checking real usage and API changes. | Intermediate | 30 min |
| Official documentation | Raw Mode — Ratatui | <https://ratatui.rs/concepts/backends/raw-mode/> | Explains canonical versus raw input, signal implications, and the obligation to restore the terminal. | Intermediate | 20 min |
| Official documentation | Tui with Terminal and EventHandler — Ratatui | <https://ratatui.rs/recipes/apps/terminal-and-event-handler/> | Maintainer recipe for startup, alternate screen, event loops, signals, async coordination, and cleanup on every exit path. | Intermediate | 50 min |
| Official documentation | ratatui crate documentation | <https://docs.rs/ratatui/latest/ratatui/> | Current widget, buffer, backend, terminal, style, and layout API reference without a stale version pin. | Intermediate | 1 hr |
| Official documentation | Ratatui maintainer examples | <https://github.com/ratatui/ratatui/tree/main/examples> | Compile-ready examples for widgets and interaction patterns when API docs alone are too abstract. | Intermediate | 45 min |
| Official documentation | ratatui::layout | <https://docs.rs/ratatui/latest/ratatui/layout/index.html> | Direct reference for constraints, directions, flex behavior, and compile-checked area splitting. | Intermediate | 30 min |
| Official documentation | TestBackend in ratatui::backend | <https://docs.rs/ratatui/latest/ratatui/backend/struct.TestBackend.html> | Shows deterministic in-memory terminal rendering for unit tests without a real TTY. | Intermediate | 25 min |
| Official documentation | Testing with insta snapshots — Ratatui | <https://ratatui.rs/recipes/testing/snapshots/> | Maintainer recipe that combines TestBackend buffers with reviewable snapshot tests for whole-screen regressions. | Intermediate | 35 min |
| Official documentation | Live Display — Rich | <https://rich.readthedocs.io/en/latest/live.html> | Explains controlled terminal-region refresh for progress, dashboards, and streaming responses. | Intermediate | 25 min |
| Reference | tty — Terminal control functions | <https://docs.python.org/3/library/tty.html> | Python's standard helpers for raw and cbreak terminal modes, including the attributes returned for restoration. Pair them with try/finally cleanup and the lower-level termios contract. | Intermediate | 20 minutes |
| Official documentation | Introduction to POSIX Utilities | <https://pubs.opengroup.org/onlinepubs/9699919799/utilities/V3_chap01.html> | Durable standard-level reference for option syntax, operands, diagnostics, environment, standard streams, and exit behavior. | Advanced | 1 hr |
| Reference | Unicode Standard Annex 11: East Asian Width | <https://www.unicode.org/reports/tr11/> | Primary reference for width properties and ambiguous-width behavior behind terminal-cell alignment bugs. | Advanced | 45 min |
| Reference | pty(7) — Linux manual page | <https://www.man7.org/linux/man-pages/man7/pty.7.html> | Defines master and slave pseudoterminals, foreground process groups, signals, and why terminal panels are not ordinary pipes. | Advanced | 35 min |
| Reference | termios — POSIX-style tty control | <https://docs.python.org/3/library/termios.html> | The standard Python interface for reading, changing, draining, and restoring POSIX terminal attributes. It is essential context for avoiding a terminal left in raw mode after errors or signals. | Advanced | 35 minutes |

## GUI, Web, and Interactive Application Development

Understand native immediate-mode GUIs, Qt applications, browser canvases, embedded frontends, HTTP services, WebSockets, and the state boundaries between them.

**Useful prerequisites:** A language foundation and basic event-loop, HTTP, and state concepts.

**Project connection:** Twenty-four repositories use GUI, web, or interactive interfaces, including egui/eframe, PyQt6, Leptos, Wails, Tauri, React, Canvas, Axum, NiceGUI, Flask, and WebSockets.

**Suggested order:** Choose the smallest framework overview that matches the project, learn its state and lifecycle model, then study background work, network boundaries, rendering loops, accessibility, and testability.

**Continue with:** [Architecture and Design Patterns](#architecture-and-design-patterns), [Security and Linux Operations](#security-and-linux-operations).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | egui crate documentation | <https://docs.rs/egui/latest/egui/> | Current API reference for immediate-mode widgets, layouts, input, textures, and custom painting. | Beginner | 1 hr |
| Official documentation | eframe crate documentation | <https://docs.rs/eframe/latest/eframe/> | Current framework reference for native and web application setup, App updates, persistence, and window integration. | Beginner | 45 min |
| Article | Why immediate mode — egui | <https://github.com/emilk/egui?tab=readme-ov-file#why-immediate-mode> | The maintainer's concise comparison of immediate and retained UI state clarifies egui's ownership model. | Beginner | 15 min |
| Official documentation | PyQt6 documentation | <https://www.riverbankcomputing.com/static/Docs/PyQt6/> | Canonical binding reference for using Qt 6 classes, signals, slots, and modules from Python. | Beginner | 45 min |
| Official documentation | Qt 6 QTextBrowser documentation | <https://doc.qt.io/qt-6/qtextbrowser.html> | Direct widget reference for navigable rich text, sources, links, history, and read-only document presentation. | Beginner | 20 min |
| Official documentation | QApplication::setFont documentation | <https://doc.qt.io/qt-6/qapplication.html#setFont> | Direct reference for application-level font defaults and widget-class-specific overrides. | Beginner | 10 min |
| Official documentation | embed package documentation | <https://pkg.go.dev/embed> | Shows how to package frontend assets into a Go binary and expose them through the io/fs abstraction. | Beginner | 25 min |
| Official documentation | CanvasRenderingContext2D — MDN | <https://developer.mozilla.org/en-US/docs/Web/API/CanvasRenderingContext2D> | Direct API reference for paths, shapes, text, transforms, state, compositing, images, and pixel operations. | Beginner | 45 min |
| Official documentation | WebSocket — MDN | <https://developer.mozilla.org/en-US/docs/Web/API/WebSocket> | Browser API lifecycle for opening, sending, receiving, errors, close events, buffered data, and ready states. | Beginner | 30 min |
| Official documentation | Managing State — React | <https://react.dev/learn/managing-state> | Maintainer learning path for deriving, locating, sharing, preserving, resetting, and scaling UI state. | Beginner | 1 hr |
| Official documentation | NiceGUI Documentation | <https://nicegui.io/documentation/> | Current backend-first model, event-loop rules, lifecycle hooks, binding, tasks, and client/server state for Python web UIs. | Beginner | 1 hr |
| Official documentation | W3C Web Accessibility Initiative | <https://www.w3.org/WAI/> | Standards-oriented starting point for accessible web interfaces, keyboard behavior, semantics, contrast, and testing resources. | Beginner | 30 min |
| Official documentation | egui GitHub — emilk/egui | <https://github.com/emilk/egui> | Maintainer demos, examples, design notes, and release history for practical immediate-mode GUI work. | Intermediate | 40 min |
| Official documentation | Painter in egui | <https://docs.rs/egui/latest/egui/struct.Painter.html> | Direct contract for custom shapes, text, clipping, layers, transforms, and low-level 2D drawing. | Intermediate | 30 min |
| Official documentation | Qt 6 QThread documentation | <https://doc.qt.io/qt-6/qthread.html> | Primary reference for thread affinity, event loops, worker objects, queued signals, interruption, and teardown. | Intermediate | 45 min |
| Official documentation | Qt 6 QPalette documentation | <https://doc.qt.io/qt-6/qpalette.html> | Accurately documents palette roles, groups, resolution, and platform/theme caveats without pretending to be a full dark-theme recipe. | Intermediate | 25 min |
| Article | PyQt6 threading — QThreadPool worker pattern | <https://www.pythonguis.com/tutorials/multithreading-pyqt6-applications-qthreadpool/> | Practical complement to the Qt API docs for moving work off the UI thread and returning results with signals. | Intermediate | 45 min |
| Official documentation | axum crate documentation | <https://docs.rs/axum/latest/axum/> | Current router, extractor, handler, response, middleware, and error-model reference for Rust web services. | Intermediate | 1 hr |
| Official documentation | State in axum::extract | <https://docs.rs/axum/latest/axum/extract/struct.State.html> | Direct guidance for owned server state, cloning handles, subrouters, and choosing State over request extensions. | Intermediate | 30 min |
| Official documentation | gorilla/websocket package documentation | <https://pkg.go.dev/github.com/gorilla/websocket> | Documents HTTP upgrade, framing, deadlines, close handling, and the one-reader/one-writer concurrency contract. | Intermediate | 45 min |
| Article | Fix Your Timestep! | <https://gafferongames.com/post/fix_your_timestep/> | Primary derivation of fixed and semi-fixed update loops, stability, accumulated time, and the spiral-of-death trade-off. | Intermediate | 35 min |
| Official documentation | Storage — NiceGUI | <https://nicegui.io/documentation/storage> | Distinguishes tab, client, browser, user, and general state by location, lifetime, persistence, and security requirements. | Intermediate | 30 min |
| Official documentation | Introduction — The Leptos Book | <https://book.leptos.dev/> | Maintainer book from fine-grained reactivity through routing, global state, client rendering, server rendering, and hydration. | Intermediate | 2 hr |
| Official documentation | How does it work? — Wails | <https://wails.io/docs/howdoesitwork/> | Explains Go-to-JavaScript bindings, generated types, lifecycle callbacks, embedded assets, and the webview boundary. | Intermediate | 45 min |
| Official documentation | Process Model — Electron | <https://www.electronjs.org/docs/latest/tutorial/process-model> | Defines main, renderer, preload, and utility process responsibilities plus safe IPC exposure through context isolation. | Intermediate | 45 min |
| Reference | RFC 6455: The WebSocket Protocol | <https://www.rfc-editor.org/info/rfc6455/> | Normative handshake, framing, fragmentation, close, masking, origin, and security reference behind browser and server libraries. | Advanced | 1 hr 30 min |
| Official documentation | Security — Electron | <https://www.electronjs.org/docs/latest/tutorial/security> | Maintainer checklist for sandboxing, context isolation, navigation, permissions, CSP, sender validation, and untrusted content. | Advanced | 1 hr |
| Official documentation | Security — xterm.js | <https://xtermjs.org/docs/guides/security/> | Threat model for browser terminals, untrusted terminal data, JavaScript access, links, WebSockets, privilege, and embedding. | Advanced | 45 min |
| Official documentation | node-pty | <https://github.com/microsoft/node-pty> | Maintainer reference for spawning terminal processes, flow control, platform support, privilege inheritance, and server-side risk. | Advanced | 35 min |
| Reference | Supported Terminal Sequences — xterm.js | <https://xtermjs.org/docs/api/vtfeatures/> | Concrete inventory of control, CSI, DCS, ESC, and OSC sequences for terminal emulation and compatibility testing. | Advanced | 1 hr |

## Architecture and Design Patterns

Separate durable domain behavior from CLI, TUI, GUI, network, storage, and provider adapters; make ownership, dependency direction, contracts, and failure boundaries explicit.

**Useful prerequisites:** Experience building at least one small application and seeing change ripple through it.

**Project connection:** Forty-nine repositories expose architecture themes such as headless shared cores, ports and adapters, state machines, provider abstractions, client/server systems, DAGs, plugins, and versioned machine contracts.

**Suggested order:** Begin with separation of concerns and dependency direction, then study concrete application structures, state ownership, contracts, compatibility, distributed workflows, and plugin boundaries.

**Continue with:** [Advanced and Cross-Cutting Topics](#advanced-and-cross-cutting-topics), [Error Handling and Reliability](#error-handling-and-reliability).

### Project-derived concept notes

- Conductor's append/replace handoff record and ordered review gates form a project-specific protocol across heterogeneous coding agents. Preserve actor, evidence, decision, validation result, and schema version as explicit fields; no general resource teaches this exact convention.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Article | Hexagonal architecture — the original 2005 article | <https://alistair.cockburn.us/hexagonal-architecture/> | Primary definition of ports and adapters, a UI-free application core, technology-specific adapters, and isolated regression testing. | Intermediate | 35 min |
| Official documentation | Rust API Guidelines | <https://rust-lang.github.io/api-guidelines/> | Library-team checklist for naming, traits, conversions, errors, documentation, flexibility, safety, and dependable public crate APIs. | Intermediate | 1 hr |
| Official documentation | Developing and publishing Go modules | <https://go.dev/doc/modules/developing> | Connects focused public APIs, compatibility commitments, versioning, discovery, local client tests, and module publication. | Intermediate | 40 min |
| Official documentation | Multi-stage builds — Docker Docs | <https://docs.docker.com/build/building/multi-stage/> | Shows how to separate build and runtime concerns when packaging mixed-language binaries and frontends. | Intermediate | 30 min |
| Official documentation | SemVer Compatibility — The Cargo Book | <https://doc.rust-lang.org/cargo/reference/semver.html> | Detailed classification of Rust public-API changes so library boundaries can evolve without accidental consumer breakage. | Advanced | 1 hr |
| Official documentation | PyO3 user guide | <https://pyo3.rs/main/index.html> | Maintainer guide to the in-process alternative for Python/Rust integration, including extensions, embedding, the GIL, and packaging choices. | Advanced | 1 hr 30 min |
| Official documentation | Architecture overview — Model Context Protocol | <https://modelcontextprotocol.io/docs/learn/architecture> | Current host-client-server model, data and transport layers, lifecycle, capabilities, and contract vocabulary for MCP systems. | Advanced | 45 min |

## Error Handling and Reliability

Represent failure precisely, preserve useful context, distinguish findings from execution failures, bound retries, and shut down cleanly across subprocess, network, file, and terminal boundaries.

**Useful prerequisites:** Core language control flow and basic I/O.

**Project connection:** Reliability concepts appeared in 67 repositories: typed Rust errors, Go wrapping and contexts, Python exceptions, Bash traps, provider fallbacks, process status, retry/backoff, partial failure, and atomic output.

**Suggested order:** Learn the native error model first, then subprocess and cleanup behavior, timeouts and retry policy, graceful shutdown, partial failure, and user-facing diagnostics.

**Continue with:** [Testing and Code Quality](#testing-and-code-quality), [Async Programming and Concurrency](#async-programming-and-concurrency).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Book | Error Handling — The Rust Programming Language | <https://doc.rust-lang.org/book/ch09-00-error-handling.html> | The official chapter establishes recoverable `Result` handling, propagation with `?`, panic boundaries, and when failure belongs in a return type. | Beginner | 1–2 hours |
| Official documentation | Errors and Exceptions — Python Tutorial | <https://docs.python.org/3/tutorial/errors.html> | The official tutorial covers exception matching, chaining, cleanup, user-defined exceptions, and narrow handling before learners jump into framework-specific patterns. | Beginner | 1 hour |
| Reference | `thiserror` — Rust API documentation | <https://docs.rs/thiserror/latest/thiserror/> | Maintainer documentation shows how libraries expose typed error enums with derived `Display`, `source`, and `From` implementations while keeping the public API explicit. | Intermediate | 45 minutes |
| Reference | `anyhow` — Rust API documentation | <https://docs.rs/anyhow/latest/anyhow/> | This complements `thiserror` for applications by documenting contextual error reports, source chains, backtraces, and the `Context` trait without conflating app and library error design. | Intermediate | 45 minutes |
| Reference | Serde field attributes | <https://serde.rs/field-attrs.html#default> | The maintainer reference explains `default`, `rename`, `flatten`, custom serializers, and validation boundaries needed for tolerant but deliberate parsing of evolving tool output. | Intermediate | 30 minutes |
| Blog | Working with Errors in Go 1.13 | <https://go.dev/blog/go1.13-errors> | The Go project explains wrapping plus `errors.Is`, `errors.As`, and `Unwrap`, including the API-compatibility consequences of exposing wrapped implementation errors. | Intermediate | 30 minutes |
| Reference | `subprocess` — Subprocess management | <https://docs.python.org/3/library/subprocess.html> | The standard reference documents argument-safe process creation, timeouts, captured output, exit checking, and the security differences between argv execution and `shell=True`. | Intermediate | 1–2 hours |
| Reference | std::process::Command | <https://doc.rust-lang.org/std/process/struct.Command.html> | Rust's standard argv-based subprocess builder, covering environment control, standard streams, working directories, spawning, output capture, and platform behavior. Passing arguments separately avoids an unnecessary shell parsing layer. | Intermediate | 35 minutes |
| Article | Writing Safe Shell Scripts | <https://sipb.mit.edu/doc/safe-shell/> | MIT SIPB’s concise checklist adds practical habits around quoting, temporary files, cleanup, and command failure; it is retained only alongside the explicit `errexit` caveat reference below. | Intermediate | 20 minutes |
| Reference | std::process::ExitStatus | <https://doc.rust-lang.org/std/process/struct.ExitStatus.html> | The standard termination-status API for success, codes, and platform-specific signal details. Security and operations tools should distinguish a completed check with findings from a process that failed to execute or finish. | Intermediate | 15 minutes |
| Reference | BashFAQ/105 — Why does `set -e` behave unexpectedly? | <https://mywiki.wooledge.org/BashFAQ/105> | This focused community reference earns its place by documenting the exception-heavy semantics and portability traps of `errexit` that simplistic “strict mode” articles omit. | Advanced | 30 minutes |
| Article | Timeouts, retries, and backoff with jitter | <https://builder.aws.com/content/3EumjoZascWd1oZiEgL8ORlv3qE/timeouts-retries-and-backoff-with-jitter> | Amazon’s primary engineering guidance connects timeout selection, bounded retries, exponential backoff, jitter, and retry multiplication across layers for resilient API clients. | Advanced | 35 minutes |

## Testing and Code Quality

Build confidence with unit, integration, property, fuzz, CLI, TUI, snapshot, concurrency, browser, and end-to-end tests, backed by formatting and static analysis.

**Useful prerequisites:** The relevant language's functions, modules, and error model.

**Project connection:** Testing or quality tooling appeared in 60 repositories and GitHub Actions in 48. Fixtures, temporary files, contract tests, snapshots, parsers, concurrency, and release gates are recurring needs.

**Suggested order:** Start with native unit and integration tests, add table/parameterized cases, then properties and fuzzing at parsers, deterministic UI/CLI tests, concurrency controls, and CI release gates.

**Continue with:** [Git, GitHub, Automation, and Developer Tooling](#git-github-automation-and-developer-tooling), [Advanced and Cross-Cutting Topics](#advanced-and-cross-cutting-topics).

### Project-derived concept notes

- Cross-stack agent, MCP, PTY, browser, and JavaScript workflows still lack one durable end-to-end testing curriculum. Keep project-owned fixtures that test cancellation, approval, stream finalization, malformed tool data, terminal restoration, and browser-origin boundaries together.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Book | Writing Automated Tests — The Rust Programming Language | <https://doc.rust-lang.org/book/ch11-00-testing.html> | The official chapter introduces assertions, expected panics, `Result`-returning tests, filtering, ignored tests, and the distinction between unit and integration tests. | Beginner | 1–2 hours |
| Official documentation | ShellCheck | <https://www.shellcheck.net/> | The project’s rule catalog turns common quoting, globbing, pipeline, portability, and data-flow mistakes into actionable diagnostics and explanations. | Beginner | 45 minutes |
| Official documentation | Tests — The Cargo Book | <https://doc.rust-lang.org/cargo/guide/tests.html> | Cargo’s guide explains the actual layout and execution of unit, integration, and documentation tests, complementing the language-level testing chapter with build-tool behavior. | Intermediate | 45 minutes |
| Reference | `testing` — Go standard library | <https://pkg.go.dev/testing> | The canonical package reference covers tests, benchmarks, examples, subtests, cleanup, parallel execution, and native fuzz targets in the form the `go` tool actually discovers. | Intermediate | 1–2 hours |
| Official documentation | Go Fuzzing | <https://go.dev/doc/security/fuzz/> | The Go team’s guide provides the end-to-end native fuzzing workflow, corpus handling, minimization, and regression promotion needed for parsers and protocol boundaries. | Intermediate | 1 hour |
| Reference | `io.Writer` — Go standard library | <https://pkg.go.dev/io#Writer> | This tiny interface is a high-leverage design seam: accepting a writer instead of hard-coding stdout makes CLI output composable and directly testable. | Intermediate | 20 minutes |
| Reference | `unittest` — Unit testing framework | <https://docs.python.org/3/library/unittest.html> | Python’s built-in framework reference covers fixtures, assertions, subtests, discovery, cleanup, mocking integration, and command-line execution with no third-party dependency. | Intermediate | 1–2 hours |
| Official documentation | pytest documentation | <https://docs.pytest.org/en/stable/> | Maintainer documentation provides the practical Python testing path for plain assertions, fixtures, parametrization, temporary paths, monkeypatching, plugins, and test selection. | Intermediate | 3–4 hours |
| Official documentation | Bats-core documentation | <https://bats-core.readthedocs.io/en/stable/> | Bats supplies a maintained TAP-producing harness for executable Bash and Unix CLI behavior, including setup, teardown, helpers, file-descriptor caveats, and CI use. | Intermediate | 2 hours |
| Official documentation | Proptest | <https://proptest-rs.github.io/proptest/intro.html> | The project’s guide adds generated inputs, shrinking, failure persistence, and state-machine testing for parsers and deterministic cores where example-based Rust tests leave gaps. | Advanced | 2–3 hours |
| Official documentation | Hypothesis documentation | <https://hypothesis.readthedocs.io/en/latest/> | Hypothesis adds property-based generation, shrinking, reproducible failures, and stateful testing for round trips and parser invariants that hand-picked examples miss. | Advanced | 3–4 hours |

## Async Programming and Concurrency

Reason about futures, tasks, goroutines, threads, channels, queues, cancellation, synchronization, backpressure, and the cost of blocking work.

**Useful prerequisites:** Strong command of one language's ownership or object model plus error propagation.

**Project connection:** Twenty-five repositories explicitly map here and 21 use async or concurrency concepts, including streaming providers, parallel DAG steps, watchers, background UI work, servers, and bounded pipelines.

**Suggested order:** Learn the runtime's task model, then cancellation and shutdown, shared state, bounded channels, blocking bridges, memory-order rules, and workload-specific concurrency tests.

**Continue with:** [Performance and Resource Efficiency](#performance-and-resource-efficiency), [Error Handling and Reliability](#error-handling-and-reliability).

### Project-derived concept notes

- The Rust Async Book still marks some coverage incomplete. For runtime-neutral cancellation, fairness, structured task ownership, and shutdown semantics, pair it with the Tokio guides and record runtime-specific behavior in project tests.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Book | Asynchronous Programming in Rust | <https://rust-lang.github.io/async-book/> | The Rust project’s Async Book explains futures, `async`/`await`, executors, pinning, streams, and cancellation semantics beneath any one runtime; unfinished guide chapters are explicitly marked. | Intermediate | 5–7 hours |
| Official documentation | Tokio Tutorial | <https://tokio.rs/tokio/tutorial> | Tokio’s maintained tutorial provides the practical runtime path through spawning, shared state, channels, I/O, framing, `select!`, streams, and graceful shutdown. | Intermediate | 5–7 hours |
| Official documentation | Graceful Shutdown — Tokio | <https://tokio.rs/tokio/topics/shutdown> | This focused guide connects shutdown detection, cancellation tokens, and task tracking into a complete termination protocol instead of leaving background tasks orphaned. | Intermediate | 40 minutes |
| Reference | `context` — Go standard library | <https://pkg.go.dev/context> | The standard contract for deadlines and cancellation across API boundaries explains propagation, `Done`, causes, and why contexts must not be stored casually in structs. | Intermediate | 1 hour |
| Blog | Go Concurrency Patterns: Pipelines and cancellation | <https://go.dev/blog/pipelines> | The Go team develops fan-out, fan-in, channel closure, cancellation, and goroutine-leak prevention as one worked design rather than isolated syntax examples. | Intermediate | 45 minutes |
| Reference | `os/signal.NotifyContext` — Go standard library | <https://pkg.go.dev/os/signal#NotifyContext> | `NotifyContext` turns SIGINT and SIGTERM into composable cancellation and makes graceful CLI shutdown easier to coordinate than hand-managed signal channels. | Intermediate | 20 minutes |
| Reference | `threading` — Thread-based parallelism | <https://docs.python.org/3/library/threading.html> | The standard reference covers thread lifecycle, locks, conditions, events, semaphores, barriers, exception hooks, and the GIL limits that shape appropriate use. | Intermediate | 2–3 hours |
| Reference | `queue` — Synchronized queue classes | <https://docs.python.org/3/library/queue.html> | Python’s queue reference supplies bounded producer-consumer coordination, task completion, priority queues, and modern shutdown semantics without hand-rolled locking. | Intermediate | 1 hour |
| Reference | `tokio` — Rust API documentation | <https://docs.rs/tokio/latest/tokio/> | The versioned crate reference is the authoritative lookup for runtime configuration, task and synchronization primitives, time, signals, process management, and feature flags. | Advanced | Ongoing reference |
| Official documentation | Bridging with sync code — Tokio | <https://tokio.rs/tokio/topics/bridging> | Tokio’s guidance shows when to own a runtime, use `spawn_blocking`, choose runtime flavors, and keep blocking work from stalling asynchronous executors. | Advanced | 35 minutes |
| Reference | The Go Memory Model | <https://go.dev/ref/mem> | The normative happens-before rules clarify what channels, locks, atomics, and goroutine creation actually synchronize, and why race-free design is the baseline. | Advanced | 1–2 hours |
| Official documentation | Coroutines and Tasks — Python `asyncio` | <https://docs.python.org/3/library/asyncio-task.html> | The official guide covers coroutine scheduling, task groups, cancellation, timeouts, shielding, cross-thread submission, and the failure behavior of structured concurrency. | Advanced | 2–3 hours |

## Data, Storage, Search, and File Processing

Model and validate JSON/YAML contracts, use SQLite safely, stream archives and compression, hash and classify content, traverse filesystems, extract metadata, and persist state deliberately.

**Useful prerequisites:** Language I/O, errors, and basic data structures.

**Project connection:** Sixty-one repositories process files or data; recurring families include JSON, YAML, SQLite/FTS5, archives, hashing, metadata, XDG paths, atomic replacement, file watching, and document builds.

**Suggested order:** Start with formats and typed serialization, continue through SQLite transactions and search, then streaming files and archives, metadata and traversal, filesystem durability, locking, and reproducible document pipelines.

**Continue with:** [Performance and Resource Efficiency](#performance-and-resource-efficiency), [Security and Linux Operations](#security-and-linux-operations).

### Project-derived concept notes

- Timeshift's exact snapshot discovery and retention behavior lacks a stable, detailed upstream teaching resource. Treat its on-disk layout and command output as a versioned external contract and verify behavior against fixtures before deleting snapshots.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Reference | `infer` — Rust API documentation | <https://docs.rs/infer/latest/infer/> | The implementation reference provides magic-byte detection and extension/MIME results while making clear that signatures cover a finite format set. | Beginner | 30 minutes |
| Reference | `mime_guess` — Rust API documentation | <https://docs.rs/mime_guess/latest/mime_guess/> | This extension-based MIME lookup complements signature detection and explicitly exposes ambiguity and fallback behavior rather than promising authoritative content identification. | Beginner | 20 minutes |
| Reference | `serde` — Rust API documentation | <https://docs.rs/serde/latest/serde/> | The versioned API reference is the ongoing implementation lookup for `Serialize`, `Deserialize`, derive support, data formats, and feature flags. | Intermediate | Ongoing reference |
| Reference | `serde_json` — Rust API documentation | <https://docs.rs/serde_json/latest/serde_json/> | The canonical crate reference covers typed and untyped JSON, stream-oriented readers and writers, error classification, raw values, and arbitrary-precision options. | Intermediate | 1 hour |
| Reference | `zstd` — Rust API documentation | <https://docs.rs/zstd/latest/zstd/> | Maintainer API documentation shows streaming encoders and decoders, dictionary use, compression levels, and the `Read`/`Write` adapters used in bounded-memory pipelines. | Intermediate | 1 hour |
| Reference | `tar` — Rust API documentation | <https://docs.rs/tar/latest/tar/> | The crate reference documents streaming archive traversal and creation, path handling, headers, sparse files, and the security-sensitive choice not to extract blindly. | Intermediate | 1 hour |
| Reference | `std::io` — Rust standard library | <https://doc.rust-lang.org/std/io/index.html> | The primary reference explains composable `Read`, `Write`, `BufRead`, cursors, adapters, error kinds, and copying for streaming pipelines. | Intermediate | 1–2 hours |
| Reference | `BufReader` in `std::io` | <https://doc.rust-lang.org/std/io/struct.BufReader.html> | This focused reference teaches when buffering reduces small-read system calls, how capacity affects behavior, and when multiple wrappers can discard buffered data. | Intermediate | 30 minutes |
| Reference | `rusqlite` — Rust API documentation | <https://docs.rs/rusqlite/latest/rusqlite/> | The maintained binding reference covers connections, prepared statements, transactions, backup, hooks, feature flags, and bundled SQLite/FTS5 builds. | Intermediate | 2 hours |
| Official documentation | Transaction — SQLite | <https://www.sqlite.org/lang_transaction.html> | SQLite's transaction contract explains implicit versus explicit transactions, deferred/immediate/exclusive starts, upgrade failures, nesting limits, and commit behavior. | Intermediate | 45 minutes |
| Official documentation | Uniform Resource Identifiers — SQLite | <https://www.sqlite.org/uri.html> | This reference documents `mode=ro`, immutable and shared-cache URI parameters, percent encoding, and the opt-in rules needed for deliberate read-only database access. | Intermediate | 30 minutes |
| Official documentation | Query Planning — SQLite | <https://www.sqlite.org/queryplanner.html> | The official planner tutorial makes index selection, multi-column and covering indexes, sorting, and `ANALYZE` concrete enough to design measured search schemas. | Intermediate | 1–2 hours |
| Reference | `blake3` — Rust API documentation | <https://docs.rs/blake3/latest/blake3/> | The crate reference covers incremental and memory-mapped hashing, keyed and derive-key modes, Rayon integration, output readers, and constant-time comparison concerns. | Intermediate | 1 hour |
| Reference | `walkdir` — Rust API documentation | <https://docs.rs/walkdir/latest/walkdir/> | The traversal reference covers pruning, depth bounds, symlink following, same-filesystem limits, descriptor pressure, deterministic sorting, and per-entry errors. | Intermediate | 45 minutes |
| Reference | `Metadata` in `std::fs` | <https://doc.rust-lang.org/std/fs/struct.Metadata.html> | The standard-library contract clarifies file type, length, timestamps, permissions, platform extensions, and why metadata observations can race subsequent operations. | Intermediate | 30 minutes |
| Reference | `exif` — Rust API documentation | <https://docs.rs/kamadak-exif/latest/exif/> | The crate API explains EXIF/TIFF container parsing, tag lookup, field values, endian handling, and safe read-only metadata extraction from supported formats. | Intermediate | 1 hour |
| Reference | `pdf_extract` — Rust API documentation | <https://docs.rs/pdf-extract/latest/pdf_extract/> | The crate reference documents pure-Rust PDF text extraction and its error surface; it is an implementation option, not a promise of layout-faithful or OCR output. | Intermediate | 30 minutes |
| Reference | `calamine` — Rust API documentation | <https://docs.rs/calamine/latest/calamine/> | Maintainer documentation covers workbook discovery, sheet and cell iteration, formulas, date values, ranges, and supported spreadsheet containers. | Intermediate | 1 hour |
| Reference | `quick_xml` — Rust API documentation | <https://docs.rs/quick-xml/latest/quick_xml/> | The streaming XML reference teaches event-based parsing, encoding, Serde integration, namespace handling, and bounded-memory extraction from XML-based office archives. | Intermediate | 1–2 hours |
| Reference | XDG Base Directory Specification | <https://specifications.freedesktop.org/basedir/latest/> | The normative Linux desktop contract defines config, data, state, cache, runtime, and search directories, including absolute-path and security requirements. | Intermediate | 30 minutes |
| Official documentation | fsnotify | <https://github.com/fsnotify/fsnotify> | Maintainer documentation describes cross-platform filesystem notifications, recursive-watch limitations, event behavior, buffering, and platform caveats needed before building debounce or coalescing logic. | Intermediate | 1 hour |
| Reference | asciicast v2 | <https://docs.asciinema.org/manual/asciicast/v2/> | The official line-oriented JSON format specifies headers, timed output/input/marker events, environment fields, and streaming properties for terminal recording libraries. | Intermediate | 45 minutes |
| Reference | Pandoc User's Guide | <https://pandoc.org/MANUAL.html> | The authoritative manual supports reproducible document conversion through explicit readers, writers, metadata, templates, filters, resource paths, and PDF-engine selection. | Intermediate | 2–3 hours |
| Reference | `shutil.copy2` — Python standard library | <https://docs.python.org/3/library/shutil.html#shutil.copy2> | The standard contract explains content-plus-metadata copying, platform limitations, symlink behavior, and non-atomic failure modes for recovery-oriented copy tools. | Intermediate | 30 minutes |
| Reference | RFC 8259: The JavaScript Object Notation (JSON) Data Interchange Format | <https://www.rfc-editor.org/rfc/rfc8259> | The normative JSON grammar and interoperability rules settle edge cases around numbers, strings, duplicate names, encodings, and parser limits. | Advanced | 1 hour |
| Reference | YAML Ain't Markup Language (YAML) version 1.2.2 | <https://yaml.org/spec/1.2.2/> | The language specification distinguishes YAML's representation, serialization, presentation, tag, anchor, and schema rules from library-specific behavior. | Advanced | 2–3 hours |
| Reference | JSON Schema Specification | <https://json-schema.org/specification> | The official specification hub supports durable local data and tool contracts through validation vocabularies, reusable schemas, identifiers, and versioned dialects. | Advanced | 2–3 hours |
| Reference | RFC 8878: Zstandard Compression and the `application/zstd` Media Type | <https://www.rfc-editor.org/rfc/rfc8878.html> | The format specification is the durable source for frame structure, decoding limits, checksums, skippable frames, and interoperability beyond one crate. | Advanced | 2 hours |
| Official documentation | Write-Ahead Logging — SQLite | <https://www.sqlite.org/wal.html> | The authoritative WAL guide explains reader/writer concurrency, checkpoints, durability trade-offs, read-only WAL requirements, and cases where rollback journals remain preferable. | Advanced | 1 hour |
| Official documentation | SQLite FTS5 Extension | <https://www.sqlite.org/fts5.html> | The complete primary guide covers query syntax, tokenizers, prefix indexes, BM25, snippets, contentless/external-content designs, maintenance commands, and storage trade-offs. | Advanced | 3–4 hours |
| Official documentation | Atomic Commit In SQLite | <https://www.sqlite.org/atomiccommit.html> | This design document connects journals, locking, flush ordering, sector assumptions, and failure recovery, making transaction durability a systems concept rather than a magic property. | Advanced | 2 hours |
| Blog | Towards Inserting One Billion Rows in SQLite Under A Minute | <https://avi.im/blag/2021/fast-sqlite-inserts/> | This retained community benchmark adds a distinct measured lesson: transaction batching and prepared-statement reuse dominate, while unsafe PRAGMAs trade away durability and must not be copied into production blindly. | Advanced | 30 minutes |
| Official documentation | BLAKE3 — official implementations and specification | <https://github.com/BLAKE3-team/BLAKE3> | The project repository links the specification, design paper, official implementations, test vectors, benchmarks, and security notes needed to evaluate content-addressing choices. | Advanced | 1–2 hours |
| Official documentation | ExifTool by Phil Harvey | <https://exiftool.org/> | The maintainer site supplies broad RAW, image, video, PDF, and office metadata coverage plus application/API documentation that a narrow EXIF crate cannot. | Advanced | 2–3 hours |
| Reference | `rename(2)` — Linux manual page | <https://man7.org/linux/man-pages/man2/rename.2.html> | The system-call contract explains atomic replacement, no-replace/exchange variants, cross-filesystem failure, NFS caveats, and why atomic visibility is not crash durability. | Advanced | 45 minutes |
| Reference | `fsync(2)` — Linux manual page | <https://man7.org/linux/man-pages/man2/fsync.2.html> | The primary Linux reference distinguishes data and metadata flushing and states the often-missed requirement to sync the containing directory for durable name changes. | Advanced | 30 minutes |
| Reference | `flock(2)` — Linux manual page | <https://man7.org/linux/man-pages/man2/flock.2.html> | The advisory-lock contract covers shared/exclusive/nonblocking locks, descriptor semantics, inheritance, and network-filesystem caveats for multi-process stores. | Advanced | 30 minutes |
| Reference | `statvfs(3)` — Linux manual page | <https://man7.org/linux/man-pages/man3/statvfs.3.html> | The standards-oriented filesystem-statistics API explains block and inode capacity, available-space semantics, read-only flags, and portability limits for disk monitors. | Advanced | 30 minutes |

## Performance and Resource Efficiency

Measure before optimizing and connect profiling evidence to buffering, batching, allocation, database transactions, parallelism, zero-copy buffers, caching, backpressure, and resource limits.

**Useful prerequisites:** A correct tested implementation plus familiarity with its I/O and concurrency model.

**Project connection:** Twenty-nine repositories map to performance; seven use explicit resource controls. Large archives, search indexes, terminal rendering, image libraries, monitors, containers, and interactive loops all need bounded work.

**Suggested order:** Profile first, build reproducible benchmarks, improve algorithm or batching choices, then consider parallelism, zero-copy techniques, caches, and host/container limits while rechecking correctness.

**Continue with:** [Async Programming and Concurrency](#async-programming-and-concurrency), [Advanced and Cross-Cutting Topics](#advanced-and-cross-cutting-topics).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Book | The Rust Performance Book | <https://nnethercote.github.io/perf-book/introduction.html> | This measurement-first guide moves from profiling to build configuration, allocation, hashing, I/O, code generation, and parallelism while warning against intuition-only optimization. | Intermediate | 5–7 hours |
| Official documentation | Criterion.rs Documentation | <https://bheisler.github.io/criterion.rs/book/index.html> | The maintainer book teaches statistically informed microbenchmarks, warm-up and measurement settings, plots, baselines, regression detection, async timing, and profiler integration. | Intermediate | 2–3 hours |
| Official documentation | Flamegraph for Rust projects | <https://github.com/flamegraph-rs/flamegraph> | The project documentation provides a practical sampling-profiler workflow and records platform prerequisites, debug-symbol needs, permissions, and interpretation limits. | Intermediate | 45 minutes |
| Reference | `rayon` — Rust API documentation | <https://docs.rs/rayon/latest/rayon/> | The canonical reference covers parallel iterators, work stealing, custom thread pools, scoped tasks, fallible processing, ordering, and cases where parallel overhead outweighs work. | Intermediate | 1–2 hours |
| Official documentation | Channels — Tokio Tutorial | <https://tokio.rs/tokio/tutorial/channels> | The worked bounded-channel design demonstrates backpressure, single-owner resource tasks, request/response handoff, and why unbounded producer growth is a resource bug. | Intermediate | 45 minutes |
| Official documentation | `st.cache_data` — Streamlit | <https://docs.streamlit.io/develop/api-reference/caching-and-state/st.cache_data> | This focused implementation reference documents TTL, entry bounds, persistence, hashing, copying, invalidation, and the security implications of pickle-backed cached data. | Intermediate | 45 minutes |
| Reference | `bytes` — Rust API documentation | <https://docs.rs/bytes/latest/bytes/> | The buffer API makes zero-copy trade-offs concrete through reference-counted slicing, `BytesMut`, cursor traits, shared allocation, and the distinction from fallible I/O operations. | Advanced | 1 hour |

## Security and Linux Operations

Operate Linux with least privilege and recovery paths: SSH, firewalls, Tailscale authorization, kernel tunables, secrets, containers, backups, scheduling, block devices, sanitization, and SMTP.

**Useful prerequisites:** Comfort with Linux files, processes, networking, and a local recovery console or tested rollback method.

**Project connection:** Sixty-two repositories map to security or Linux operations. Hardening, backups, networking, container boundaries, secret-safe automation, removable media, monitoring, and system services recur across the account.

**Suggested order:** Begin with the distribution security baseline and least privilege; prove SSH/network recovery before firewall changes; study exact upstream manuals; then add backups and restore tests, container boundaries, scheduling, and destructive-media threat models.

**Continue with:** [Git, GitHub, Automation, and Developer Tooling](#git-github-automation-and-developer-tooling), [Error Handling and Reliability](#error-handling-and-reliability).

### Project-derived concept notes

- Safe removable-media writing still deserves a project lab that combines signature verification, `lsblk` identity, mount checks, explicit destructive confirmation, post-write verification, interruption handling, and recovery from selecting the wrong target.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | Firewall | <https://ubuntu.com/server/docs/how-to/security/firewalls/> | Ubuntu's current UFW guide explains rule ordering, application profiles, logging, and dry-run inspection. Keep an existing administrative session open and validate the replacement path before changing remote-access rules. | Beginner | 20 minutes |
| Official documentation | Install Tailscale on Linux | <https://tailscale.com/docs/install/linux> | The maintained installation route for supported Linux distributions, including package setup, authentication, and service startup. It replaces versioned knowledge-base URLs that have moved. | Beginner | 10 minutes |
| Reference | mountpoint(1) | <https://man7.org/linux/man-pages/man1/mountpoint.1.html> | The upstream-derived command contract for testing whether a directory is a mount point, following symlinks deliberately, and using exit status in scripts. A backup job should verify both the mount and the expected source device before writing. | Beginner | 15 minutes |
| Reference | crontab guru | <https://crontab.guru/> | A focused interactive explainer for the common five-field cron expression. Use it to visualize a schedule, then confirm implementation-specific features and environment behavior in the crontab manual. | Beginner | 10 minutes |
| Reference | Sign in with app passwords | <https://support.google.com/mail/answer/185833?hl=en> | Google's current requirements and limitations for app passwords, including two-step verification and cases where the option is unavailable. Prefer OAuth where supported and never place the credential in a repository. | Beginner | 10 minutes |
| Official documentation | Security suggestions | <https://ubuntu.com/server/docs/explanation/security/security_suggestions/> | A distribution-maintained security baseline covering updates, least privilege, firewalls, SSH, AppArmor, and operational trade-offs. Use it to build a threat-modelled checklist instead of copying an unreviewed hardening script. | Intermediate | 25 minutes |
| Article | Linux server hardening: most important steps to secure systems | <https://linux-audit.com/linux-server-hardening-most-important-steps-to-secure-systems/> | A maintained community companion that organizes hardening as inventory, minimization, configuration, auditing, and verification rather than a bag of sysctl values. Use the upstream manuals for exact directives and validate each change against the host's workload. | Intermediate | 30 minutes |
| Official documentation | Secure an Ubuntu server using Tailscale and UFW | <https://tailscale.com/docs/how-to/secure-ubuntu-server-with-ufw> | Shows a supported deny-by-default pattern that preserves management through Tailscale. It is especially useful for avoiding the common lockout caused by enabling UFW before proving the overlay-network path. | Intermediate | 20 minutes |
| Reference | Tailscale CLI | <https://tailscale.com/docs/reference/tailscale-cli> | The complete command reference for connecting, inspecting, debugging, and changing a node. Check command effects here before scripting state-changing operations. | Intermediate | 30 minutes |
| Official documentation | Access control | <https://tailscale.com/docs/features/access-control> | Explains Tailscale grants, ACL policy, groups, tags, users, and device identity as one authorization model. It is the starting point for replacing broad network trust with least-privilege connectivity. | Intermediate | 25 minutes |
| Official documentation | Tailscale SSH | <https://tailscale.com/docs/reference/ssh-over-tailscale> | Documents how Tailscale SSH authentication and authorization differ from ordinary OpenSSH. It helps prevent accidentally assuming that network reachability alone grants shell access. | Intermediate | 25 minutes |
| Reference | sysctl(8) | <https://man7.org/linux/man-pages/man8/sysctl.8.html> | Documents safe reading, writing, pattern matching, and system-wide loading of kernel parameters. Read current values first and stage changes so they can be reverted from a local console. | Intermediate | 20 minutes |
| Reference | Secrets Management Cheat Sheet | <https://cheatsheetseries.owasp.org/cheatsheets/Secrets_Management_Cheat_Sheet.html> | A durable lifecycle guide for creation, storage, least privilege, rotation, auditing, CI/CD injection, leak detection, and incident response. It is a strong cross-tool baseline for API keys, SSH keys, SMTP credentials, and build secrets. | Intermediate | 50 minutes |
| Reference | OS Command Injection Defense Cheat Sheet | <https://cheatsheetseries.owasp.org/cheatsheets/OS_Command_Injection_Defense_Cheat_Sheet.html> | Explains why structured process APIs, argument separation, allowlists, and input validation are safer than constructing shell strings. It directly supports CLIs that execute local or remote commands. | Intermediate | 25 minutes |
| Official documentation | Docker Engine security | <https://docs.docker.com/engine/security/> | Covers the daemon trust boundary, Linux namespaces, control groups, capabilities, and the security implications of daemon access. It corrects the dangerous assumption that a container is automatically a strong sandbox. | Intermediate | 35 minutes |
| Official documentation | Rootless mode | <https://docs.docker.com/engine/security/rootless/> | Shows how to run both the Docker daemon and containers inside a user namespace, with prerequisites and limitations. It is a practical least-privilege option for development and homelab workloads. | Intermediate | 25 minutes |
| Official documentation | Build secrets | <https://docs.docker.com/build/building/secrets/> | Documents secret and SSH mounts that avoid persisting credentials in image layers or build arguments. Use it for authenticated dependency fetches and private builds. | Intermediate | 20 minutes |
| Official documentation | Resource constraints | <https://docs.docker.com/engine/containers/resource_constraints/> | Explains memory, swap, CPU, and real-time limits and the host risk of leaving containers unbounded. It supports capacity planning for self-hosted CI and monitoring stacks. | Intermediate | 30 minutes |
| Official documentation | Image verification | <https://documentation.ubuntu.com/security/software-integrity/image-verification/> | Explains signature-backed verification of Ubuntu images and why a bare checksum downloaded from the same compromised source is insufficient. Use it before any destructive removable-media write. | Intermediate | 20 minutes |
| Reference | lsblk(8) | <https://man7.org/linux/man-pages/man8/lsblk.8.html> | The current util-linux reference for stable block-device inspection and machine-readable columns. Scripts should explicitly request fields and verify type, transport, mount state, and target identity before any write. | Intermediate | 25 minutes |
| Reference | findmnt(8) | <https://man7.org/linux/man-pages/man8/findmnt.8.html> | Documents reliable queries against mount tables and /proc mount information, with explicit output columns and filters. It is safer for automation than parsing the human-oriented output of mount. | Intermediate | 25 minutes |
| Reference | realpath(1) | <https://man7.org/linux/man-pages/man1/realpath.1.html> | Documents canonical and relative path resolution, missing components, symlink behavior, delimiters, and error status. It helps scheduled jobs avoid assumptions about their working directory, but it does not expand a shell tilde passed as a literal. | Intermediate | 20 minutes |
| Official documentation | #StopRansomware Guide | <https://www.cisa.gov/stopransomware/ransomware-guide> | CISA's recovery guidance emphasizes offline encrypted backups and regular integrity and restore tests. It turns a file-copy routine into a verifiable recovery practice. | Intermediate | 25 minutes |
| Reference | crontab(5) | <https://man7.org/linux/man-pages/man5/crontab.5.html> | Explains cron's restricted environment, time semantics, mail behavior, and command parsing. It helps make non-interactive jobs reproducible instead of testing whether a shell happens to be attached. | Intermediate | 25 minutes |
| Reference | systemd.timer(5) | <https://www.freedesktop.org/software/systemd/man/latest/systemd.timer.html> | The official timer-unit reference covers monotonic and calendar schedules, persistence, accuracy, dependencies, and randomized delay. Pair it with a service unit when you need logged, inspectable Linux scheduling. | Intermediate | 35 minutes |
| Reference | Desktop Entry Specification | <https://specifications.freedesktop.org/desktop-entry/latest/> | The normative cross-desktop format for application launchers, actions, localization, field codes, validation, and security-sensitive execution fields. It replaces trial-and-error launcher recipes. | Intermediate | 40 minutes |
| Reference | Desktop Application Autostart Specification | <https://specifications.freedesktop.org/autostart/latest/> | Defines how desktop-session autostart entries are discovered, enabled, disabled, and overridden. It is the durable basis for packaging background tray processes without surprising users. | Intermediate | 20 minutes |
| Reference | ln invocation | <https://www.gnu.org/software/coreutils/manual/coreutils.html#ln-invocation> | The GNU reference for hard and symbolic links, replacement behavior, relative targets, backups, and portability. It exposes why ln -sf alone is not a complete idempotent reconciliation strategy. | Intermediate | 20 minutes |
| Reference | at(1) | <https://manpages.ubuntu.com/manpages/noble/man1/at.1.html> | Documents one-shot at and batch jobs, queue inspection, deletion, environment capture, mail, permissions, and parsing. Generated jobs still require strict quoting and an explicit cancellation strategy. | Intermediate | 20 minutes |
| Reference | msmtp manual | <https://marlam.de/msmtp/msmtp.html> | The upstream manual covers account selection, TLS verification, authentication, sendmail mode, passwordeval, logging, and exit codes. Use a secret helper with restrictive permissions rather than embedding credentials in configuration. | Intermediate | 45 minutes |
| Reference | msmtp | <https://wiki.archlinux.org/title/Msmtp> | A high-quality community integration guide for system and user configuration, mail aliases, secret helpers, and common client setups. Cross-check option semantics against the upstream manual. | Intermediate | 25 minutes |
| Reference | Grants syntax | <https://tailscale.com/docs/reference/syntax/grants> | The authoritative syntax and semantics for grants, including selectors and application capabilities. Pair it with policy tests and a rollback plan before deploying changes. | Advanced | 30 minutes |
| Reference | sshd_config(5) | <https://man.openbsd.org/sshd_config.5> | The upstream OpenSSH server-configuration reference, including precedence, Match blocks, authentication controls, forwarding, and safe syntax validation. Test with sshd -t and keep a recovery session before reloading a remote daemon. | Advanced | 50 minutes |
| Reference | sshd(8) | <https://man.openbsd.org/sshd.8> | The upstream daemon manual explains startup, authentication flow, authorized keys, privilege separation, signals, and exit behavior. It provides the context needed to reason about sshd_config rather than treating directives as magic switches. | Advanced | 45 minutes |
| Official documentation | Linux kernel sysctl documentation | <https://www.kernel.org/doc/html/latest/admin-guide/sysctl/index.html> | The kernel-maintained index for runtime tunables. Use it to confirm that a parameter exists on the running kernel and understand its subsystem before changing a copied hardening value. | Advanced | 35 minutes |
| Reference | IP Sysctl | <https://www.kernel.org/doc/html/latest/networking/ip-sysctl.html> | The authoritative meanings and defaults for IPv4 and IPv6 networking tunables, including per-interface all/default behavior. This is the primary source for evaluating network-hardening recommendations. | Advanced | 70 minutes |
| Official documentation | Kernel Self-Protection | <https://www.kernel.org/doc/html/latest/security/self-protection.html> | Explains the kernel project's security design goals and the distinction between attack-surface reduction, exploit prevention, and hardening. It gives sysctl and build-time controls a threat-modelled context. | Advanced | 35 minutes |
| Reference | kernel sysctl: modules_disabled | <https://www.kernel.org/doc/html/latest/admin-guide/sysctl/kernel.html> | The kernel-maintained semantics for module loading and other kernel namespace tunables. Setting modules_disabled is one-way until reboot, so verify every required driver and recovery path before using it. | Advanced | 25 minutes |
| Reference | Operational state of a network interface | <https://www.kernel.org/doc/Documentation/ABI/testing/sysfs-class-net> | The kernel ABI definition for interface operstate, carrier, dormant, testing, and related sysfs attributes. It prevents monitoring tools from guessing status from filenames or display text. | Advanced | 20 minutes |
| Reference | Security: kernel hardening | <https://wiki.archlinux.org/title/Security#Kernel_hardening> | An actively maintained community reference that connects kernel parameters, lockdown, module policy, and distribution configuration. Treat it as implementation context and confirm exact tunables in kernel documentation. | Advanced | 35 minutes |
| Reference | sysctl.d(5) | <https://man7.org/linux/man-pages/man5/sysctl.d.5.html> | Explains persistent sysctl file precedence, naming, exclusions, and boot-time application. It is essential for avoiding settings that appear correct interactively but are overwritten at reboot. | Advanced | 25 minutes |
| Reference | sudoers(5) | <https://man7.org/linux/man-pages/man5/sudoers.5.html> | The detailed sudo policy reference for command matching, tags, environment handling, logging, and include order. Validate edits with visudo and grant the smallest command surface required. | Advanced | 60 minutes |
| Reference | podman(1) | <https://docs.podman.io/en/latest/markdown/podman.1.html> | The upstream Podman reference explains rootless user namespaces, storage, networking, remote clients, and important filesystem limitations. It is the right starting point for understanding what host data a monitoring container can actually observe. | Advanced | 55 minutes |
| Official documentation | Guidelines for Media Sanitization: NIST SP 800-88 Rev. 2 | <https://csrc.nist.gov/pubs/sp/800/88/r2/final> | The current NIST guidance distinguishes clear, purge, and destroy methods and ties sanitization to media type and risk. It is the durable threat-model reference for why file overwrites cannot promise secure deletion on SSDs, copy-on-write filesystems, or remapped storage. | Advanced | 90 minutes |
| Reference | systemd.resource-control(5) | <https://www.freedesktop.org/software/systemd/man/latest/systemd.resource-control.html> | The official cgroup-backed reference for limiting CPU, memory, I/O, tasks, and device access for services and slices. It supports capacity controls beyond container-specific flags. | Advanced | 60 minutes |
| Reference | Domain XML format: Filesystems | <https://libvirt.org/formatdomain.html#filesystems> | The authoritative libvirt schema for filesystem devices, driver options, access modes, ID mapping, and virtiofs configuration. Use it when generating or reviewing VM definitions. | Advanced | 40 minutes |

## Git, GitHub, Automation, and Developer Tooling

Use Git and hosting automation safely, manage credentials, build secure CI, mirror and back up repositories, operate Gitea/Woodpecker, package desktop integrations, manage dotfiles, and share VM files.

**Useful prerequisites:** Basic commits, branches, shell commands, and filesystem permissions.

**Project connection:** Sixty-eight repositories map here, with GitHub Actions in 48, packaging/deployment in 46, and Git/repository automation in 23. Gitea, GitHub CLI, XDG, Stow, libvirt, and release provenance are account-wide concerns.

**Suggested order:** Learn remotes and authentication, then credential helpers and the Git model, GitHub CLI and Actions security, mirroring and restore, desktop/XDG and dotfile conventions, and virtualization integration.

**Continue with:** [Security and Linux Operations](#security-and-linux-operations), [Testing and Code Quality](#testing-and-code-quality).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Article | How to use rsync to sync local and remote directories | <https://www.digitalocean.com/community/tutorials/how-to-use-rsync-to-sync-local-and-remote-directories> | A clear worked introduction to source/destination trailing slashes, archive mode, SSH transport, progress, and deletion. Use dry-run first and consult the upstream manual for production filters and failure semantics. | Beginner | 30 minutes |
| Official documentation | Integrating with the desktop | <https://developer.gnome.org/documentation/guidelines/maintainer/integrating.html> | GNOME's maintainer guide turns the desktop-entry specification into practical installation, icon, validation, and application-metadata steps. | Beginner | 15 minutes |
| Reference | notify-send(1) | <https://manpages.debian.org/trixie/libnotify-bin/notify-send.1.en.html> | A maintained manual for command-line desktop notifications, including urgency, expiry, icons, categories, hints, replacement, and actions. Remember that cron and system services may not have a user's D-Bus session. | Beginner | 10 minutes |
| Official documentation | About remote repositories | <https://docs.github.com/en/get-started/git-basics/about-remote-repositories> | Introduces remotes, fetch and push URLs, HTTPS versus SSH, and the security boundary between a local repository and a hosting service. | Beginner | 10 minutes |
| Official documentation | Managing remote repositories | <https://docs.github.com/en/get-started/git-basics/managing-remote-repositories> | Provides supported commands for adding, inspecting, renaming, changing, and removing remotes, with troubleshooting for common configuration mistakes. | Beginner | 15 minutes |
| Official documentation | Connecting to GitHub with SSH | <https://docs.github.com/en/authentication/connecting-to-github-with-ssh> | The canonical learning route for key generation, agent setup, account registration, connection testing, troubleshooting, and key lifecycle. It replaces duplicate third-party SSH recipes. | Beginner | 35 minutes |
| Book | Pro Git | <https://git-scm.com/book/en/v2> | The freely available canonical Git book builds a durable mental model from everyday snapshots and branches through internals, protocols, hooks, and administration. | Beginner | 12–16 hours |
| Reference | GitHub does dotfiles | <https://dotfiles.github.io/> | A durable community index of bootstrap patterns, bare repositories, symlink managers, templates, secret handling, and machine-specific configuration. Compare approaches here, then choose a reversible model with a documented recovery path. | Beginner | 25 minutes |
| Reference | GitHub CLI manual | <https://cli.github.com/manual/gh> | The canonical command index for authentication, repositories, issues, pull requests, Actions, releases, extensions, and API access. | Beginner | 30 minutes |
| Reference | gh repo create | <https://cli.github.com/manual/gh_repo_create> | The exact repository-creation flags for visibility, source pushes, remotes, templates, teams, and initialization. Review visibility and target owner before running it. | Beginner | 10 minutes |
| Official documentation | GitHub CLI quickstart | <https://docs.github.com/en/github-cli/github-cli/quickstart> | A short task-oriented introduction to authentication, repository operations, issues, pull requests, and command discovery. | Beginner | 15 minutes |
| Reference | rsync(1) | <https://rsync.samba.org/ftp/rsync/rsync.1.html> | The upstream, current rsync manual covers archive semantics, deletion, filters, partial transfers, remote shells, exit codes, and dry runs. Treat --delete and destination selection as destructive operations and prove restores separately. | Intermediate | 60 minutes |
| Reference | GNU Stow manual | <https://www.gnu.org/software/stow/manual/stow.html> | The upstream manual explains package trees, targets, conflict handling, adoption, ignore lists, simulation, and restowing. It supports reversible symlink-based dotfile management. | Intermediate | 50 minutes |
| Official documentation | Error: Permission denied (publickey) | <https://docs.github.com/en/authentication/troubleshooting-ssh/error-permission-denied-publickey> | A focused diagnostic flow for the most common GitHub SSH failure, including remote URL, identity, agent, and account checks. | Intermediate | 15 minutes |
| Reference | gitcredentials | <https://git-scm.com/docs/gitcredentials.html> | The official credential-helper model for HTTPS authentication, including matching rules and secure-storage integrations. It helps avoid tokens in remote URLs, scripts, or plaintext files. | Intermediate | 30 minutes |
| Official documentation | Mirror Repository | <https://docs.gitea.com/usage/repository/repo-mirror> | Gitea's supported pull and push mirror workflows, including authentication and explicit force-push risk. It provides a safer reference point for GitHub-to-Gitea synchronization. | Intermediate | 25 minutes |
| Official documentation | Installation with Docker | <https://docs.gitea.com/installation/install-with-docker> | The maintained container deployment guide covers persistent volumes, permissions, databases, SSH ports, rootless images, upgrades, and secret generation. | Intermediate | 45 minutes |
| Official documentation | Prometheus: Getting started | <https://prometheus.io/docs/prometheus/latest/getting_started/> | A durable introduction to scrape configuration, targets, queries, and expression browsing. Use it as the small verified starting point before expanding a monitoring stack's retention and resource footprint. | Intermediate | 35 minutes |
| Official documentation | Security for GitHub Actions | <https://docs.github.com/en/actions/concepts/security> | An official map of workflow permissions, secrets, OIDC, runner trust, dependency pinning, attestations, and compromise response. It supports fail-closed automation instead of treating CI YAML as harmless metadata. | Intermediate | 35 minutes |
| Reference | gh repo edit | <https://cli.github.com/manual/gh_repo_edit> | The exact flags for repository description, visibility, features, merge policy, default branch, archived state, and security settings. Visibility changes have broad consequences and require explicit confirmation. | Intermediate | 15 minutes |
| Reference | gh pr create | <https://cli.github.com/manual/gh_pr_create> | The pull-request creation reference, including base/head selection, draft status, templates, body files, recovery, and fork behavior. | Intermediate | 15 minutes |
| Official documentation | Sharing files with Virtiofs | <https://libvirt.org/kbase/virtiofs.html> | Libvirt's focused guide covers domain XML, shared-memory requirements, guest mounting, unprivileged mode, UID mapping, migration limits, and externally launched virtiofsd. It is more useful than obsolete QEMU virtiofsd documentation. | Advanced | 35 minutes |
| Official documentation | virtiofsd | <https://gitlab.com/virtio-fs/virtiofsd/-/blob/main/README.md> | The maintained Rust virtiofsd documentation covers invocation, sandboxing, privilege dropping, UID/GID mapping, read-only exports, limits, and QEMU wiring. It replaces the removed legacy daemon page in QEMU documentation. | Advanced | 40 minutes |
| Reference | systemd.mount(5) | <https://www.freedesktop.org/software/systemd/man/latest/systemd.mount.html> | The official mount-unit reference explains /etc/fstab generation, dependency rules, network mounts, automount interactions, and timeout behavior for managed shares. | Advanced | 35 minutes |
| Reference | git-clone | <https://git-scm.com/docs/git-clone.html> | The authoritative semantics for normal, bare, and mirror clones, refspecs, partial clones, submodules, and object sharing. Read the --mirror and --shared warnings before automating backups or synchronization. | Advanced | 45 minutes |
| Official documentation | Backup and Restore | <https://docs.gitea.com/usage/backup-and-restore> | Documents Gitea's database, repository, configuration, attachment, hook, Docker, and consistency requirements. A mirror is not a full service backup, so restore testing belongs beside mirroring. | Advanced | 35 minutes |
| Reference | virt-xml(1) | <https://manpages.ubuntu.com/manpages/noble/man1/virt-xml.1.html> | The command reference for safely editing libvirt domain XML non-interactively, including print, update, add, remove, define, and confirmation behavior. Preview changes before applying them to a running or irreplaceable guest. | Advanced | 30 minutes |
| Official documentation | Server configuration | <https://woodpecker-ci.org/docs/administration/configuration/server> | The current Woodpecker server reference covers forge OAuth, registration controls, databases, persistence, TLS, secrets, metrics, and resource limits for a self-hosted CI control plane. | Advanced | 60 minutes |
| Official documentation | Artifact attestations | <https://docs.github.com/en/actions/concepts/security/artifact-attestations> | Explains signed build provenance and verification for binaries and container images. It is useful for proving that a release came from the expected workflow and commit. | Advanced | 25 minutes |
| Reference | gh api | <https://cli.github.com/manual/gh_api> | Documents authenticated REST and GraphQL requests, pagination, typed fields, caching, templates, and previews for automation beyond dedicated gh subcommands. | Advanced | 35 minutes |

## Local AI and Related Tools

Integrate local and hosted models without confusing convenience with safety: understand model metadata and context limits, provider streams and tools, MCP architecture and authorization, evaluations, prompt injection, and agent extensions.

**Useful prerequisites:** HTTP/JSON, async streams, secrets, and a clear statement of which data may leave the machine.

**Project connection:** Twelve repositories map to local AI or agent tooling, including Ollama clients, multi-provider adapters, MCP servers, tool loops, skills, hooks, subagents, local bridges, and editorial workflows.

**Suggested order:** Start with Ollama's API and model cards, learn context and streaming, compare primary provider contracts, then study MCP authorization, prompt/tool threat boundaries, evaluations, and executable agent extensions.

**Continue with:** [Security and Linux Operations](#security-and-linux-operations), [Architecture and Design Patterns](#architecture-and-design-patterns).

### Project-derived concept notes

- Provider documentation cannot decide Tom's privacy policy. Each multi-provider project needs a local data-classification rule stating what must stay local, what may be sent to each provider, what gets logged, and how credentials and retained conversations are removed.
- Secure localhost AI bridges still need a practical origin/CORS and approval lab covering malicious web pages, DNS rebinding, tool-result injection, cancellation, retries, and idempotent finalization.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | Ollama API introduction | <https://docs.ollama.com/api/introduction> | Defines the local HTTP API base URL, request shape, model naming, versioning, and authentication differences between local and hosted access. | Beginner | 15 minutes |
| Official documentation | Model Cards | <https://huggingface.co/docs/hub/en/model-cards> | Explains how to document intended use, limitations, datasets, evaluation, licensing, and bias for models. Read a model card before treating a local model as suitable for sensitive or tool-using work. | Beginner | 20 minutes |
| Official documentation | Gemma documentation | <https://ai.google.dev/gemma/docs> | Google's maintained Gemma hub links current model families, deployment guides, responsible-use material, and technical documentation. It is more durable than a bookmark to an older Ollama model tag. | Beginner | 20 minutes |
| Official documentation | Ollama Python library | <https://github.com/ollama/ollama-python> | The maintained Python client, typed request patterns, streaming iteration, custom clients, async support, and error examples. It complements the wire-level API without hiding local-model and context limits. | Intermediate | 30 minutes |
| Official documentation | Ollama streaming | <https://docs.ollama.com/api/streaming> | Explains newline-delimited streaming, final response metadata, error handling, and when to disable streaming. It supports correct terminal and GUI token pipelines. | Intermediate | 15 minutes |
| Official documentation | Ollama context length | <https://docs.ollama.com/context-length> | Shows how context limits change memory use and model behavior. It is essential for choosing bounded histories and avoiding unexplained slowdowns or out-of-memory failures. | Intermediate | 10 minutes |
| Reference | Ollama Modelfile | <https://docs.ollama.com/modelfile> | The maintained reference for model bases, parameters, prompt templates, adapters, messages, and licensing metadata. It replaces model-specific bookmarks with a reusable customization model. | Intermediate | 30 minutes |
| Official documentation | Responsible Generative AI Toolkit | <https://ai.google.dev/responsible/docs> | A practical official toolkit for safety policies, model cards, evaluation, and safeguards. It frames local deployment as an engineering responsibility rather than a privacy guarantee by itself. | Intermediate | 35 minutes |
| Official documentation | Using tools | <https://developers.openai.com/api/docs/guides/tools> | The current OpenAI guide to built-in tools, function tools, tool choice, schemas, and tool-call handling. It supports typed provider adapters and explicit execution boundaries. | Intermediate | 35 minutes |
| Official documentation | Streaming API responses | <https://developers.openai.com/api/docs/guides/streaming-responses> | Documents streaming event handling, finalization, partial output, and moderation implications. It is the primary contract for building correct OpenAI terminal and GUI streams. | Intermediate | 30 minutes |
| Official documentation | Getting started with evaluations | <https://developers.openai.com/api/docs/guides/evaluation-getting-started> | A current route for defining criteria, datasets, graders, and repeatable evaluations. It is preferable to relying on subjective spot checks when changing prompts, tools, or agents. | Intermediate | 40 minutes |
| Official documentation | How tool use works | <https://platform.claude.com/docs/en/agents-and-tools/tool-use/how-tool-use-works> | Anthropic's current tool-contract guide covers definitions, tool decisions, result messages, parallel calls, streaming, and error responses for multi-provider adapters. | Intermediate | 35 minutes |
| Official documentation | Create custom subagents | <https://code.claude.com/docs/en/sub-agents> | Explains agent isolation, descriptions, tools, permissions, model selection, persistent memory, hooks, and foreground versus background execution. | Intermediate | 30 minutes |
| Official documentation | Extend Claude with skills | <https://code.claude.com/docs/en/slash-commands> | Documents reusable skills, discovery metadata, arguments, supporting files, tool restrictions, execution modes, and sharing. It supports maintainable agent packages instead of oversized global prompts. | Intermediate | 35 minutes |
| Official documentation | Importing a model | <https://docs.ollama.com/import> | Documents supported model and adapter formats, quantization, conversion, and import workflows. It helps distinguish a compatible artifact from a model that merely has a similar name. | Advanced | 25 minutes |
| Official documentation | MCP and connectors | <https://developers.openai.com/api/docs/guides/tools-connectors-mcp> | Explains remote MCP servers, connectors, approvals, authentication, data sharing, and prompt-injection risk in OpenAI integrations. | Advanced | 40 minutes |
| Official documentation | MCP security best practices | <https://modelcontextprotocol.io/docs/tutorials/security/security_best_practices> | Covers confused-deputy risks, token handling, consent, least privilege, local-server compromise, session hijacking, and other MCP-specific threat boundaries. | Advanced | 45 minutes |
| Official documentation | MCP authorization | <https://modelcontextprotocol.io/docs/tutorials/security/authorization> | Explains the protocol's authorization flow and implementation responsibilities. It helps keep provider tokens scoped to the intended server and user. | Advanced | 40 minutes |
| Reference | MCP Security Cheat Sheet | <https://cheatsheetseries.owasp.org/cheatsheets/MCP_Security_Cheat_Sheet.html> | An implementation-focused checklist for input validation, tool authorization, output handling, secret redaction, logging, network controls, and supply-chain risk around MCP servers. | Advanced | 35 minutes |
| Reference | LLM Prompt Injection Prevention Cheat Sheet | <https://cheatsheetseries.owasp.org/cheatsheets/LLM_Prompt_Injection_Prevention_Cheat_Sheet.html> | A durable threat model and layered defenses for direct, indirect, multimodal, persistent, and tool-mediated prompt injection. Treat model output as untrusted input to every privileged action. | Advanced | 45 minutes |
| Official documentation | Streaming Messages | <https://platform.claude.com/docs/en/build-with-claude/streaming> | The authoritative Anthropic event stream, including deltas, tool input, errors, recovery, and final usage. It enables correct cross-provider stream normalization. | Advanced | 35 minutes |
| Official documentation | Hooks reference | <https://code.claude.com/docs/en/hooks> | The current lifecycle-hook reference for deterministic validation and automation around agent events. Hooks execute code, so review inputs, permissions, timeouts, and failure behavior as production interfaces. | Advanced | 45 minutes |

## Advanced and Cross-Cutting Topics

Study the contracts that span several layers: observability, provenance, protocol evolution, full-text and binary-code search, compatibility, terminal simulation, release safety, interactive visualization, and durable state.

**Useful prerequisites:** Working experience in at least two earlier sections and a concrete project problem to anchor the material.

**Project connection:** Fifty-three repositories map here. These resources support complex systems such as Linux-Ops-Suite, Git-Vista, workstate, teacher-thing, Zellij, agent workflows, search engines, and multi-interface applications.

**Suggested order:** Choose one real cross-cutting problem, read its primary specification or design paper, write the local invariants and failure modes, and build focused tests before generalizing an abstraction.

**Continue with:** [Architecture and Design Patterns](#architecture-and-design-patterns), [Performance and Resource Efficiency](#performance-and-resource-efficiency).

### Project-derived concept notes

- The Multi-Index Hashing paper is rigorous but not a complete implementation curriculum. teacher-thing should keep versioned golden vectors, exact-radius tests, bucket invariants, migration fixtures, and brute-force comparison tests as its educational specification.
- Provenance, freshness, dropped-record accounting, and privacy-minimizing compiled state are covered in fragments across standards. workstate should retain a project-specific exercise that models stale, missing, failed, and unknown evidence independently.

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | Overview of multipage apps — Streamlit | <https://docs.streamlit.io/develop/concepts/multipage-apps/overview> | Current first-party guidance replaces the older “numeric pages directory” framing with both `st.navigation` and directory-based routing, including state and URL caveats. | Beginner | 30 minutes |
| Official documentation | Plotly Express in Python | <https://plotly.com/python/plotly-express/> | The maintainer guide provides a concise high-level route from tidy data to interactive figures while documenting when to drop to graph objects for control. | Beginner | 1 hour |
| Official documentation | humanize | <https://humanize.readthedocs.io/en/latest/> | The project reference provides tested size, number, time, and date presentation helpers while keeping human-facing formatting separate from stored machine values. | Beginner | 30 minutes |
| Reference | `indicatif` — Rust API documentation | <https://docs.rs/indicatif/latest/indicatif/> | The crate reference documents progress bars, draw targets, iterators, `Read`/`Write` wrappers, multi-progress rendering, and non-TTY behavior for long data jobs. | Beginner | 45 minutes |
| Reference | `comfy_table` — Rust API documentation | <https://docs.rs/comfy-table/latest/comfy_table/> | This implementation reference covers deterministic terminal tables, width constraints, wrapping, alignment, styling, and Unicode-aware layout for data-oriented CLIs. | Beginner | 30 minutes |
| Official documentation | Observability primer — OpenTelemetry | <https://opentelemetry.io/docs/concepts/observability-primer/> | The project primer connects traces, metrics, logs, baggage, resources, context propagation, and correlation without tying observability to one backend. | Intermediate | 1–2 hours |
| Official documentation | D3 by Observable | <https://d3js.org/> | The maintained D3 entry point links scales, shapes, selections, transitions, zoom, and force/graph modules for bespoke interactive data visualization. | Intermediate | 3–4 hours |
| Reference | `assert_cmd` — Rust API documentation | <https://docs.rs/assert_cmd/latest/assert_cmd/> | The crate reference supports black-box CLI assertions over exit status, stdout, stderr, environment, and cargo-built binaries for data-pipeline boundary tests. | Intermediate | 45 minutes |
| Book | Testing — Command Line Applications in Rust | <https://rust-cli.github.io/book/tutorial/testing.html> | The Rust CLI working group's tutorial turns `assert_cmd`, predicates, temporary files, and fixture setup into an end-to-end testing workflow rather than isolated API calls. | Intermediate | 1 hour |
| Reference | `tracing` — Rust API documentation | <https://docs.rs/tracing/latest/tracing/> | The instrumentation reference explains structured events, spans, causality, subscribers, filtering, async caveats, and low-overhead disabled callsites for observable systems. | Advanced | 2 hours |
| Reference | PROV-Overview | <https://www.w3.org/TR/prov-overview/> | The W3C overview supplies a standard vocabulary for entities, activities, agents, derivations, and bundles when designing provenance-aware snapshots and compiled state. | Advanced | 1 hour |
| Article | Fast Search in Hamming Space with Multi-Index Hashing | <https://norouzi.github.io/research/papers/multi_index_hashing.pdf> | The primary paper derives exact sub-linear search over binary codes and reports time and memory trade-offs, giving perceptual-hash systems a rigorous design baseline. | Advanced | 1–2 hours |
| Reference | RequireJS API | <https://requirejs.org/docs/api.html> | The primary API reference documents AMD modules, dependency loading, configuration, optimization, and legacy compatibility needed to maintain older interactive visualizations. | Advanced | 1–2 hours |

## Career and Certification Resources

Translate hands-on practice into current, owner-published certification objectives without turning the learning path into an exam-dump directory.

**Useful prerequisites:** Choose a target role first; certifications are evidence frameworks, not substitutes for projects and operational judgment.

**Project connection:** The repository history includes A+ and Microsoft credential material, while the account's work also aligns with Linux administration, GitHub, and cloud fundamentals.

**Suggested order:** Use an entry-level objective list as a gap analysis, practice every operational domain in a lab, then consider performance-based Linux or role-specific GitHub/cloud certifications.

**Continue with:** [Security and Linux Operations](#security-and-linux-operations), [Git, GitHub, Automation, and Developer Tooling](#git-github-automation-and-developer-tooling).

| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
|---|---|---|---|---|---:|
| Official documentation | CompTIA A+ | <https://www.comptia.org/en-us/certifications/a/> | The authoritative source for the current exam series, domains, prerequisites, delivery options, and renewal requirements. Always download objectives from the certification owner before choosing study material. | Beginner | 20 minutes |
| Official documentation | Linux Essentials | <https://www.lpi.org/our-certifications/linux-essentials-overview/> | A vendor-neutral entry route covering Linux concepts, command-line basics, permissions, security, and open-source culture. The official objectives make it useful as a fundamentals checklist even without sitting the exam. | Beginner | 20 minutes |
| Official documentation | About GitHub Certifications | <https://docs.github.com/en/get-started/showcase-your-expertise-with-github-certifications/about-github-certifications> | The official map of GitHub Foundations and role-specific certifications, with direct links to current study guides and exam details. | Beginner | 15 minutes |
| Official documentation | Microsoft Certified: Azure Fundamentals | <https://learn.microsoft.com/en-us/credentials/certifications/azure-fundamentals/> | The maintained certification page and objective route for cloud concepts, Azure architecture and services, and governance. Recheck the skills-measured date before scheduling because Microsoft updates objectives frequently. | Beginner | 20 minutes |
| Official documentation | Linux Foundation Certified System Administrator | <https://training.linuxfoundation.org/certification/LFCS/> | The official performance-based Linux administration certification and current competency domains. It aligns well with hands-on service, storage, networking, user, and security work. | Intermediate | 25 minutes |
| Official documentation | Red Hat Certified System Administrator exam EX200 | <https://www.redhat.com/en/services/training/ex200-red-hat-certified-system-administrator-rhcsa-exam?section=Objectives> | The live RHCSA objectives for a practical enterprise-Linux exam. Check the stated RHEL version because objectives change as the platform advances. | Intermediate | 25 minutes |
