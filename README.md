# Codex Companion Starter

[中文说明](./README.zh-CN.md)

Prompt templates for turning Codex CLI into a more consistent long-term personal assistant workflow.

This repository is for people who want Codex CLI to do more than answer one-off questions. The prompts here help it:

- keep a stable collaboration style
- initialize local project memory structure
- avoid unnecessary rewrites
- bootstrap user preferences in a lightweight way

The pack is intentionally split into three variants, so you can choose how cautious or proactive Codex should be in your environment.

## Why This Exists

Raw prompts often overfit to an idealized agent model. In practice, Codex CLI behaves better when instructions are:

- explicit about file operations
- careful about existing content
- realistic about what global config can and cannot control
- lightweight enough to avoid blocking normal work

These prompts are written around that reality.

## What's Included

- [codex-cli-personal-assistant-prompt-safe.md](./codex-cli-personal-assistant-prompt-safe.md)  
  Inspect first, change later. Best for first-time setup and existing environments.

- [codex-cli-personal-assistant-prompt-lite.md](./codex-cli-personal-assistant-prompt-lite.md)  
  Balanced default for most day-to-day use.

- [codex-cli-personal-assistant-prompt-strong.md](./codex-cli-personal-assistant-prompt-strong.md)  
  More proactive setup for greenfield projects or when you want Codex to move faster.

- [codex-cli-personal-assistant-prompt-comparison.md](./codex-cli-personal-assistant-prompt-comparison.md)  
  A side-by-side comparison table.

## Quick Start

1. Open the prompt file you want to use.
2. Copy the full `text` code block.
3. Send it to Codex CLI in the target workspace.
4. Let Codex inspect the workspace, update config, and start lightweight bootstrap if appropriate.

## Which Version Should I Use?

| Situation | Recommended |
| --- | --- |
| First time trying this workflow | `safe` |
| Default long-term usage | `lite` |
| New project and you want stronger setup automation | `strong` |
| Existing workspace with a lot of hand-written config | `safe` |

## Recommended Adoption Path

1. Start with `safe` to observe how Codex behaves in your actual environment.
2. Switch to `lite` once the structure and defaults feel right.
3. Use `strong` when you explicitly want Codex to push setup forward with fewer confirmations.

## Design Principles

- Default preference layer, not hard control layer
- Incremental edits over destructive rewrites
- Project-local memory over fake global omniscience
- Lightweight bootstrap over long onboarding forms
- Realistic compatibility with Codex CLI behavior

## Important Boundaries

- `~/.codex/AGENTS.md` should be treated as a default preference layer, not a permanent hard control mechanism.
- `.assistant/` is a local project convention for memory and collaboration context, not a built-in Codex CLI protocol.
- Actual behavior still depends on runtime instructions, tool permissions, and higher-priority context.

## Who This Is For

This project is useful if you want Codex CLI to behave more like:

- a repeatable project assistant
- a workspace-aware collaborator
- a tool that can preserve lightweight context across tasks

It is probably not useful if you only want quick one-off prompts with no local structure.

## Notes

If Codex behaves too aggressively in your environment, fall back to `safe`.

If it is too conservative and does not make enough progress, move to `strong`.

