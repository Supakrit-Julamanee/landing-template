# Landing page template for Claude Code

Everything here is project-scoped: it only works when you run `claude` inside this folder.
Nothing is installed into ~/.claude.

## New client
1. Copy this whole folder:  `cp -R landing-template ~/clients/<client-name>`
2. Fill in `docs/brief.md`
3. `cd ~/clients/<client-name> && claude`
4. Type:  `/landing docs/brief.md`   (add `--auto` to skip the spec approval)

The first time, Claude Code asks you to trust the folder and approve the Playwright MCP server — say yes.

## Remove
Delete the folder. Nothing else on your machine changes.
