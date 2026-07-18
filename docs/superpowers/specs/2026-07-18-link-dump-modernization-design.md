# Link Dump Audit and Modernization Design

**Date:** 2026-07-18
**Repository:** `tom2025b/Link-Dump`
**Primary document:** `links.md`

## Purpose

Transform the current chronological Link Dump into a durable, detailed learning path. Every retained resource will be verified, evaluated for quality and relevance, assigned useful learning metadata, and placed where a learner can understand why and when to use it.

The finished document must retain the approachable table-based style of the final existing section while providing substantially more depth, stronger organization, and a complete audit trail.

## Current State

The repository currently contains:

- 250 resource rows and 243 unique URLs.
- 35 mostly chronological, session-based topic sections.
- Duplicate URLs and overlapping sections.
- Broad YouTube search-result links instead of selected resources.
- A mixture of official documentation, strong community material, aging tutorials, SEO-driven articles, and references mislabeled as official.
- A stale header claiming 480 links.
- A README whose topic list covers only the first eight sections.
- Four columns per resource: type, title, URL, and a short statement of usefulness.

## Goals

1. Verify every existing URL and assess the content behind it.
2. Remove resources that are dead, obsolete, redundant, misleading, paywalled without unique value, or below the quality of an available alternative.
3. Prefer official documentation, specifications, maintainer-authored guides, and canonical books.
4. Use community resources when they explain a concept better than the official reference or when no official educational material exists.
5. Expand the collection to cover important concepts implied by the existing projects and technologies.
6. Reorganize the document into a progressive learning path rather than a chronological bookmark dump.
7. Give every resource a title, direct URL, detailed value statement, difficulty, estimated reading or viewing time, and content type.
8. Record what was removed and added, with a reason for each decision.
9. Update the README so it accurately explains the document and its coverage.

## Non-Goals

- Do not preserve an entry solely because it already exists.
- Do not target an arbitrary final link count at the expense of quality.
- Do not turn the repository into a general-purpose directory of every programming topic.
- Do not add trendy news posts, release announcements, undated search-result pages, or near-duplicate resources merely to make the collection larger.
- Do not require a custom application or database to read the learning path; Markdown remains the canonical format.

## Editorial Model

The document will use a hybrid structure:

1. Broad, logical learning-path sections make the collection navigable.
2. Resources within each section progress from beginner foundations to intermediate application and advanced depth.
3. Short section introductions explain what the learner will gain, useful prerequisites, and how the topic connects to Tom's projects.
4. Detailed resource tables preserve the style of the current final entry.
5. Audit appendices preserve accountability for removals, replacements, and additions.

Each resource row will use this schema:

| Field | Requirement |
|---|---|
| Type | One of: Official documentation, Article, Blog, Book, Video, or Reference |
| Title | The resource's current, accurate title |
| URL | A direct HTTPS URL to the resource, not a search-results page |
| Why this is valuable | One to three specific sentences explaining what it teaches, when to use it, and why it earned a place |
| Difficulty | Beginner, Intermediate, or Advanced |
| Estimated time | A realistic range such as 10–15 min, 45–60 min, 3–5 hr, or Ongoing reference |

Difficulty means:

- **Beginner:** Assumes little prior knowledge and teaches basic vocabulary or workflows.
- **Intermediate:** Assumes working familiarity and focuses on applying concepts in real projects.
- **Advanced:** Requires strong foundations or covers internals, trade-offs, security implications, or performance behavior.

Estimated time represents the useful first pass through the relevant material, not exhaustive study. API manuals and specifications may use `Ongoing reference` when a linear reading estimate would be misleading.

## Planned Learning-Path Sections

The exact subsection names may be refined during curation, but the finished structure will cover:

1. **How to Use This Learning Path**
   - Suggested routes for Linux operations, Rust systems work, Go CLI work, Python tooling, and application architecture.

2. **Core Language Fundamentals**
   - Rust ownership, borrowing, traits, iterators, modules, error values, and I/O.
   - Go packages, interfaces, errors, contexts, goroutines, channels, and file I/O.
   - Python language, typing, generators, threading, subprocesses, and packaging.
   - Bash quoting, strict-mode caveats, traps, pipelines, and portable scripting.

3. **Libraries and Frameworks Used in Tom's Projects**
   - Rust: Tokio, reqwest, Serde, thiserror, clap, Axum, rusqlite, Rayon, archive and file-processing crates.
   - Go: Cobra, YAML, WebSockets, standard-library concurrency, and CLI building.
   - Python: Rich, Requests, Streamlit, Plotly, PyQt6, and terminal primitives.

4. **CLI and TUI Development**
   - Command design, argument parsing, exit codes, output streams, terminal capabilities, accessibility, `NO_COLOR`, Ratatui, Crossterm, Rich, and test backends.

5. **GUI, Web, and Interactive Application Development**
   - egui/eframe, PyQt6, Axum, WebSockets, Canvas, embedded assets, and client/server state.

6. **Architecture and Design Patterns**
   - Hexagonal architecture, ports and adapters, separation of concerns, dependency direction, facades, project layout, state ownership, and hybrid Python/Rust boundaries.

7. **Error Handling and Reliability**
   - Rust `Result`, thiserror versus anyhow, Go error wrapping and cancellation, Python exceptions and subprocess failures, Bash cleanup and traps, retries, timeouts, and graceful shutdown.

8. **Testing and Code Quality**
   - Unit, integration, property, CLI, TUI, concurrency, and end-to-end testing; test fixtures; temporary files; linters; formatting; and deterministic tests.

9. **Async Programming and Concurrency**
   - Rust futures and Tokio, Go goroutines and channels, Python threads and queues, cancellation, backpressure, shared state, synchronization, and avoiding blocking work on async runtimes.

10. **Data, Storage, Search, and File Processing**
    - JSON and YAML, SQLite, WAL, FTS5, transactions, streaming archives, compression, hashing, MIME detection, metadata extraction, filesystem traversal, and XDG paths.

11. **Performance and Resource Efficiency**
    - Buffered and streaming I/O, zero-copy concepts, batching, SQLite transaction performance, parallel iterators, profiling, benchmarking, fixed-timestep loops, and memory-aware file processing.

12. **Security and Linux Operations**
    - SSH, UFW, Tailscale, sysctl, Linux hardening, secret storage, email credentials, least privilege, backup safety, cron/systemd execution, and safe network defaults.

13. **Git, GitHub, Automation, and Developer Tooling**
    - Remotes, authentication, GitHub CLI, repository automation, rsync, dotfiles, GNU Stow, XDG integration, desktop entries, libvirt/virtiofs, and reproducible scripts.

14. **Local AI and Related Tools**
    - Ollama APIs, local model selection, streaming responses, model limitations, and responsible integration into terminal applications.

15. **Advanced and Cross-Cutting Topics**
    - API design, compatibility, typed boundaries, observability, secure defaults, protocol design, server-authoritative loops, full-text search design, and maintainable systems interfaces.

16. **Career and Certification Resources**
    - Current official certification objectives and high-quality study material, clearly separated from software-engineering paths.

## Resource Selection Policy

Resources will be ranked using this order:

1. Current official documentation, specification, language book, or maintainer guide.
2. Maintainer-authored tutorial or canonical project example.
3. Established book or course with durable technical value.
4. High-quality community article that adds concrete explanation, examples, or trade-off analysis missing from official documentation.
5. Forum or Q&A material only when it documents a specific subtlety that is not covered better elsewhere.

A resource will be removed or replaced when any of these apply:

- The URL is dead or permanently redirects to unrelated content.
- The content describes an unsupported version and does not clearly distinguish historical behavior.
- It is a generic search-results page rather than a selected resource.
- It is inaccurate, shallow, heavily promotional, copied, or search-engine optimized without meaningful teaching value.
- It requires payment or registration while a comparable open resource exists.
- Its useful content is fully covered by a stronger retained resource.
- It duplicates another URL or repeats the same teaching role without adding a distinct perspective.
- Its title or type overstates its authority, such as labeling a third-party blog as official.

Multiple resources may remain for one concept when they serve different roles, such as a beginner tutorial, an authoritative reference, and an advanced design explanation.

## Link Verification Method

The audit will:

1. Extract and normalize every current URL.
2. Check each URL using redirects and bounded network timeouts.
3. Use a normal GET request when a server rejects or mishandles HEAD requests.
4. Classify responses as healthy, redirected, ambiguous, restricted, or dead.
5. Manually inspect ambiguous responses such as 403, 429, bot protection, login gates, soft-404 pages, and JavaScript-only documentation.
6. Confirm that the page title and content still match the Link Dump entry.
7. Replace old URLs with canonical destinations when an official redirect or documentation move exists.
8. Re-run the checker against the final document.

A 403, 429, or bot-protection response alone will not be treated as proof that a resource is dead. Likewise, an HTTP 200 response will not be treated as proof that a resource remains relevant.

## Audit Decisions and Traceability

Each original resource will receive one internal decision:

- **Keep:** Alive, relevant, and meets the quality bar.
- **Update:** Same resource, but title, URL, type, value statement, difficulty, or time needs correction.
- **Replace:** Removed in favor of a named stronger alternative.
- **Consolidate:** Duplicate or overlapping entry merged into one canonical resource.
- **Remove:** No longer valuable and no direct replacement is needed.

The end of `links.md` will contain:

1. **Resources Removed or Replaced** — original title and URL, action, reason, and replacement when applicable.
2. **Resources Added** — new title and URL, target section, and why it was selected.
3. **Future Educational Gaps** — concepts for which existing material remains weak, fragmented, overly version-specific, or insufficiently practical.
4. **Audit Notes** — audit date, methodology, counts, and limitations.

## Files and Responsibilities

- `links.md`
  - Canonical learning path.
  - Contains all retained and added resources, metadata, navigation, and audit appendices.
- `README.md`
  - Explains the repository, major learning paths, metadata fields, audit date, and how to use `links.md`.
- `docs/superpowers/specs/2026-07-18-link-dump-modernization-design.md`
  - Records this approved design.
- `docs/superpowers/plans/2026-07-18-link-dump-modernization.md`
  - Records the execution and validation plan.

No executable link-checking utility will be committed unless a reusable checker becomes clearly valuable during implementation. Temporary audit data may be generated outside the repository or under `/tmp`.

## Validation and Acceptance Criteria

The modernization is complete only when:

- Every original URL has an explicit audit decision.
- Every retained URL has been checked for reachability and manually assessed for relevance.
- Every resource row contains all six required metadata fields.
- The final document has no duplicate normalized URLs unless a deliberate exception is documented.
- No resource points to a generic search-results page.
- Official resources are labeled accurately.
- Dead, irrelevant, and low-quality resources are absent from the curated sections.
- Important concepts in the existing 35 topics are either represented in the new structure or recorded as intentionally removed.
- Each major section reads in a sensible beginner-to-advanced order.
- The removal and addition appendices explain every material curation decision.
- The reported resource totals match the actual document.
- Markdown tables, headings, internal links, and external URLs pass final checks.
- `README.md` accurately represents the finished Link Dump.

## Delivery

Work will be performed in the local clone before any remote update. Commits made by Codex will use author name `claude_2010` and Tom's GitHub noreply address. A dated summary will be copied to `~/projects/_claude-outputs/` after the audit and rewrite are complete.
