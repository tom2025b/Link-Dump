# Link Dump Modernization Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Replace the current chronological Link Dump with a verified, expanded, detailed learning path and a complete record of removals, replacements, and additions.

**Architecture:** Build an immutable inventory of the 250 original rows, attach a curation decision and reachability evidence to every row, research missing concepts in independent domain batches, and then integrate the approved resources into one canonical `links.md`. Keep temporary audit evidence under `/tmp/link-dump-audit`; commit only the finished learning path, README, specification, and plan.

**Tech Stack:** Markdown, Git, Python 3 standard library, `rg`, `awk`, `sort`, `curl`, shell utilities, browser research, and official project documentation.

## Global Constraints

- Work in the local clone before any remote update.
- Preserve the table-based style of the final existing section.
- Every curated resource must include Type, Title, URL, Why this is valuable, Difficulty, and Estimated time.
- Allowed types are exactly: Official documentation, Article, Blog, Book, Video, and Reference.
- Allowed difficulty values are exactly: Beginner, Intermediate, and Advanced.
- Prefer current official documentation, specifications, maintainer guides, and canonical books.
- Retain community resources only when they add teaching value not supplied by an official source.
- Do not retain generic search-result pages, dead links, misleading labels, redundant entries, or low-quality SEO material.
- Do not target an arbitrary resource count at the expense of quality.
- When a relevant concept lacks a strong durable resource, add a concise explanatory note in its learning-path section and record the gap under Future Educational Gaps instead of selecting a weak link.
- A 403, 429, or bot challenge is ambiguous until manually reviewed; HTTP 200 alone does not prove relevance.
- Keep `links.md` as the canonical learning path and `README.md` as the concise repository guide.
- Codex commits must use `claude_2010 <262510778+tom2025b@users.noreply.github.com>`.
- Copy the completed-task summary to `/home/tom/projects/_claude-outputs/2026-07-18_link-dump-modernization_summary.md`.

---

## File Map

- Modify: `links.md`
  - Final learning path, resource metadata, navigation, removed/replaced resources, added resources, future gaps, and audit notes.
- Modify: `README.md`
  - Accurate overview, learning routes, field definitions, audit status, and usage instructions.
- Existing: `docs/superpowers/specs/2026-07-18-link-dump-modernization-design.md`
  - Approved design and acceptance criteria.
- Create: `docs/superpowers/plans/2026-07-18-link-dump-modernization.md`
  - This execution plan.
- Temporary: `/tmp/link-dump-audit/original-resources.tsv`
  - One immutable row for each original resource.
- Temporary: `/tmp/link-dump-audit/build_inventory.py`
  - Deterministically parses the original four-column Markdown rows and creates both audit ledgers.
- Temporary: `/tmp/link-dump-audit/http-status.tsv`
  - Automated reachability evidence and canonical redirect targets.
- Temporary: `/tmp/link-dump-audit/check_urls.py`
  - Runs bounded concurrent curl probes and maps unique URL results back to all original row IDs.
- Temporary: `/tmp/link-dump-audit/decisions.tsv`
  - One keep, update, replace, consolidate, or remove decision for every original row.
- Temporary: `/tmp/link-dump-audit/candidates-*.md`
  - Domain-specific research notes using the final six-field schema.
- Create outside repository: `/home/tom/projects/_claude-outputs/2026-07-18_link-dump-modernization_summary.md`
  - Tom's durable completion record.

---

### Task 1: Freeze the Original Inventory and Audit Schema

**Files:**
- Read: `links.md`
- Create: `/tmp/link-dump-audit/original-resources.tsv`
- Create: `/tmp/link-dump-audit/decisions.tsv`

**Interfaces:**
- Consumes: The 250 original Markdown table rows in `links.md`.
- Produces: A stable `row_id` from `LD-0001` through `LD-0250`, the original section and metadata, a normalized URL, and an empty decision record for later audit tasks.

- [ ] **Step 1: Confirm the local baseline**

Run:

```bash
git status --short --branch
rg -n '^\| \[[A-Z& ]+\] \|' links.md | wc -l
rg -o 'https?://[^ |)]+' links.md | wc -l
rg -o 'https?://[^ |)]+' links.md | sort -u | wc -l
```

Expected:

- The branch is `docs/link-dump-modernization`.
- The worktree is clean; the local branch is ahead of `origin/main` only by the approved design and plan commits.
- Resource rows: `250`.
- URL occurrences: `250`.
- Unique URLs: `243`.

- [ ] **Step 2: Create the audit workspace**

Run:

```bash
mkdir -p /tmp/link-dump-audit
```

Expected: `/tmp/link-dump-audit` exists and the repository remains otherwise unchanged.

- [ ] **Step 3: Write the deterministic inventory parser**

Use `apply_patch` to create `/tmp/link-dump-audit/build_inventory.py` with:

```python
#!/usr/bin/env python3
import csv
import re
from pathlib import Path
from urllib.parse import urlsplit, urlunsplit

SOURCE = Path("links.md")
OUT_DIR = Path("/tmp/link-dump-audit")
ROW_RE = re.compile(
    r"^\|\s*(\[[^\]]+\])\s*\|\s*(.*?)\s*\|\s*"
    r"(https?://\S+)\s*\|\s*(.*?)\s*\|\s*$"
)


def normalize_url(url: str) -> str:
    parts = urlsplit(url.strip())
    scheme = parts.scheme.lower()
    host = (parts.hostname or "").lower()
    if parts.port:
        host = f"{host}:{parts.port}"
    path = parts.path or "/"
    if path != "/":
        path = path.rstrip("/")
    return urlunsplit((scheme, host, path, parts.query, ""))


def main() -> None:
    rows = []
    section = ""
    for line in SOURCE.read_text(encoding="utf-8").splitlines():
        if line.startswith("## "):
            section = line.removeprefix("## ").strip()
            continue
        match = ROW_RE.match(line)
        if not match:
            continue
        original_type, title, url, value = match.groups()
        rows.append(
            (
                f"LD-{len(rows) + 1:04d}",
                section,
                original_type.strip("[]"),
                title.strip(),
                url.strip(),
                value.strip(),
                normalize_url(url),
            )
        )

    if len(rows) != 250:
        raise SystemExit(f"expected 250 original rows, found {len(rows)}")

    OUT_DIR.mkdir(parents=True, exist_ok=True)
    with (OUT_DIR / "original-resources.tsv").open(
        "w", encoding="utf-8", newline=""
    ) as handle:
        writer = csv.writer(handle, delimiter="\t", lineterminator="\n")
        writer.writerow(
            [
                "row_id",
                "section",
                "original_type",
                "original_title",
                "original_url",
                "original_value",
                "normalized_url",
            ]
        )
        writer.writerows(rows)

    with (OUT_DIR / "decisions.tsv").open(
        "w", encoding="utf-8", newline=""
    ) as handle:
        writer = csv.writer(handle, delimiter="\t", lineterminator="\n")
        writer.writerow(
            [
                "row_id",
                "decision",
                "original_title",
                "original_url",
                "replacement_title",
                "replacement_url",
                "reason",
            ]
        )
        for row_id, _section, _type, title, url, _value, _normalized in rows:
            writer.writerow([row_id, "", title, url, "", "", ""])


if __name__ == "__main__":
    main()
```

Expected: The parser accepts four-column resource rows even when the value statement contains an internal pipe character.

- [ ] **Step 4: Generate both immutable audit ledgers**

Run:

```bash
python3 /tmp/link-dump-audit/build_inventory.py
sed -n '1,3p' /tmp/link-dump-audit/original-resources.tsv
sed -n '249,251p' /tmp/link-dump-audit/original-resources.tsv
```

Expected:

- The header uses the seven documented inventory columns.
- The first row is `LD-0001`.
- The last row is `LD-0250`.
- `/tmp/link-dump-audit/decisions.tsv` contains the documented seven decision columns with blank decision fields.

- [ ] **Step 5: Verify inventory integrity**

Run:

```bash
test "$(( $(wc -l < /tmp/link-dump-audit/original-resources.tsv) - 1 ))" -eq 250
test "$(( $(wc -l < /tmp/link-dump-audit/decisions.tsv) - 1 ))" -eq 250
cut -f1 /tmp/link-dump-audit/original-resources.tsv | tail -n +2 | sort | uniq -d
```

Expected: Both `test` commands exit 0 and the duplicate-ID command prints nothing.

---

### Task 2: Run the Automated Reachability Audit

**Files:**
- Read: `/tmp/link-dump-audit/original-resources.tsv`
- Create: `/tmp/link-dump-audit/http-status.tsv`
- Update: `/tmp/link-dump-audit/decisions.tsv`

**Interfaces:**
- Consumes: One normalized original URL per `row_id`.
- Produces: `row_id`, requested URL, HTTP code, final URL, result class, and a short network note for all 250 original rows.

- [ ] **Step 1: Write the bounded concurrent URL checker**

Use `apply_patch` to create `/tmp/link-dump-audit/check_urls.py` with:

```python
#!/usr/bin/env python3
import csv
import subprocess
from concurrent.futures import ThreadPoolExecutor
from pathlib import Path
from urllib.parse import urlsplit, urlunsplit

AUDIT_DIR = Path("/tmp/link-dump-audit")
USER_AGENT = (
    "Link-Dump-Audit/2026-07-18 "
    "(+https://github.com/tom2025b/Link-Dump)"
)


def normalize_url(url: str) -> str:
    parts = urlsplit(url.strip())
    host = (parts.hostname or "").lower()
    if parts.port:
        host = f"{host}:{parts.port}"
    path = parts.path or "/"
    if path != "/":
        path = path.rstrip("/")
    return urlunsplit((parts.scheme.lower(), host, path, parts.query, ""))


def probe(url: str, head: bool) -> tuple[int, str, str, int, str]:
    command = [
        "curl",
        "--silent",
        "--show-error",
        "--location",
        "--max-redirs",
        "8",
        "--connect-timeout",
        "10",
        "--max-time",
        "30",
        "--retry",
        "1",
        "--retry-delay",
        "1",
        "--user-agent",
        USER_AGENT,
        "--output",
        "/dev/null",
        "--write-out",
        "%{http_code}\\t%{url_effective}\\t%{content_type}",
    ]
    if head:
        command.append("--head")
    command.append(url)
    result = subprocess.run(command, text=True, capture_output=True, check=False)
    fields = result.stdout.strip().split("\t", 2)
    code = int(fields[0]) if fields and fields[0].isdigit() else 0
    final_url = fields[1] if len(fields) > 1 else url
    content_type = fields[2] if len(fields) > 2 else ""
    note = result.stderr.strip().replace("\t", " ").replace("\n", " ")[:240]
    return code, final_url, content_type, result.returncode, note


def check(url: str) -> tuple[str, int, str, str, int, str, str]:
    code, final_url, content_type, exit_code, note = probe(url, head=True)
    if code in {0, 403, 405, 429} or exit_code != 0:
        code, final_url, content_type, exit_code, note = probe(url, head=False)

    if exit_code != 0 or code == 0:
        result_class = "dead"
    elif 200 <= code <= 299:
        result_class = (
            "redirected"
            if normalize_url(final_url) != normalize_url(url)
            else "healthy"
        )
    elif code in {401, 403, 405, 429}:
        result_class = "ambiguous"
    elif code in {404, 410} or 500 <= code <= 599:
        result_class = "dead"
    else:
        result_class = "ambiguous"
    return (
        url,
        code,
        final_url,
        content_type,
        exit_code,
        result_class,
        note,
    )


def main() -> None:
    with (AUDIT_DIR / "original-resources.tsv").open(
        encoding="utf-8", newline=""
    ) as handle:
        inventory = list(csv.DictReader(handle, delimiter="\t"))

    unique_urls = sorted({row["original_url"] for row in inventory})
    with ThreadPoolExecutor(max_workers=10) as pool:
        by_url = {result[0]: result for result in pool.map(check, unique_urls)}

    with (AUDIT_DIR / "http-status.tsv").open(
        "w", encoding="utf-8", newline=""
    ) as handle:
        writer = csv.writer(handle, delimiter="\t", lineterminator="\n")
        writer.writerow(
            [
                "row_id",
                "requested_url",
                "http_code",
                "final_url",
                "content_type",
                "curl_exit",
                "result_class",
                "note",
            ]
        )
        for row in inventory:
            (
                _url,
                code,
                final_url,
                content_type,
                exit_code,
                result_class,
                note,
            ) = by_url[row["original_url"]]
            writer.writerow(
                [
                    row["row_id"],
                    row["original_url"],
                    code,
                    final_url,
                    content_type,
                    exit_code,
                    result_class,
                    note,
                ]
            )


if __name__ == "__main__":
    main()
```

Expected: The checker uses ten workers, retries HEAD-hostile endpoints with GET, follows at most eight redirects, and records a result even when curl fails.

- [ ] **Step 2: Run the reachability audit and map results to every row**

Run:

```bash
python3 /tmp/link-dump-audit/check_urls.py
test "$(( $(wc -l < /tmp/link-dump-audit/http-status.tsv) - 1 ))" -eq 250
cut -f7 /tmp/link-dump-audit/http-status.tsv | sort | uniq -c
```

Expected: The line-count assertion exits 0 and the class summary accounts for all 250 original rows.

- [ ] **Step 2: Map reachability results back to every row**

Write `/tmp/link-dump-audit/http-status.tsv` with:

```text
row_id	requested_url	http_code	final_url	content_type	curl_exit	result_class	note
```

Use these result classes:

- `healthy`: 200–299 with a relevant-looking document response.
- `redirected`: successful response at a materially different canonical URL.
- `ambiguous`: 401, 403, 405, 429, bot challenge, JavaScript shell, or unexpected content type.
- `dead`: 404, 410, repeated 5xx, DNS failure, TLS failure, or connection failure after retry.

Expected: 251 lines including the header and exactly one record for every `LD-*` ID.

- [ ] **Step 3: Review ambiguous and dead classifications**

Open every `ambiguous` result in a browser and manually retry representative `dead` groups by host. Reclassify a row only after confirming whether it is bot-protected, moved, login-gated, or genuinely unavailable.

Expected: Sites that reject automated clients but serve real content are marked for manual retention review; unresolved endpoints remain ambiguous until their domain curation task.

- [ ] **Step 4: Flag redirects, dead responses, and search pages**

Run targeted reports for:

```text
result_class in {redirected, ambiguous, dead}
URL contains youtube.com/results, google.com/search, or bing.com/search
final host differs from requested host
content type is not HTML, plain text, PDF, or expected documentation content
```

Expected: All broad YouTube search links are flagged for replacement, and no flagged row is automatically removed without manual review.

- [ ] **Step 5: Enter provisional decisions**

Mark confirmed duplicates as `consolidate`, generic search-result pages as `replace`, and confirmed dead irrelevant pages as `remove`. Leave ambiguous and content-quality decisions for domain review.

Expected: Every provisional decision includes a concrete reason; no decision is based solely on 403 or 429.

---

### Task 3: Curate Core Languages, Error Handling, Testing, and Concurrency

**Files:**
- Read: `links.md`
- Read: `/tmp/link-dump-audit/original-resources.tsv`
- Read: `/tmp/link-dump-audit/http-status.tsv`
- Update: `/tmp/link-dump-audit/decisions.tsv`
- Create: `/tmp/link-dump-audit/candidates-core-languages.md`

**Interfaces:**
- Consumes: Original Rust, Go, Python, Bash, error-handling, testing, async, and concurrency resources.
- Produces: Fully sourced candidate rows for the Core Language Fundamentals, Error Handling and Reliability, Testing and Code Quality, and Async Programming and Concurrency sections.

- [ ] **Step 1: Audit the original language resources**

Review each matching original row for current title, version relevance, authority, depth, and distinct teaching role. Give every reviewed `row_id` one decision in `decisions.tsv`.

Expected: No original language-related row remains undecided.

- [ ] **Step 2: Fill fundamental coverage gaps**

Research durable sources for:

- Rust ownership, borrowing, traits, iterators, modules, I/O, `Result`, error context, testing, Cargo integration tests, futures, Tokio task design, cancellation, and blocking work.
- Go packages, interfaces, errors and wrapping, `context`, testing and fuzzing, goroutines, channels, synchronization, and graceful shutdown.
- Python language reference, typing, exceptions, generators, subprocesses, threading, queues, testing, and packaging.
- Bash quoting, pipelines, `set -e` caveats, traps, cleanup, ShellCheck, and portable scripting.

Use official language books and references first. Add a community explanation only when it supplies a clearer practical path or a distinct advanced treatment.

- [ ] **Step 3: Write complete candidate rows**

Use the final schema for every candidate:

```markdown
| Type | Title | URL | Why this is valuable | Difficulty | Estimated time |
```

Every value statement must identify what the resource teaches and why it is preferable or complementary to other entries.

Expected: No candidate row contains an unverified title, generic search URL, missing metadata, or unsupported `Type`/`Difficulty` value.

- [ ] **Step 4: Verify all newly selected URLs**

Run the same bounded curl checks as Task 2, then manually open every ambiguous result and enough healthy results to confirm titles and relevance.

Expected: Every candidate has a reachability result and a content-quality justification.

---

### Task 4: Curate Libraries, Frameworks, CLI/TUI, GUI/Web, and Architecture

**Files:**
- Read: `links.md`
- Read: `/tmp/link-dump-audit/original-resources.tsv`
- Read: `/tmp/link-dump-audit/http-status.tsv`
- Update: `/tmp/link-dump-audit/decisions.tsv`
- Create: `/tmp/link-dump-audit/candidates-app-development.md`

**Interfaces:**
- Consumes: Original resources for project libraries, terminal interfaces, GUI/web systems, and architecture.
- Produces: Candidate rows for Libraries and Frameworks, CLI and TUI Development, GUI/Web/Interactive Development, and Architecture and Design Patterns.

- [ ] **Step 1: Audit every matching original row**

Cover Ratatui, Crossterm, clap, Rich, egui/eframe, PyQt6, Axum, WebSockets, Canvas, Serde, reqwest, Cobra, Streamlit, Plotly, hexagonal architecture, project layout, facades, state ownership, and hybrid Python/Rust boundaries.

Expected: Each matching original `row_id` has one evidence-backed decision.

- [ ] **Step 2: Replace weak or misleading sources**

Replace search-result pages, stale tutorials, third-party pages mislabeled official, and shallow framework introductions when official guides or maintainer examples are available.

Expected: Each replacement decision names its replacement title and direct URL.

- [ ] **Step 3: Add missing application-development concepts**

Research command semantics, standard streams, exit status, terminal lifecycle cleanup, accessibility, `NO_COLOR`, snapshot/TestBackend testing, event loops, UI state, server state, embedded assets, WebSocket lifecycle, dependency direction, ports and adapters, and public API boundaries.

- [ ] **Step 4: Write and verify complete candidate rows**

Use the six-field schema and the Task 2 verification rules.

Expected: Every candidate is direct, alive or manually confirmed, accurately typed, and ordered from beginner to advanced within its future subsection.

---

### Task 5: Curate Data, File Processing, Performance, and Advanced Topics

**Files:**
- Read: `links.md`
- Read: `/tmp/link-dump-audit/original-resources.tsv`
- Read: `/tmp/link-dump-audit/http-status.tsv`
- Update: `/tmp/link-dump-audit/decisions.tsv`
- Create: `/tmp/link-dump-audit/candidates-data-performance.md`

**Interfaces:**
- Consumes: Original storage, archive, search, hashing, file metadata, and performance resources.
- Produces: Candidate rows for Data/Storage/Search/File Processing, Performance and Resource Efficiency, and Advanced and Cross-Cutting Topics.

- [ ] **Step 1: Audit matching original resources**

Cover JSON/YAML, SQLite, FTS5, WAL, transactions, archives, zstd, tar, BLAKE3, filesystem traversal, MIME detection, EXIF/PDF/office extraction, XDG paths, streaming I/O, Rayon, batching, fixed timesteps, and read-only database access.

Expected: Each matching original row has one decision and any duplicate URL has a single canonical teaching role.

- [ ] **Step 2: Prefer primary technical sources**

Use SQLite documentation, Rust standard-library documentation, crate documentation, format specifications, and maintainers' design material ahead of benchmark blogs or generic tutorials.

Expected: Community performance articles remain only when their measurements or explanation add value beyond official references.

- [ ] **Step 3: Add missing depth**

Research profiling, criterion-style benchmarking, buffered I/O, zero-copy trade-offs, batching, backpressure, transaction boundaries, full-text search design, resource limits, compatibility, and observability.

- [ ] **Step 4: Write and verify complete candidate rows**

Use the six-field schema and Task 2 verification rules.

Expected: Every candidate explains whether it is meant for learning, implementation guidance, or ongoing reference.

---

### Task 6: Curate Security, Linux Operations, Tooling, Local AI, and Career Material

**Files:**
- Read: `links.md`
- Read: `/tmp/link-dump-audit/original-resources.tsv`
- Read: `/tmp/link-dump-audit/http-status.tsv`
- Update: `/tmp/link-dump-audit/decisions.tsv`
- Create: `/tmp/link-dump-audit/candidates-operations-tools.md`

**Interfaces:**
- Consumes: Original Git/GitHub, UFW, SSH, sysctl, Tailscale, hardening, backup, desktop, virtualization, SMTP, local AI, and certification resources.
- Produces: Candidate rows for Security and Linux Operations, Git/GitHub/Automation/Developer Tooling, Local AI and Related Tools, and Career and Certification Resources.

- [ ] **Step 1: Audit matching original resources**

Expected: Every matching original row has one evidence-backed decision, and resources presenting dangerous hardening commands without context are removed or paired with authoritative guidance.

- [ ] **Step 2: Correct authority and safety labels**

Distinguish official manuals and specifications from community wikis and commercial blogs. Prefer OpenSSH manuals, kernel/systemd documentation, Ubuntu or distribution documentation, Tailscale documentation, Git/GitHub documentation, GNU manuals, libvirt/QEMU documentation, Google account documentation, and current certification objectives.

- [ ] **Step 3: Add missing operational concepts**

Research least privilege, secret storage, rollback-safe firewall/SSH changes, backup verification, cron versus systemd timers, safe network defaults, Git credential safety, repository automation, local model limitations, and responsible local-AI integration.

- [ ] **Step 4: Write and verify complete candidate rows**

Use the six-field schema and Task 2 verification rules.

Expected: Security value statements include important safety context and do not encourage copying unreviewed hardening snippets.

---

### Task 7: Complete the Decision Ledger

**Files:**
- Read: `/tmp/link-dump-audit/candidates-core-languages.md`
- Read: `/tmp/link-dump-audit/candidates-app-development.md`
- Read: `/tmp/link-dump-audit/candidates-data-performance.md`
- Read: `/tmp/link-dump-audit/candidates-operations-tools.md`
- Update: `/tmp/link-dump-audit/decisions.tsv`

**Interfaces:**
- Consumes: All domain audits and replacement selections.
- Produces: Exactly one final decision and reason for each of the 250 original rows.

- [ ] **Step 1: Find incomplete decisions**

Run a TSV-aware check for missing `decision` or `reason`.

Expected: The first run lists any rows not finalized during Tasks 2–6.

- [ ] **Step 2: Resolve every incomplete decision**

Use only `keep`, `update`, `replace`, `consolidate`, or `remove`. A `replace` row must include both replacement title and replacement URL. A `consolidate` row must identify the retained canonical resource in `reason`.

- [ ] **Step 3: Validate the ledger**

Run checks that assert:

- 250 decision rows.
- 250 unique row IDs.
- Zero empty decisions.
- Zero empty reasons.
- Zero replacement decisions without replacement metadata.
- Zero decision values outside the allowed set.

Expected: Every check exits 0 and prints no invalid rows.

---

### Task 8: Rewrite `links.md` as the Detailed Learning Path

**Files:**
- Modify: `links.md`
- Read: All `/tmp/link-dump-audit/candidates-*.md`
- Read: `/tmp/link-dump-audit/decisions.tsv`

**Interfaces:**
- Consumes: Vetted candidate rows and the complete original-resource decision ledger.
- Produces: One canonical document with navigation, progressive sections, six-field resource tables, and project-specific context.

- [ ] **Step 1: Build the document shell**

Create:

- Title and audit date.
- A concise explanation of the selection standard.
- Metadata legend.
- Difficulty and time definitions.
- Linked table of contents.
- Suggested learning routes for Linux operations, Rust systems work, Go CLI work, Python tooling, and application architecture.
- The 15 technical sections plus Career and Certification Resources defined in the design.

Expected: Every design section has a destination heading before resource rows are inserted.

- [ ] **Step 2: Add section introductions**

For each section, write:

- What the learner will understand.
- Useful prerequisites.
- Which of Tom's project themes use the concept.
- A suggested beginner-to-advanced reading order.
- A concise concept note wherever no available resource clears the quality bar.

Expected: The document reads as a learning path even before individual links are followed.

- [ ] **Step 3: Integrate vetted resource rows**

Insert only candidates that passed reachability and quality review. Order them by learning role and difficulty, not by discovery date.

Expected: Every row has exactly six populated fields and one allowed type and difficulty.

- [ ] **Step 4: Remove chronological duplication**

Represent each resource once in its best primary section. When a resource supports another section, use a short internal cross-reference instead of duplicating its URL.

Expected: Normalized URL duplicate report is empty except any explicitly documented exception.

- [ ] **Step 5: Commit the canonical learning path**

Run:

```bash
git diff --check
git add links.md
git -c user.name=claude_2010 -c user.email=262510778+tom2025b@users.noreply.github.com commit -m "docs: rebuild Link Dump as learning path"
```

Expected: Commit succeeds with only `links.md` staged for this commit.

---

### Task 9: Add the Curation Audit Appendices

**Files:**
- Modify: `links.md`
- Read: `/tmp/link-dump-audit/decisions.tsv`
- Read: All `/tmp/link-dump-audit/candidates-*.md`

**Interfaces:**
- Consumes: Final decisions and the set difference between original and curated URLs.
- Produces: Removed/replaced, added, future-gap, and audit-note sections at the end of `links.md`.

- [ ] **Step 1: Add Resources Removed or Replaced**

For each non-keep decision, include the original title and URL, action, specific reason, and replacement title/URL when applicable. Consolidated duplicates may be grouped only when every affected original URL remains identifiable.

- [ ] **Step 2: Add Resources Added**

List every URL not present in the normalized original inventory. Include its title, destination section, and selection reason.

- [ ] **Step 3: Add Future Educational Gaps**

Document concepts where the best available material remains fragmented, overly version-specific, insufficiently practical, or absent. Match each gap to the concise note placed in its relevant learning-path section. Do not manufacture gaps merely to populate the section.

- [ ] **Step 4: Add Audit Notes and exact counts**

Report:

- Audit date.
- Original row and unique-URL counts.
- Final curated resource and unique-URL counts.
- Counts kept, updated, replaced, consolidated, removed, and added.
- Automated and manual verification method.
- Known limitations such as bot-protected resources that required browser confirmation.

- [ ] **Step 5: Commit appendices**

Run:

```bash
git diff --check
git add links.md
git -c user.name=claude_2010 -c user.email=262510778+tom2025b@users.noreply.github.com commit -m "docs: record Link Dump audit decisions"
```

Expected: Commit succeeds and the end of `links.md` contains all four required audit sections.

---

### Task 10: Rewrite the README

**Files:**
- Modify: `README.md`
- Read: `links.md`

**Interfaces:**
- Consumes: The final section structure, audit date, and metadata definitions.
- Produces: A concise, accurate entry point to the repository.

- [ ] **Step 1: Replace the stale topic list**

Describe the major learning routes and link to `links.md` headings rather than listing only the original first eight topics.

- [ ] **Step 2: Explain each metadata field**

Document Type, Title, URL, Why this is valuable, Difficulty, and Estimated time. Explain that official-first does not mean official-only.

- [ ] **Step 3: Explain maintenance and audit status**

State the last audit date, how dead or ambiguous links are treated, and where readers can see removals and additions.

- [ ] **Step 4: Commit the README**

Run:

```bash
git diff --check
git add README.md
git -c user.name=claude_2010 -c user.email=262510778+tom2025b@users.noreply.github.com commit -m "docs: update Link Dump guide"
```

Expected: README accurately matches `links.md` and contains no stale link-count claim.

---

### Task 11: Validate the Finished Repository

**Files:**
- Verify: `links.md`
- Verify: `README.md`
- Verify: `docs/superpowers/specs/2026-07-18-link-dump-modernization-design.md`
- Verify: `docs/superpowers/plans/2026-07-18-link-dump-modernization.md`

**Interfaces:**
- Consumes: The integrated documentation.
- Produces: Evidence that formatting, metadata, coverage, counts, decisions, and URLs satisfy the design.

- [ ] **Step 1: Validate Git and Markdown hygiene**

Run:

```bash
git status --short
git diff --check origin/main..HEAD
rg -n 'T(BD)|T(ODO)|https?://[^ ]*\.\.\.' README.md links.md docs/superpowers
```

Expected: No unintended files, whitespace errors, placeholders, or truncated URLs.

- [ ] **Step 2: Validate allowed metadata**

Parse resource rows and assert:

- Six fields per resource.
- Allowed type value.
- Non-empty title, HTTPS URL, and value statement.
- Allowed difficulty value.
- Non-empty estimated time.

Expected: Zero invalid rows.

- [ ] **Step 3: Validate duplication and search URLs**

Run normalized duplicate detection and:

```bash
rg -n '(youtube\.com/results|google\.com/search|bing\.com/search)' links.md
```

Expected: Both checks print nothing unless a duplicate exception is explicitly documented in Audit Notes.

- [ ] **Step 4: Re-run final URL checks**

Check every unique curated URL using Task 2's curl settings. Manually inspect every ambiguous result and record the outcome in Audit Notes.

Expected: No confirmed dead URL remains in a curated learning-path table.

- [ ] **Step 5: Reconcile counts**

Independently count final rows, unique normalized URLs, and each decision class; compare them with Audit Notes and the Resources Added appendix.

Expected: Every reported count matches the generated count.

- [ ] **Step 6: Check design coverage**

Compare the final document with every goal and acceptance criterion in `docs/superpowers/specs/2026-07-18-link-dump-modernization-design.md`.

Expected: Every criterion is satisfied or a concrete limitation is recorded under Future Educational Gaps or Audit Notes.

---

### Task 12: Independent Review, Completion Summary, and Local Handoff

**Files:**
- Review: `links.md`
- Review: `README.md`
- Create: `/home/tom/projects/_claude-outputs/2026-07-18_link-dump-modernization_summary.md`

**Interfaces:**
- Consumes: Final commits and validation evidence.
- Produces: Independent quality feedback, any required corrections, a clean repository state, and Tom's durable summary.

- [ ] **Step 1: Request independent review**

Use `superpowers:requesting-code-review` to review:

- Compliance with the approved design.
- Resource quality and official-first policy.
- Learning-path progression.
- Audit traceability.
- Metadata consistency.
- Any unsupported claims or obviously weak additions.

Expected: Reviewer findings are concrete and prioritized.

- [ ] **Step 2: Resolve all material findings**

Apply corrections, re-run the affected checks from Task 11, and commit with the required Codex author identity.

- [ ] **Step 3: Use verification-before-completion**

Run the complete Task 11 validation suite on the final commit and capture fresh output before claiming completion.

- [ ] **Step 4: Create Tom's dated summary**

Write a clean Markdown summary containing:

- Scope and outcome.
- Files changed.
- Original and final counts.
- Audit decision totals.
- Major removals and replacements.
- Major topic expansions.
- Validation commands and outcomes.
- Local commit SHAs.
- Any remaining limitations.

Save it exactly as:

```text
/home/tom/projects/_claude-outputs/2026-07-18_link-dump-modernization_summary.md
```

- [ ] **Step 5: Verify the local handoff**

Run:

```bash
git status --short --branch
git log --oneline --decorate -8
test -s /home/tom/projects/_claude-outputs/2026-07-18_link-dump-modernization_summary.md
```

Expected: Worktree is clean, commits are visible locally, and the summary file is non-empty.

- [ ] **Step 6: Present integration options**

Use `superpowers:finishing-a-development-branch` to determine whether Tom wants the local commits pushed directly, published through a review branch/PR, retained locally, or otherwise integrated. Do not push or create a PR before that choice.
