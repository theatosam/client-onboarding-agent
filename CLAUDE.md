# Client Onboarding Agent

An AI agent that automates new client onboarding end-to-end (welcome sequences, document collection, scheduling).

## Superpowers

Superpowers is **DISABLED** in this project (`.claude/settings.json`).
Before starting a build session: open `.claude/settings.json` and flip `"superpowers@superpowers-marketplace": false` to `true`.
The global token budget rule (max 2 skills/session) applies once enabled.

## claude-mem

Active in this project. Session observations are captured automatically — no setup needed when you start building.

## Memory

stored in a shared Obsidian vault outside this repository.

**Retrieval protocol:**
1. Run `mcp__obsidian__search-vault` with relevant keywords before answering any question about project state, decisions, or prior work.
2. Run `mcp__obsidian__read-note` to load a specific file when search returns a match (`memory/[filename].md`).
3. Do NOT rely solely on conversation history -- memories persist across sessions in the vault.

**Write protocol (when saving a new memory):**
1. Write to the local memory/ folder (system-enforced, auto-loaded).
2. AND write the same content to `second-brain/memory/` via `mcp__obsidian__create-note` or `mcp__obsidian__edit-note`.
