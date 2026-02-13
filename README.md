# gh-scout

An open-source skill for exploring GitHub repositories from any AI coding agent, using the `gh` CLI.

I really liked [Amp's Librarian](https://ampcode.com/news/librarian) — a subagent that can search remote codebases on GitHub, read framework source code, trace dependencies, and answer architectural questions about any public (or private) repo. It's genuinely one of the best things about Amp (for me).

But I wanted that same capability in Claude Code, and I didn't want to spin up an MCP server or depend on a specific platform to get it. So I built gh-scout: a portable alternative that does Librarian-style GitHub exploration using the `gh` CLI you already have installed.

It works with Claude Code, Amp, or really any agent that can run shell commands.

## What it can do

- **Browse repos** — search repositories, list files, read source code, get full directory trees
- **Search code** — find implementations across repos by pattern, language, or keyword
- **Analyze issues & PRs** — list, filter, read details, view diffs, examine review comments
- **Trace commits** — list history, compare refs, blame files, inspect individual changes
- **Track releases** — list versions, compare tags, review changelogs
- **Gather insights** — contributors, language breakdown, dependency graph, commit activity

## Prerequisites

- [`gh` CLI](https://cli.github.com/) installed and authenticated (`gh auth login`)

## Installation

### Claude Code (plugin)

```
/plugin marketplace add AndrewBastin/gh-scout
/plugin install gh-scout@gh-scout
```

### Universal installer for other agents (npx skills)

```bash
# Install to all detected agents
npx skills add AndrewBastin/gh-scout

# Install to a specific agent
npx skills add AndrewBastin/gh-scout --agent claude-code
npx skills add AndrewBastin/gh-scout --agent amp
```

### Manual (any agent with shell access)

Copy `skills/exploring-github/SKILL.md` into your agent's skill directory. See the [Agent Skills spec](https://agentskills.io) for your agent's path.

## Usage

Once installed, the skill activates automatically when you ask about GitHub repositories. Examples:

- Explore the architecture of denoland/deno
- What issues are open about performance in tokio-rs/tokio?
- Show me the recent PRs merged in rust-lang/rust
- Compare releases v1.0 and v2.0 in some-org/some-repo
- How does React's useEffect cleanup work? Read the source.

## License

MIT
