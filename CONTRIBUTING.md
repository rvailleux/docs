---
hidden: true
---

# Contributing to Apizee Docs

This repository is the GitBook mono-repo for the Apizee Help Center, synced to GitBook via Git Sync. Changes pushed to `master` go live on [apizeelegacy.gitbook.io](https://apizeelegacy.gitbook.io/apizeelegacy-docs) within a few minutes.

---

## Repository layout

| Folder / file | Purpose |
| :--- | :--- |
| `faq/` | FAQ space |
| `video-assistance/` | Video Assistance space |
| `video-assistance-multi/` | Multi-participant Assistance space |
| `meetings/` | Meetings space |
| `telehealth/` | Telehealth space |
| `embed/` | Embed space |
| `salesforce/` | Salesforce integration space |
| `genesys/` | Genesys integration space |
| `servicenow/` | ServiceNow integration space |
| `common/` | Common space (Help Center homepage) |
| `shared/` | Shared includes referenced across spaces |
| `_unassigned/` | Orphaned pages not in any published space |
| `ARCHITECTURE.md` | Site structure decisions and roadmap |

Each space folder contains a `SUMMARY.md` (sidebar navigation), a `README.md` (landing page), and a `.gitbook.yaml` (per-space config). Images live in each space's `.gitbook/assets/` directory.

---

## Git workflow

All changes go on a feature branch, then a pull request to `master`.

```bash
git checkout -b fix/your-description
# edit files
git add <files>
git commit -m "fix: short description of what changed"
git push origin fix/your-description
# open a PR → merge to master → GitBook syncs automatically
```

Commit directly to `master` only for trivial one-liner fixes (typos, single-word corrections).

### Commit message conventions

Follow [Conventional Commits](https://www.conventionalcommits.org/):

| Prefix | When to use |
| :--- | :--- |
| `fix:` | Correcting content, broken links, formatting errors |
| `feat:` | New pages, new sections, new spaces |
| `docs:` | Rewrites, restructuring, editorial improvements |
| `refactor:` | Factorizing duplicates into shared includes, flattening navigation |
| `chore:` | Dependency bumps, sync triggers, tooling |

---

## Content conventions

### Links

Always use **relative file paths** between pages — never absolute URLs pointing back to the GitBook domain.

```markdown
<!-- correct -->
[Reset your password](../../faq/general/i-forgot-my-password-can-i-reset-it.md)

<!-- wrong — breaks in previews and local tools -->
[Reset your password](https://apizeelegacy.gitbook.io/apizeelegacy-docs/faq/general/...)
```

Cross-space links follow the same rule — just traverse up with `../` to reach the sibling space folder.

### Hints

Use the four supported styles: `info`, `success`, `warning`, `danger`. The opening tag, body, and closing tag each go on their own line with no extra blank lines inside.

```markdown
{% hint style="warning" %}
This action cannot be undone.
{% endhint %}
```

### Shared includes

Reusable content blocks (user-role tables, login steps, common notices) live in `shared/.gitbook/includes/`. Reference them with a path relative to the current file:

```markdown
{% include "../../shared/.gitbook/includes/user-roles-table.md" %}
```

Do not duplicate a block that already exists as a shared include — find it first.

### SUMMARY.md

The `SUMMARY.md` in each space defines the sidebar. Navigation is organized **by action category**, not by audience role. The top-level structure per space is:

- Getting started
- (Action-based sections — e.g. "During a session", "Portal", "Administration")

Keep nesting to **at most 3 levels**. GitBook's parser is strict about indentation — use 2-space indents for nested items.

### Page frontmatter

Add YAML frontmatter at the very top of a page when you need to control the description, icon, or visibility. The `---` block must come before any markdown content.

```yaml
---
description: "Short SEO description for this page."
icon: key
hidden: false
---
```

Leave out fields you are not setting — don't add empty placeholders.

---

## What NOT to do

- **Do not add copyright footers** — they were removed during the migration and must not be re-introduced.
- **Do not use absolute `/apizeelegacy-docs/` prefixes** in internal links — use relative paths.
- **Do not link to GitHub raw `.md` URLs** — always link to the rendered GitBook page (or use a relative path).
- **Do not duplicate content** that already exists as a shared include — reuse it.
- **Do not commit `.env`** — it contains live API keys.
- **Do not run `scripts/convert.py`** (in the parent repo) without explicit approval — it would overwrite manual editorial fixes.

---

## Validation before pushing

Before opening a PR:

1. Check that all new internal links point to existing `.md` files.
2. Verify every `{% hint %}` block has both an opening and a closing `{% endhint %}` tag.
3. Confirm images are placed in the relevant space's `.gitbook/assets/` folder and referenced with a relative path.
4. Review your diff in the GitBook preview (or locally) to catch rendering issues with custom blocks.

---

## Questions

For editorial decisions and migration history, see [`ARCHITECTURE.md`](ARCHITECTURE.md) and `../decision.md` (parent repo).
