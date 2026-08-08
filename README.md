# BEFOREVIBE skill

An [agent skill](https://agentskills.io) that teaches your coding agent the
BEFOREVIBE method: grill an app idea with two waves of hard product questions
— each with a recommended answer you edit or accept — BEFORE any code is
written, then generate the visual storyboard, production-ready PRD (free),
logo and screen mockups through the BEFOREVIBE MCP connector.

## Install

**Claude Code**

```bash
mkdir -p ~/.claude/skills/beforevibe
curl -fsSL https://beforevibe.com/skill -o ~/.claude/skills/beforevibe/SKILL.md
```

(from GitHub instead: `curl -fsSL https://raw.githubusercontent.com/BEFOREVIBE/beforevibe-skill/main/beforevibe/SKILL.md`)

(or copy `SKILL.md` into `~/.claude/skills/beforevibe/` — per-project:
`.claude/skills/beforevibe/`)

Then just describe an app idea; the skill triggers on its own, or say
"grill my idea".

**Other agents** — any agent that reads `SKILL.md`-style skills (Cursor,
Codex CLI, …): copy the `beforevibe/` folder into that agent's skills
directory.

## The deliverables

The grill itself is free and runs in the conversation. For the visual
storyboard, the PRD, the logo and the AI screen mockups, the skill hands off
to the BEFOREVIBE MCP connector:

```bash
claude mcp add --transport http beforevibe https://beforevibe.com/api/mcp
```

PRD: free. Logo and screens: credits (5 free every month). Details:
https://beforevibe.com/mcp

## License

MIT — grill freely.
