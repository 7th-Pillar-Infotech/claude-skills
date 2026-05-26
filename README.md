# 7th Pillar — Claude Code Skills

Shared skills for the team to use with [Claude Code](https://claude.ai/code). Each skill is a reusable workflow that any team member can invoke with a slash command.

## Available Skills

| Skill | Command | What it does |
|-------|---------|-------------|
| Case Study Generator | `/case-study` | Analyzes a project repo and generates a publish-ready case study for website and LinkedIn |

## Setup (One-Time)

### Option A: Symlink (recommended — auto-updates with git pull)

```bash
git clone git@github.com:7th-Pillar-Infotech/claude-skills.git ~/7thPillar/claude-skills
ln -s ~/7thPillar/claude-skills/skills/* ~/.claude/skills/
```

### Option B: Copy

```bash
git clone git@github.com:7th-Pillar-Infotech/claude-skills.git ~/7thPillar/claude-skills
cp -r ~/7thPillar/claude-skills/skills/* ~/.claude/skills/
```

> With Option A, run `cd ~/7thPillar/claude-skills && git pull` to get skill updates.
> With Option B, re-copy after updates.

## Usage

Open any project in Claude Code and type the skill command:

```
/case-study
```

Claude will scan the project, ask a few questions, and generate `CASE-STUDY.md` with both a full website version and a short LinkedIn post.

## Adding New Skills

1. Create a new directory under `skills/` with a `SKILL.md` file
2. Follow the [skill format spec](https://agentskills.io/specification)
3. Open a PR for review

## Structure

```
skills/
  case-study/
    SKILL.md          # Skill definition
  future-skill/
    SKILL.md
```
