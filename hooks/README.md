# Claude Code Destructive Bash Command Blocker Hook

A lightweight, zero-dependency `pre-tool-use` hook for Claude Code that intercepts and blocks dangerous commands before execution.

## 🛡️ Blocked Command Patterns
- `rm -rf` / `rm -fr` (recursive force wipes)
- `git push --force` / `git push -f`
- `DROP TABLE`
- `TRUNCATE`
- `DELETE FROM` without a `WHERE` clause

Every blocked attempt is logged to `~/.claude/hooks/blocked.log` with timestamp, project path, and attempted command.

## 🚀 Quickstart (Installation in 2 Commands)

```bash
mkdir -p ~/.claude/hooks && curl -sSL https://raw.githubusercontent.com/claude-builders-bounty/claude-builders-bounty/main/hooks/pre-tool-use.py -o ~/.claude/hooks/pre-tool-use.py
chmod +x ~/.claude/hooks/pre-tool-use.py
```
