# agent-skills

> **Status: alpha, work in progress.** These skills are in use on one project and will change. Pin a commit if you depend on one.

Skills for coding agents, in the portable `SKILL.md` format that both [Claude Code](https://docs.claude.com/en/docs/claude-code/skills) and [Codex](https://developers.openai.com/codex/skills) load.

## Skills

| Skill | What it does |
|---|---|
| [reviewable-prs](skills/reviewable-prs/SKILL.md) | Keeps pull requests small and clear enough for a human to review in one sitting: a file budget, one idea per PR, a description template, diagrams when a flow changes, and how to split work on GitHub, GitLab, Bitbucket, Azure DevOps and Gerrit. |

## Install

Copy a skill's folder into one of these:

| Agent | One project | Every project |
|---|---|---|
| Claude Code | `.claude/skills/` in the repo | `~/.claude/skills/` |
| Codex | `.agents/skills/` in the repo | `~/.agents/skills/` |

For example, for every project in both agents:

```bash
git clone https://github.com/dornad/agent-skills.git
mkdir -p ~/.claude/skills ~/.agents/skills
cp -R agent-skills/skills/reviewable-prs ~/.claude/skills/
cp -R agent-skills/skills/reviewable-prs ~/.agents/skills/
```

Agents load a skill when they decide a task matches its description. For rules that must always apply, also add a line to the project's `AGENTS.md` or `CLAUDE.md`, such as "Follow the reviewable-prs skill when planning changes and opening pull requests."

## Why

Agents write code faster than people can read it. These skills come from scaffolding an iOS app with AI help and reviewing what the agents produced. The write-up is in progress.

## License

[MIT](LICENSE)
