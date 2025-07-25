# Awesome Claude Agents 🚀

A community-driven collection **Claude Code agents** and sub-agents—turn your Claude instance into an unstoppable team of domain experts! This repo catalogs plug-and-play agents, agent frameworks, and orchestration recipes contributed by the community and curated from public sources.

### What are Claude Agents?

**Claude Agents** are specialized, task-focused AI "teammates" defined via simple Markdown+YAML files. Each agent lives in `.claude/agents/` and is scoped with a clear role, tool set, and behaviour prompt. With sub-agent support, Claude Code can now delegate complex projects to expert agents who work in parallel—just like a real engineering team!

## 🌟 Featured Agents & Repos

| Name | Type | Role / Highlights | Link |
|---|---|---|---|
| Tech Debt Finder & Fixer | Sub-Agent | Scans codebase for debt, refactors, and automates fixes with test validation | [derek-opdee/subagent-example-script] |
| Architecture Reviewer | Sub-Agent | Detects circular deps, generates diagrams, flags anti-patterns | [derek-opdee/subagent-example-script] |
| Test Generator | Sub-Agent | Suggests, writes, and integrates tests for uncovered paths | [derek-opdee/subagent-example-script] |
| Performance Optimizer | Sub-Agent | Analyzes bundle size, boosts DB/index/query speed, optimizes React | [derek-opdee/subagent-example-script] |
| 28-Subagent Power Pack | Repo | Security, compliance, changelogs, SQL tuning & more (ready-to-use agents) | [wshobson/agents] |
| Claude Code Dev Kit | Meta-Repo | Sets up docs, multi-agent templates, hooks & MCP server integration | [peterkrueck/Claude-Code-Development-Kit] |

## 📚 How to Use

### 1. Clone an Agent Repo
```bash
git clone https://github.com/derek-opdee/subagent-example-script.git ~/.claude/agents/dee-pack
# Or, for 28 ready-made agents:
git clone https://github.com/wshobson/agents ~/.claude/agents/wh-bundle
```
Or just copy individual `.md` agent files into your project’s `.claude/agents/` directory.

### 2. View or Create Agents
```bash
claude /agents
```
You’ll see your agents listed with descriptions and tool scopes. Create your own with the interactive prompt or by dropping in new Markdown files!

### 3. Invoke Agents
Tell Claude to use them—automatically or explicitly:

```text
> Use the test-generator sub agent to write Jest tests for cart.js
> Run security audit in parallel with bundle analysis (spawn 2 agents)
```

### 4. Mix, Match, and Share!
Mix and match roles, tweak YAML front-matter, and contribute your own agents back to this directory!

## ✨ Tips for Creating Great Agents

- **Specialise Roles:** “Proactively review PRs for security and lint errors,” “only optimize SQL queries in src/db/.”
- **Limit Permissions:** List only the tools/commands each agent truly needs for maximum safety.
- **Keep Context Lean:** Set concise system prompts to control token cost per spawn.
- **Provide Dry-Run / Interactive Modes:** Where possible, so users stay in control.

## 🤝 Contributing

- Fork this repo, add your `my-unique-agent.md` files to the main directory, and open a PR.
- Include a short description and a working example in each agent file.
- Want your own agent repo included? Submit a link and summary via PR or issue.


## License

MIT License for this directory. Individual agent files may contain separate copyright/attribution info.

## Credits

Big thanks to everyone building and open-sourcing specialist Claude agents—your work powers this community!  
Want to be featured? Suggest your repo or agent file via PR or issue.

: https://github.com/derek-opdee/subagent-example-script  
: https://github.com/wshobson/agents  
: https://github.com/peterkrueck/Claude-Code-Development-Kit

> “The most powerful Claude agents feel like hiring a team of experts—but you get code reviews, migrations, and tests done in minutes.”  
> – Community Contributor

*Happy hacking! Add, remix, and power up your Claude!*
