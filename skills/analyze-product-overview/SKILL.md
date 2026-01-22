---
name: analyze-product-overview
description: Extract product overview (tagline, value proposition, target audience) from README and documentation files. Use when documenting what a product does and who it's for.
---

Analyze the documentation files in the current codebase to extract product overview information.

## What to examine

1. **README.md**: Focus on introduction and first paragraphs
2. **Package description fields**: `package.json` description, `pyproject.toml` description
3. **Documentation files**: Look in `/docs`, `/documentation`, or similar directories
4. **About/Overview sections**: Marketing copy, landing page content if present

## What to extract

1. **Tagline**: A short one-liner (under 15 words) that captures what the product does
2. **Value Proposition**: What problem does this solve? Why should someone use it? (2-3 sentences)
3. **Target Audience**: Who is this product for? (e.g., developers, marketers, enterprises, small businesses)

## Guidelines

- Be concise but informative
- Write from the perspective of explaining the product to someone new
- If information isn't clearly stated, make reasonable inferences from the codebase context
- Use null for fields you cannot confidently determine

## Output format

Return your analysis as JSON:

```json
{
  "tagline": "string or null (under 15 words)",
  "value_proposition": "string or null (2-3 sentences)",
  "target_audience": "string or null (e.g., developers, enterprises)"
}
```
