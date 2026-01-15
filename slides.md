---
marp: true
theme: default
paginate: true
style: |
  @import url('https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;700&family=Outfit:wght@400;500;600;800&display=swap');

  :root {
    /* Original Palette */
    --bg: #0f1419;
    --bg-surface: #1a1f26;
    --bg-elevated: #242a33;
    --text: #e6e6e6;
    --text-muted: #8b949e;
    --accent: #f59e0b;
    --accent-dim: #d97706;
    --link: #60a5fa;
    --border: #30363d;

    /* Glassmorphism Variables */
    --glass-bg: rgba(255, 255, 255, 0.05);
    --glass-border: rgba(255, 255, 255, 0.1);
    --glass-shadow: 0 20px 40px rgba(0, 0, 0, 0.25);
  }

  section {
    background: var(--bg);
    color: var(--text);
    font-family: 'Outfit', -apple-system, sans-serif;
    padding: 60px 80px;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  h1, h2 {
    font-family: 'Outfit', sans-serif;
    font-weight: 800;
    line-height: 1.1;
  }

  h1 {
    font-size: 3.2em;
    margin-bottom: 0.3em;
    color: var(--text);
    /* Removed gradient, kept drop shadow for depth */
    filter: drop-shadow(0 4px 12px rgba(0, 0, 0, 0.5));
  }

  h2 {
    font-size: 2em;
    color: var(--accent) !important;
    margin-bottom: 0.8em;
    border-bottom: none;
  }

  a {
    color: var(--link);
    text-decoration: none;
    border-bottom: 2px solid transparent;
    transition: all 0.3s ease;
  }

  a:hover {
    border-bottom-color: var(--link);
    filter: drop-shadow(0 0 8px rgba(96, 165, 250, 0.4));
  }

  p, li {
    font-size: 1.25em;
    line-height: 1.6;
    color: var(--text);
  }

  strong {
    color: var(--accent);
    font-weight: 600;
  }

  li::marker {
    color: var(--accent);
  }

  code {
    font-family: 'JetBrains Mono', monospace;
    background: var(--bg-surface);
    color: var(--accent);
    padding: 0.1em 0.4em;
    border-radius: 6px;
    font-size: 0.85em;
    border: 1px solid var(--border);
  }

  pre {
    background: var(--bg-surface) !important;
    backdrop-filter: blur(12px);
    -webkit-backdrop-filter: blur(12px);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 1.5em !important;
    box-shadow: var(--glass-shadow);
    margin-top: 1em;
  }

  pre code {
    background: none;
    padding: 0;
    color: var(--text);
    text-shadow: none;
    border: none;
  }

  /* Title Slide Specifics */
  section.title h1 {
    font-size: 4.5em;
    margin-bottom: 0.2em;
  }

  section.title h1 a {
    color: var(--text);
    border-bottom: 3px solid var(--accent);
  }

  section.title p {
    font-size: 1.5em;
    color: var(--text-muted);
    opacity: 0.9;
  }

  section.title p a {
    color: var(--text-muted);
  }

  /* Lead Slide Specifics */
  section.lead {
    text-align: center;
  }

  section.lead h1 {
    font-size: 3.5em;
    color: var(--accent);
  }

  section.lead p, section.lead a {
    color: var(--text-muted);
  }

  /* Tables */
  table {
    border-collapse: separate;
    border-spacing: 0;
    margin: 1.5em auto;
    border-radius: 12px;
    overflow: hidden;
    border: 1px solid var(--border);
    background: var(--bg-surface);
    backdrop-filter: blur(10px);
  }

  th, td {
    padding: 1em 1.5em;
    border-bottom: 1px solid var(--border);
    border-right: 1px solid var(--border);
    color: var(--text);
  }

  th {
    background: var(--bg-elevated);
    color: var(--accent);
    font-weight: 600;
    text-transform: uppercase;
    font-size: 0.85em;
    letter-spacing: 0.05em;
  }

  tr:last-child td {
    border-bottom: none;
  }

  th:last-child, td:last-child {
    border-right: none;
  }

  /* Grid Layout for Quick Reference */
  .grid-layout {
    display: grid;
    grid-template-columns: 1fr 1fr;
    gap: 30px;
    margin-top: 20px;
  }

  .card {
    background: var(--bg-surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 24px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    transition: all 0.2s ease;
    backdrop-filter: blur(8px);
    box-shadow: 0 4px 6px rgba(0,0,0,0.1);
  }

  .card:hover {
    transform: translateY(-4px);
    border-color: var(--accent);
    box-shadow: 0 10px 20px rgba(0,0,0,0.2);
  }

  .card h3 {
    font-size: 1.25em;
    color: var(--accent);
    margin: 0;
    font-weight: 600;
  }

  .card code {
    font-size: 0.9em;
    background: var(--bg-elevated);
    align-self: flex-start;
    border: 1px solid var(--border);
  }

  .card .tag {
    font-size: 0.8em;
    color: var(--text-muted);
    background: rgba(255,255,255,0.05);
    padding: 4px 10px;
    border-radius: 100px;
    align-self: flex-start;
    display: flex;
    align-items: center;
    gap: 6px;
  }

  /* Flow Layout for Concepts Slide */
  .flow-container {
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 20px;
    margin-top: 40px;
  }

  .flow-card {
    background: var(--bg-surface);
    border: 1px solid var(--border);
    border-radius: 16px;
    padding: 30px;
    display: flex;
    flex-direction: column;
    align-items: center;
    text-align: center;
    gap: 10px;
    flex: 1;
    backdrop-filter: blur(8px);
    transition: all 0.3s ease;
  }

  .flow-card h3 {
    font-size: 1.5em;
    margin: 0;
    color: var(--text);
  }

  .flow-card.highlight {
    border-color: var(--accent);
    background: rgba(34, 211, 238, 0.05);
  }

  .flow-card.accent {
    border-color: #e879f9;
    background: rgba(232, 121, 249, 0.05);
    box-shadow: 0 0 30px rgba(232, 121, 249, 0.15);
  }

  .arrow {
    font-size: 2em;
    color: var(--text-muted);
    opacity: 0.5;
  }
---

<!-- _class: title -->

# [CLAUDE.md](https://docs.anthropic.com/en/docs/claude-code/memory)

Custom instructions that Claude Code reads automatically.

---

<!-- _class: title -->

# [AGENTS.md](https://agents.md)

Custom instructions that coding agents read automatically.

[Codex CLI](https://github.com/openai/codex) · [Gemini CLI](https://github.com/google-gemini/gemini-cli) · [Cursor](https://cursor.com) · [OpenCode](https://opencode.ai)

---

<!-- _class: lead -->

# Be concise.

[Models can only follow a few instructions before failing.](https://arxiv.org/html/2507.11538v1)

---

<!-- _class: centered -->

<div class="flow-container">
  <div class="flow-card">
    <h3>📉 Fewer Concepts</h3>
  </div>

  <div class="arrow">→</div>

  <div class="flow-card highlight">
    <h3>🎯 More Focus</h3>
  </div>

  <div class="arrow">→</div>

  <div class="flow-card accent">
    <h3>🚀 Better Results</h3>
  </div>
</div>

<p style="text-align: center; margin-top: 40px; color: var(--text-muted);">
  If you tell someone 100 things, they'll struggle to remember them all.
</p>

---

## Why conciseness matters

Models don't "think" - they generate text based on previous text.

**What the model sees:**
- System prompt + CLAUDE.md files
- Code files it reads
- MCP server responses, tool results, etc

Confusing or unrelated content **increases entropy** - the model has more noise to work through.

---

## Keep context clean

**Be concise.** Only include what the model truly needs.

**Start fresh often.** Use `/new` or exit and relaunch sessions frequently.

Every instruction competes for the model's attention.

---

## When CLAUDE.md Loads

```
~/.claude/CLAUDE.md     # Always loaded (personal prefs)

~/pla/CLAUDE.md         # Loaded when you start a session here

~/pla/CLAUDE.local.md   # Personal additions (gitignored)
```

All files are **loaded and appended**. Treat changes like code review.

---

## Progressive Disclosure

Add CLAUDE.md files in subdirectories - loaded only when working there.

---

```
project/
├── CLAUDE.md              # Build commands, architecture
├── src/
│   ├── CLAUDE.md          # Code patterns
│   └── models/
│       └── CLAUDE.md      # Model conventions
├── tests/
│   └── CLAUDE.md          # Test utilities
└── docs/
    └── CLAUDE.md          # Doc style
```

`tests/CLAUDE.md` loads **only when working in** `tests/`.

---

## Rules

For larger projects: `.claude/rules/*.md`

- Works like Cursor's rules system
- Path-specific with YAML frontmatter (`paths: ["src/**/*.ts"]`)
- Same priority as CLAUDE.md - they coexist

---

## Writing Tips

- **Be concise** - read and be skeptical of every line
- **Be specific** - "Use Pest" not "Use appropriate testing"
- **Include commands** - `npm run dev`, `zar migrate`
- **Skip obvious things** - no standard conventions
- **No code formatting rules** - it's not an expensive, slow linter

---

## Example: Root

```markdown
# Project Name

Laravel 11 + Livewire 3. SingleStore database.

## Commands
- `zar migrate` - Run migrations
- `zex vendor/bin/pint --dirty` - Format code

## Patterns
- Multi-tenant: filter by tenant_id
```

---

## Example: Subdirectory

```markdown
# tests/CLAUDE.md

## Multi-tenancy
Call `createNewTenantAndSetAsCurrent()` in beforeEach().

## Factories
Located in `database/factories/`.
```

---

<!-- _class: centered -->

## Quick Reference

<div class="grid-layout">
  <div class="card">
    <h3>Global</h3>
    <code>~/.claude/CLAUDE.md</code>
    <div class="tag">Scope: Personal</div>
  </div>

  <div class="card">
    <h3>Project</h3>
    <code>./CLAUDE.md</code>
    <div class="tag">Scope: Project • Git: Yes</div>
  </div>

  <div class="card">
    <h3>Subdirectory</h3>
    <code>./dir/CLAUDE.md</code>
    <div class="tag">Scope: Nested • Git: Yes</div>
  </div>

  <div class="card">
    <h3>Personal</h3>
    <code>**/CLAUDE.local.md</code>
    <div class="tag">Scope: Local • Git: No</div>
  </div>

  <div class="card">
    <h3>Rules</h3>
    <code>.claude/rules/*.md</code>
    <div class="tag">Scope: Project • Git: Yes</div>
  </div>
</div>
