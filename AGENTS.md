# AGENTS.md — Guidelines and PR Review Rules for AI Agents (awesome-telegram)

This file defines the rules that AI agents (Claude, Codex, automated reviewers, bots, etc.) should follow when reviewing pull requests, evaluating contributions, or helping maintain this repository. `CLAUDE.md` is a symlink to this file.

---

## What this repository is

A curated list of Telegram-related resources: bots, libraries, tools, groups, channels, and integrations.

**The core criterion is: does this have a meaningful relation to Telegram?** It is **relevance to Telegram** — not exclusivity.
Multi-platform tools are welcome as long as they have meaningful Telegram support. Closed-source projects are welcome. The entry just needs to be useful to someone in the Telegram ecosystem.

---

## Acceptance Rules

### ✅ ACCEPT (or approve after minor fixes) if:

- Entry is related to Telegram in some way — bots, libraries, tools, integrations, channels, groups (can also support other platforms)
- Has a valid link (t.me, GitHub, website, etc.)
- Description is a single concise sentence
- Follows the [Format Rules](#format-rules) below, including em dash `–` (not hyphen `-`) ⚠️ STALE: `–` (U+2013) is an en dash — see Format Rules
- Added at the bottom of the correct section ⚠️ STALE: conflicts with the PR template — see Format Rules
- PR title is descriptive (not "Update README.md")

### ⚠️ REQUEST CHANGES if:

| Issue | What to ask |
|---|---|
| Description is missing or vague | Ask for a one-sentence description of what it does |
| Description is too long (more than one sentence) / marketing-heavy | Suggest a trimmed single-sentence version |
| Uses `-` instead of `–` (em dash ⚠️ STALE: `–` is an en dash) | Ask to replace with `–` |
| No link provided | Ask for project page, t.me, or website |
| Bot handle does not match project branding | Ask to clarify / reconcile |
| Wrong section placement | Point to the correct section |
| Entry not placed at the bottom of the relevant section (⚠️ STALE: conflicts with the PR template — see Format Rules) | Ask to move it to the bottom |
| Multi-platform tool placed in `## Tools` | Ask to move to `## Multi-platform Tools` (⚠️ STALE: no such section in README.md — see Section Reference) |
| PR title is "Update README.md" or similarly generic | Ask for a meaningful title |

### ❌ CLOSE/REJECT if:

| Reason | Example |
|---|---|
| Copyright-infringing content | Bot providing unlicensed streaming/download links |
| Crypto trading bot requesting API keys via Telegram | High risk of scam/phishing for users (security risk) |
| Self-promotion of paid/adult gated content | Private VIP content groups |
| PR title is "Update README.md" AND content is low quality | Explicitly violates contributing guidelines |

---

## Format Rules

Entry format:
```
* [Name](https://link.to/project) – Single sentence description.
```

With open-source link (optional, for open-source entries):
```
* [Name](https://t.me/botname) – [Open Source](https://github.com/user/repo) Single sentence description.
```

- Use `–` (em dash, U+2013), not `-` (hyphen) ⚠️ STALE: U+2013 `–` is an en dash, not an em dash; `.github/scripts/check_pr.py` and `.github/pull_request_template.md` call it an en dash and reject the em dash `—` (U+2014). The required character is `–`.
- One entry per line
- Add new entries at the **bottom** of the relevant section ⚠️ STALE: `.github/pull_request_template.md` requires **alphabetical order** within the section (case-insensitive, ignoring `@` and `[`), while `contributing.md` still says "bottom of the relevant category" — the repo contradicts itself; confirm with the owner.
- No trailing punctuation style inconsistency — match the existing list style

---

## Section Reference

| Entry type | Section |
|---|---|
| Telegram bots | `## Bots` |
| Inline bots | `### Inline Bots` |
| Games | `### Games` |
| Python libraries | `### Bot Libs > #### Python` |
| JS/TS/Node libraries | `### Bot Libs > #### Javascript/Typescript/Node` |
| Other language libraries | appropriate `### Bot Libs > #### <Language>` subsection |
| Telegram-specific tools | `## Tools` |
| Multi-platform tools (Telegram + others) | `## Multi-platform Tools` ⚠️ STALE: README.md has no `## Multi-platform Tools` section |
| Telegram themes | `## Themes` |
| Telegram groups | `## Groups` |
| Telegram channels | `## Channels` |
| Bot stores / directories | `## Bot Stores` / `## Telegram Directory` |
| Security-focused channels | `## Security` |

---

## Important Notes

- **Public source code is NOT required.** Closed-source bots, tools, and services are welcome.
- **Multi-platform is OK.** If Telegram is one of several supported platforms, place the entry in `## Multi-platform Tools` (⚠️ STALE: no such section in README.md — see Section Reference).
- **Niche/regional tools are OK.** Region-specific tools (e.g., alerts for a specific country) are accepted.
- **One PR = one entry.** Each PR should add a single entry to the list.
- **New entries go at the bottom of their section.** ⚠️ STALE: conflicts with the PR template — see Format Rules

---

## PR Review Checklist

When reviewing a PR, check:

1. [ ] Does the entry relate to Telegram?
2. [ ] Is there a valid link?
3. [ ] Is the description a single concise sentence?
4. [ ] Does it use `–` (em dash)? ⚠️ STALE: `–` is an en dash — see Format Rules
5. [ ] Is it placed at the bottom of the correct section? ⚠️ STALE: conflicts with the PR template — see Format Rules
6. [ ] Is the PR title meaningful (not "Update README.md")?
7. [ ] Are there any copyright or safety concerns?
8. [ ] If multi-platform, is it in `## Multi-platform Tools`? ⚠️ STALE: no such section in README.md — see Section Reference

---

## Suggested Comment Templates

### Requesting a shorter description:
> The description is a bit long for this list — each entry should be a single concise sentence.
> Suggested: `* [Name](link) – <one sentence>.`

### Requesting a link:
> Could you add a link to the project page or website?

### Requesting description clarity:
> Could you update the description to explain what the bot/tool actually does in one sentence?

### Closing for copyright:
> This entry raises copyright concerns (e.g., provides unlicensed streaming or download links). We cannot include it.

### Closing for safety:
> Crypto trading bots that request API keys via Telegram raise safety concerns for our users. We cannot include this entry.
