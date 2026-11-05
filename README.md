# skill-seeker

An [Agent Skill](https://docs.claude.com) that maps a project's requirements to the skills, MCP servers, plugins, libraries, and APIs it needs, then vets each candidate for security before recommending it.

- Searches what is **already installed** first, then registries, then the web
- Recommends the **smallest sufficient set**, each tied to a requirement
- Security-vets every external resource (provenance, permissions, content, supply chain)
- **Never installs or runs anything** without your approval; never invents tools

## Install

Replace `ZaheerAbbasOrakzai/skill-seeker` if your repo name differs.

### Claude Code (plugin marketplace)
```
/plugin marketplace add ZaheerAbbasOrakzai/skill-seeker
/plugin install skill-seeker@skill-seeker-marketplace
```

### Claude Code (manual, personal or per-project)
```bash
git clone https://github.com/ZaheerAbbasOrakzai/skill-seeker.git
cp -r skill-seeker/skills/skill-seeker ~/.claude/skills/          # all projects
# or: cp -r skill-seeker/skills/skill-seeker <your-project>/.claude/skills/
```

### Claude.ai / Claude desktop
1. Download the zip from the latest [Release](../../releases) (the zip must contain the `skill-seeker/` folder at its root).
2. Open **Settings > Capabilities > Skills** and upload the zip (requires Skills / code execution enabled on your plan).

### Claude API
Upload the `skill-seeker/` folder through the Skills API; see Anthropic's Skills documentation for the current endpoint.

## Use
Ask naturally:
- "What MCP server or library should I use to parse invoices in Python?"
- "Here is my project plan; map the requirements to tools we already have and find gaps."
- "Alternatives to X, vetted for security."

## Layout
```
skills/skill-seeker/
  SKILL.md                         workflow and output format
  references/vetting-and-scoring.md   scoring rubric and security checks
.claude-plugin/                    plugin + marketplace manifests
```

## Contributing
Issues and PRs welcome. Keep `SKILL.md` under 500 lines and the description trigger-focused.

## License
MIT
