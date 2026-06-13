# Apizee Documentation — GitBook Mono-repo

This repository contains the migrated Apizee product documentation, synced to GitBook via **Git Sync**.

## Spaces

Each top-level folder maps to a GitBook space:

| Folder | Space | Description |
|--------|-------|-------------|
| `video-assistance/` | Video Assistance | Agent, guest & admin guides for Apizee Video Assistance |
| `embed/` | Embed | Apizee Embed documentation |
| `video-assistance-multi/` | Multi-participant Assistance | Multi-participant video assistance guides |
| `meetings/` | Meetings | Apizee Meeting guides |
| `telehealth/` | Telehealth | Healthcare / telehealth guides |
| `salesforce/` | Salesforce | Salesforce integration |
| `genesys/` | Genesys | Genesys integration |
| `servicenow/` | ServiceNow | ServiceNow integration |
| `faq/` | FAQ | Frequently asked questions & legal |
| `shared/` | — | Shared includes and reusable content blocks |
| `_unassigned/` | — | Orphaned archives not assigned to a space |

> **Do not edit files directly on GitHub** — changes should be made via GitBook's editor (pushed back to this repo) or by editing the source ClickHelp exports and re-running the migration script.

## Migration

- Source: ClickHelp exported archives (`*-exported/` directories)
- Converter: `scripts/convert.py`
- Last run: 2026-06-13
- Status: 1,096 pages converted, 0 broken links, 0 missing assets


