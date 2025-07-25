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

Quick-Start Recipes

1. Create a ProjectLocal Sub-Agent
```bash
mkdir -p .claude/agents
cat > .claude/agents/code-reviewer.md <<'EOF'
---
name: code-reviewer
description: "Use proactively to review new pull requests for style, security, and test coverage."
tools: grep, view, edit, mcp-gemini
---
You are a senior code reviewer. Provide inline comments and suggest fixes...
EOF
```

Any request that includes “review” language will now trigger this agent automatically.

2. Clone Community Packs
```bash
# Download Derek Dee’s power pack
mkdir -p ~/.claude/agents
curl -sL https://raw.githubusercontent.com/derek-opdee/subagent-example-script/main/sub-agent-tech-debt-finder-fixer.md -o ~/.claude/agents/tech-debt.md

# Download W. Shobson’s 28-agent bundle
git clone https://github.com/wshobson/agents ~/.claude/agents/wh-bundle
```

3. Invoke Explicitly
```text
> Use the test-generator sub agent to create Jest tests for the new Cart module
```

or launch several agents at once:

```text
> Spawn 3 subagents:
> 1. Security audit
> 2. Lint & style check
> 3. Bundle size analysis
```

Claude will queue and run up to 10 tasks in parallel.

Directory Structuring Tips

- Project agents (.claude/agents/) take priority over user-level agents (~/.claude/agents/).
- Prefix agent files with numbers (like 01_, 02_) to sort their order in the /agents listing.
- Keep system prompts brief; long role descriptions increase token use.
- Limit access to only the necessary tools for each agent to maintain security and efficiency.

Common Pitfalls \& Solutions


| Issue | Cause | Solution |
| :-- | :-- | :-- |
| Sub-agent ignores task | Vague description | Use explicit trigger phrases like “use proactively for X” |
| Token blow-ups | Overly long system prompts | Reuse boilerplate; make role descriptions concise |
| No output merge | Each agent authors a full plan | Add a step where the main agent merges all findings |
| Max parallelism at 10 | System-imposed task cap | Batch remaining tasks; more start as others finish |



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
