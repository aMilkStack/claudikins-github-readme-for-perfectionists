<p align="center">
  <img src="assets/banner.png" alt="GitHub README for Perfectionists" width="100%">
</p>

# claudikins-grfp

A Claude Code plugin that writes high-quality README files through dual-AI collaborative analysis.

## What It Does

**The Problem:** Writing good README documentation is tedious. You know your code, but explaining it clearly to others takes time you'd rather spend coding.

**The Solution:** This plugin analyses your codebase and researches what works in similar projects, then co-authors a README with you section by section.

**Key Features:**
- **Parallel AI analysis:** Claude + Gemini analyse your code simultaneously, then compare notes
- **Competitive research:** Finds and scores exemplar READMEs from similar projects
- **Co-authoring workflow:** Draft, review, iterate - you stay in control
- **Update mode:** Smart diff-merge that preserves your manual edits
- **Quality metrics:** Readability scores, time-to-joy tracking, visual density checks

## Installation

Add to your Claude Code plugins:

```bash
# Via marketplace (when available)
claude plugins install claudikins-github-readme

# Or clone directly
git clone https://github.com/[user]/claudikins-github-readme ~/.claude/plugins/claudikins-github-readme
```

## Requirements

**Optional but recommended:**
- [claudikins-tool-executor](https://github.com/[user]/claudikins-tool-executor) - Enables Gemini integration and Serena semantic search

Without tool-executor, the plugin works but uses only Claude's native tools.

## Usage

The plugin triggers automatically when you mention README-related tasks:

```
"Write a README for this project"
"Update my README"
"Improve the documentation"
"Document this project"
```

### Workflow

1. **Style selection:** Choose spelling (British/American) and tone (Minimal/Conversational/Opinionated/Reference)
2. **Parallel analysis:** Two agents analyse your codebase and research similar projects simultaneously
3. **Synthesis:** Findings are combined and brainstormed
4. **Section planning:** You approve the structure before writing begins
5. **Co-authoring:** Each section is drafted, reviewed, and refined with your feedback
6. **Final review:** Quality checklist ensures nothing is missed

### Update Mode

When a README.md already exists, the plugin:
- Parses existing sections
- Identifies what's stale (missing new features, outdated prereqs)
- Updates only stale sections
- Preserves your manual customisations
- Presents changes as a diff for review

## Components

### Skills

| Skill | Purpose |
|-------|---------|
| `readme` | Main orchestrator - coordinates workflow, enforces style rules |
| `codebase-analysis` | Methodology for extracting project info and user patterns |
| `readme-research` | Methodology for finding and scoring exemplar READMEs |

### Agents

| Agent | Purpose | Tools |
|-------|---------|-------|
| `codebase-analyser` | Analyses project structure, tech stack, code quality | Read, Glob, Grep, Bash, WebFetch |
| `readme-researcher` | Finds and evaluates similar project READMEs | Read, WebSearch, WebFetch |
| `readme-writer` | Produces README content following templates | Read, Write, Glob, Grep |

## Style Rules

All generated content follows these rules:

- Clear and concise
- Active voice
- Important information first
- No M dash (—) - ever
- Technical only, no marketing fluff
- British spelling by default (American on request)

## Quality Metrics

The plugin tracks:

| Metric | Target |
|--------|--------|
| Flesch-Kincaid readability | Grade 8-10 |
| Time to Joy (commands to first result) | ≤3 |
| Visual density | 1 visual per 300 words |
| Badge count | 5-7 max |

## Gemini Integration

When used with claudikins-tool-executor, the plugin leverages:

- `gemini.analyze_code()` - Code quality, security, performance, bug analysis
- `gemini.deep_research()` - Comprehensive README research
- `gemini.brainstorming()` - Claude + Gemini collaborative idea refinement

Both AIs work in parallel, then synthesise their findings for better results than either alone.

## Contributing

Contributions welcome. This plugin follows the patterns established in [plugin-dev](https://github.com/anthropics/claude-code-plugins).

## License

[MIT](LICENSE)

---

*Built with the claudikins-github-readme plugin (yes, it documented itself).*
