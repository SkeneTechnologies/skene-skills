# Skene Skills

A Claude Code plugin for PLG (Product-Led Growth) analysis. Analyze codebases to identify growth opportunities, document features, and generate actionable growth strategies.

## Installation

In Claude Code:

```
/plugin marketplace add SkeneTechnologies/skene-marketplace
/plugin install skene@skene
```

See [Claude Code plugins documentation](https://code.claude.com/docs/en/discover-plugins) for more details.

## Available Skills

| Skill | Description |
|-------|-------------|
| `/skene:analyze-tech-stack` | Detect technology stack (framework, language, database, services) |
| `/skene:analyze-product-overview` | Extract product info from README and docs |
| `/skene:analyze-growth-hubs` | Identify viral, engagement, and monetization features |
| `/skene:analyze-features` | Document user-facing features |
| `/skene:generate-growth-manifest` | Combine analyses and identify GTM gaps |
| `/skene:generate-growth-template` | Generate PLG growth strategies |

## Usage

For a complete PLG analysis, run the skills in this order:

```
/skene:analyze-tech-stack
/skene:analyze-growth-hubs
/skene:analyze-product-overview
/skene:analyze-features
/skene:generate-growth-manifest
/skene:generate-growth-template
```

## License

MIT
