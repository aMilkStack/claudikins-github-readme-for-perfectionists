# Structural Templates

Complete templates for each README section.

## 1. Hero Section

```markdown
<!-- Banner if project has one -->
<p align="center">
  <img src="banner.png" alt="Project Name" width="600">
</p>

<!-- Badges: 5-7 max, consistent style -->
<p align="center">
  <a href="..."><img src="badge1" alt="Build"></a>
  <a href="..."><img src="badge2" alt="Coverage"></a>
  ...
</p>

# Project Name

> Tagline: One sentence value proposition (problem → solution)
```

## 2. Description

```markdown
## What is [Project]?

[Project] does X for Y. Instead of [tedious manual approach], you [simple action] and get [result].

**Key Features:**
- [Feature 1]: [Benefit]
- [Feature 2]: [Benefit]
- [Feature 3]: [Benefit]
```

**Pattern:** Show value through contrast, not "Problem/Solution" headers.

## 3. Table of Contents

Only include if README > 200 lines:

```markdown
## Table of Contents

- [Installation](#installation)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)
```

## 4. Installation

```markdown
## Installation

### Prerequisites
- [Requirement 1] (version X+)
- [Requirement 2]

### Package Manager
\`\`\`bash
npm install project-name
\`\`\`

### From Source
\`\`\`bash
git clone https://github.com/user/project
cd project
npm install
npm run build
\`\`\`

### Docker (if TTJ > 3)
\`\`\`bash
docker run -it project-name
\`\`\`
```

## 5. Quick Start

```markdown
## Quick Start

\`\`\`typescript
// The simplest possible working example
import { thing } from 'project-name';

const result = thing.doSomething();
console.log(result);
\`\`\`

**Output:**
\`\`\`
Expected output here
\`\`\`
```

## 6. Usage

```markdown
## Usage

### Basic Usage
[Code example with explanation]

### Advanced Usage
<details>
<summary>Click to expand</summary>

[Advanced configuration, options, edge cases]

</details>
```

## 7. Configuration

```markdown
## Configuration

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `option1` | string | `"default"` | What it does |
| `option2` | boolean | `false` | What it controls |
```

## 8. Contributing

```markdown
## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

### Development Setup
\`\`\`bash
git clone https://github.com/user/project
cd project
npm install
npm test
\`\`\`
```

## 9. License

```markdown
## License

[MIT](LICENSE) - see LICENSE file for details.
```
