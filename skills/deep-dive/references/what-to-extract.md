# Deep Dive Extraction Checklist

**Goal:** Extract EVERYTHING from the codebase so nothing is missed. Check each item systematically.

---

## 1. Project Identity

### Type Detection
- [ ] Check for `bin/` directory or shebang in main file → **CLI Tool**
- [ ] Check for `src/index.ts` with exports → **Library**
- [ ] Check for `src/main.ts` or `app.ts` → **Application**
- [ ] Check for `plugin.json` or `.claude-plugin/` → **Plugin**
- [ ] Check for `src/server.ts` or API routes → **API/Server**
- [ ] Check for `Dockerfile` as sole focus → **Container**
- [ ] Check `package.json` for `bin` field → **CLI Tool**
- [ ] Check `package.json` for `main`/`exports` → **Library**
- [ ] Check `setup.py` for `console_scripts` → **Python CLI**
- [ ] Check `Cargo.toml` for `[[bin]]` → **Rust CLI**

### Entry Points
- [ ] Main export file identified
- [ ] CLI entry point (if applicable)
- [ ] API routes entry (if applicable)
- [ ] Public methods/exports documented

---

## 2. Tech Stack

### Package Managers & Config Files
- [ ] `package.json` - Node.js/JavaScript
- [ ] `package-lock.json` / `yarn.lock` / `pnpm-lock.yaml`
- [ ] `requirements.txt` / `pyproject.toml` / `Pipfile` - Python
- [ ] `Cargo.toml` - Rust
- [ ] `go.mod` - Go
- [ ] `Gemfile` - Ruby
- [ ] `pom.xml` / `build.gradle` - Java
- [ ] `composer.json` - PHP

### Language Version Requirements
- [ ] `engines` field in package.json
- [ ] `requires-python` in pyproject.toml
- [ ] `rust-version` in Cargo.toml
- [ ] `.nvmrc` / `.node-version`
- [ ] `.python-version`

### Framework Detection
**JavaScript/TypeScript:**
- [ ] `react` / `vue` / `angular` / `svelte` - Frontend
- [ ] `express` / `fastify` / `koa` / `nest` - Backend
- [ ] `electron` - Desktop
- [ ] `react-native` - Mobile
- [ ] `commander` / `yargs` / `inquirer` - CLI

**Python:**
- [ ] `fastapi` / `flask` / `django` - Web
- [ ] `click` / `typer` / `argparse` - CLI
- [ ] `pytorch` / `tensorflow` / `transformers` - ML

### Build Tools
- [ ] `tsconfig.json` - TypeScript
- [ ] `webpack.config.js` - Webpack
- [ ] `vite.config.ts` - Vite
- [ ] `rollup.config.js` - Rollup
- [ ] `.babelrc` / `babel.config.js` - Babel
- [ ] `esbuild` in scripts - esbuild
- [ ] `Makefile` / `Justfile` - Make/Just

---

## 3. Dependencies

### Heavy Lifters (Top 5-7)
- [ ] List the critical runtime dependencies
- [ ] Note any with security implications
- [ ] Note any that require special setup

### Dev Dependencies of Note
- [ ] Testing framework (`jest`, `vitest`, `pytest`, `mocha`)
- [ ] Linting (`eslint`, `prettier`, `ruff`, `black`)
- [ ] Type checking (`typescript`, `mypy`)

### System Dependencies
- [ ] Check `Dockerfile` for `apt-get install` commands
- [ ] Check `.github/workflows/*.yml` for setup steps
- [ ] Check `Makefile` for prerequisite checks
- [ ] Check `INSTALL.md` or `docs/installation.md`

**Common system deps to look for:**
- [ ] `libssl-dev` - cryptography
- [ ] `libpq-dev` - PostgreSQL
- [ ] `ffmpeg` - media processing
- [ ] `graphviz` - diagram generation
- [ ] `docker` - containerisation
- [ ] `redis` / `postgres` / `mongodb` - databases

---

## 4. CI/Automation

### GitHub Actions
- [ ] `.github/workflows/` directory exists
- [ ] CI workflow (build/test on PR)
- [ ] Release workflow (publish on tag)
- [ ] Codecov/coverage action present

### Other CI
- [ ] `.circleci/config.yml` - CircleCI
- [ ] `.travis.yml` - Travis
- [ ] `.gitlab-ci.yml` - GitLab CI
- [ ] `Jenkinsfile` - Jenkins
- [ ] `azure-pipelines.yml` - Azure

### Badge Sources
- [ ] Build status badge available
- [ ] Coverage badge available
- [ ] Version/package badge available
- [ ] License badge needed

---

## 5. Documentation State

### Existing Docs
- [ ] `README.md` exists (and current state)
- [ ] `CONTRIBUTING.md` exists
- [ ] `CODE_OF_CONDUCT.md` exists
- [ ] `LICENSE` file exists (which license?)
- [ ] `CHANGELOG.md` exists
- [ ] `docs/` directory exists
- [ ] API documentation exists
- [ ] JSDoc/docstrings present in code

### Missing Standards
- [ ] Note any missing standard files
- [ ] Note any outdated documentation

---

## 6. Friction Analysis

### Time-to-Joy (TTJ)
- [ ] Count exact commands from clone to working result
- [ ] TTJ = 1-2: Excellent
- [ ] TTJ = 3: Good
- [ ] TTJ = 4-5: Acceptable
- [ ] TTJ = 6+: Needs Docker/Makefile

### Weirdness Detector
- [ ] Non-standard config paths (`.codex`, `.opencode`, etc.)
- [ ] Manual environment variable requirements
- [ ] Undocumented prerequisites
- [ ] Platform-specific constraints (Windows/Linux/macOS)
- [ ] Architecture constraints (x86/ARM)

### Copy-Paste Readiness
- [ ] Can commands be copy-pasted without modification?
- [ ] Are there placeholder values that need changing?
- [ ] Are there secrets/keys required?

---

## 7. Value Proposition Sources

### Where to Find the "Why"
- [ ] `package.json` description field
- [ ] Module-level docstrings
- [ ] JSDoc on main exports
- [ ] Existing README intro
- [ ] CLI `--help` text
- [ ] GitHub repo description
- [ ] Comments in main entry file

### Differentiators
- [ ] What does this do that alternatives don't?
- [ ] Performance characteristics
- [ ] Unique features
- [ ] Target audience

---

## 8. User Context (from Chat History)

### If `~/.claude/history.jsonl` exists:
- [ ] Grep for project path
- [ ] Look for "How do I..." patterns (knowledge gaps)
- [ ] Look for "Error..." patterns (common pitfalls)
- [ ] Look for "Why..." patterns (architectural decisions)
- [ ] Look for repeated questions (documentation needs)

### README Implications
| Pattern Found | README Implication |
|---------------|-------------------|
| Config questions | Detailed configuration section |
| Debugging struggles | Troubleshooting section |
| "How do I test" | Testing section with examples |
| Performance questions | Performance section |
| Deployment questions | Deployment guides |

---

## Output: Reality Report

After checking all items, synthesise into:

```markdown
# Deep Dive Findings

## Project Overview
- **Type:** [CLI/library/framework/plugin/app/API]
- **Tech Stack:** [languages, frameworks]
- **Value Proposition:** [1-2 sentence problem/solution]
- **Entry Point:** [main file/command]
- **Confidence:** [High/Medium/Low]

## Dependencies
- **Runtime:** [Node 18+, Python 3.10+, etc.]
- **System:** [any system dependencies]
- **Heavy Lifters:** [top 3-5 critical deps]

## Friction Report
- **TTJ:** [X] commands
- **Install Complexity:** [Low/Med/High]
- **Weirdness:** [any gotchas]
- **Platform Limits:** [any constraints]

## Documentation State
- **Existing:** [what exists]
- **Missing:** [what's needed]
- **Badge Sources:** [available CI/coverage/version]

## User Context
- **Common Struggles:** [from chat history]
- **Decisions Made:** [key decisions]

## Missing Information (Blockers)
- [ ] [anything you couldn't determine]
```

---

## Handoff

**Ask:** "Does this accurately represent the codebase? Any missing information?"

**Then:** Proceed to `crystal-ball` to predict what this project COULD become.
