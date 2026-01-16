# Roadmap & Future Vision Patterns

**Goal:** Present what the project COULD become without overpromising or creating maintenance burden.

---

## 1. Version Signalling

### Maturity Indicators

| Stage | Signal | README Language |
|-------|--------|-----------------|
| **Alpha** | Experimental, breaking changes expected | "⚠️ Alpha - API may change" |
| **Beta** | Feature-complete, stabilising | "Beta - Feedback welcome" |
| **Stable** | Production-ready | "v1.0+ - Stable API" |
| **Mature** | Battle-tested, widely adopted | "Used in production by X" |

### Version Badge Semantics

```markdown
<!-- Pre-1.0: Unstable -->
![Version](https://img.shields.io/badge/version-0.3.2-orange)

<!-- 1.0+: Stable -->
![Version](https://img.shields.io/badge/version-1.2.0-green)

<!-- With stability indicator -->
![Stability](https://img.shields.io/badge/stability-beta-yellow)
```

---

## 2. Roadmap Section Formats

### Simple List (< 5 items)

```markdown
## Roadmap

- [ ] Config file support
- [ ] Plugin system
- [x] ~~CLI improvements~~ (v1.2)
```

### Table Format (5-15 items)

```markdown
## Roadmap

| Feature | Status | Target |
|---------|--------|--------|
| Config file support | 🔄 In Progress | v1.3 |
| Plugin system | 📋 Planned | v2.0 |
| Windows support | 🤔 Considering | TBD |
```

### Categorised (> 15 items)

```markdown
## Roadmap

### Coming Soon (v1.3)
- Config file support
- Better error messages

### Planned (v2.0)
- Plugin system
- API mode

### Under Consideration
- GUI wrapper
- Cloud sync
```

---

## 3. Status Semantics

Use consistent language to set expectations:

| Status | Meaning | Commitment Level |
|--------|---------|------------------|
| **✅ Done** | Shipped | 100% |
| **🔄 In Progress** | Actively being built | High |
| **📋 Planned** | On the roadmap, will happen | Medium |
| **🤔 Considering** | Might happen, need feedback | Low |
| **💡 Ideas** | Community suggestions | None |
| **❌ Won't Do** | Explicitly out of scope | Negative |

**Important:** Only use "Planned" for things you're committed to. Use "Considering" for maybes.

---

## 4. Technical Debt Presentation

### For Contributors (honest)

```markdown
## Known Issues

| Issue | Impact | Help Wanted |
|-------|--------|-------------|
| O(n²) search in large files | Slow >10k lines | Algorithm expertise |
| No Windows CI | Untested | GitHub Actions |
```

### For Users (actionable)

```markdown
## Limitations

- Large files (>10k lines) may be slow - we're working on it
- Windows support is experimental - please report issues
```

---

## 5. Feature Gap Framing

### Positive Framing (what you DO support)

❌ Don't: "We don't support Windows"
✅ Do: "Supports macOS and Linux. Windows support planned for v2.0"

❌ Don't: "Missing plugin system"
✅ Do: "Core functionality complete. Plugin system coming in v2.0"

### Comparison Tables

```markdown
## Feature Comparison

| Feature | This Tool | Alternative A | Alternative B |
|---------|-----------|---------------|---------------|
| Speed | ⚡ Fast | 🐌 Slow | ⚡ Fast |
| Config | 📋 Planned | ✅ Yes | ❌ No |
| Plugins | 🤔 Considering | ✅ Yes | ✅ Yes |
```

---

## 6. Community Contribution Hooks

### Help Wanted Section

```markdown
## Contributing

We'd love help with:

| Area | What's Needed | Good First Issue |
|------|---------------|------------------|
| Tests | `src/core/` needs coverage | ✅ |
| Docs | API reference incomplete | ✅ |
| Performance | Profiling large files | |
| Windows | CI and compatibility | |
```

### Issue Labels to Reference

```markdown
See issues labelled:
- [`good-first-issue`](link) - Great for new contributors
- [`help-wanted`](link) - We need expertise here
- [`enhancement`](link) - Feature requests
```

---

## 7. Anti-Patterns

### Vaporware Roadmap
❌ Listing 50 features with no timeline or commitment

### Stale Roadmap
❌ "Coming in Q2 2023" when it's 2025

### Overpromising
❌ "Full Windows support coming soon!" (when you haven't started)

### No Roadmap at All
❌ Users can't tell if project is alive or where it's heading

---

## 8. Maintenance Commitment

### Active Project

```markdown
## Status

🟢 **Actively Maintained**

- Bug fixes: Within 1 week
- Security patches: Within 48 hours
- Feature requests: Reviewed monthly
```

### Maintenance Mode

```markdown
## Status

🟡 **Maintenance Mode**

This project is feature-complete. We'll fix critical bugs and security issues but aren't adding new features.
```

### Seeking Maintainers

```markdown
## Status

🟠 **Seeking Maintainers**

I can no longer maintain this project actively. If you're interested in taking over, please open an issue.
```

---

## 9. Performance Claims

### With Evidence

```markdown
## Performance

Benchmarked on M1 MacBook Pro:

| Operation | This Tool | grep | ripgrep |
|-----------|-----------|------|---------|
| 10k files | 0.8s | 2.1s | 0.3s |
| 100k files | 4.2s | 18s | 1.1s |

_Benchmark source: `benchmarks/` directory_
```

### Honest Positioning

```markdown
## Performance

Fast enough for most use cases. For files >100MB, consider [specialized-tool].
```

---

## 10. Security Posture

### For Security-Sensitive Projects

```markdown
## Security

- 🔒 No data sent externally
- 🔒 All dependencies audited monthly
- 🔒 Security issues: security@project.com

See [SECURITY.md](SECURITY.md) for our vulnerability disclosure policy.
```

### For Normal Projects

```markdown
## Security

Found a vulnerability? Please email security@project.com rather than opening a public issue.
```

---

## Output Integration

When crystal-ball identifies opportunities, map them to these patterns:

| Crystal Ball Finding | Roadmap Pattern |
|---------------------|-----------------|
| Performance opportunity | Feature comparison or benchmark section |
| Technical debt | Known Issues (for contributors) |
| Feature gap | Roadmap table with status |
| Security issue | Security section or private disclosure |
| Missing tests | Help Wanted section |
