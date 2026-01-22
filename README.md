# Skene Skills

Agent skills for PLG (Product-Led Growth) analysis. These skills help AI agents analyze codebases to identify growth opportunities, document features, and generate actionable growth strategies.

## Available Skills

| Skill | Description |
|-------|-------------|
| `analyze-tech-stack` | Detect technology stack (framework, language, database, services) |
| `analyze-product-overview` | Extract product info from README and docs |
| `analyze-growth-hubs` | Identify viral, engagement, and monetization features |
| `analyze-features` | Document user-facing features |
| `generate-growth-manifest` | Combine analyses and identify GTM gaps |
| `generate-growth-template` | Generate PLG growth strategies |

## Installation

### Claude Code

Add to your Claude Code settings (`~/.claude/settings.json`):

```json
{
  "agentSkills": [
    {
      "source": "github:SkeneTechnologies/skene-skills",
      "prefix": "skene"
    }
  ]
}
```

Then use skills with the prefix:

```
/skene:analyze-tech-stack
/skene:analyze-growth-hubs
/skene:generate-growth-manifest
```

Or install without a prefix to use skills directly:

```json
{
  "agentSkills": [
    {
      "source": "github:SkeneTechnologies/skene-skills"
    }
  ]
}
```

For more details on agent skills, see the [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code/agent-skills).

## Usage Flow

For a complete PLG analysis:

1. `/analyze-tech-stack` - Understand the technology
2. `/analyze-growth-hubs` - Find existing growth features
3. `/analyze-product-overview` - Document the product (optional)
4. `/analyze-features` - Document features (optional)
5. `/generate-growth-manifest` - Combine into a manifest
6. `/generate-growth-template` - Get actionable strategies

## License

MIT
