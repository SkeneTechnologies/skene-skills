---
name: generate-growth-manifest
description: Generate a complete growth manifest combining tech stack and growth hub analyses, identifying go-to-market gaps. Use after running analyze-tech-stack and analyze-growth-hubs skills.
---

Generate a complete growth manifest by combining analysis results from the codebase.

## Prerequisites

Before running this skill, you should have results from:
- `/analyze-tech-stack` (required)
- `/analyze-growth-hubs` (required)
- `/analyze-product-overview` (optional, for v2.0 manifest)
- `/analyze-features` (optional, for v2.0 manifest)

If these haven't been run yet, run them first or gather the information as part of this analysis.

## What to produce

1. **Project identification**: Infer project_name from package files or directory name
2. **Description**: Brief 1-2 sentence project summary
3. **Combined data**: Include tech_stack and growth_hubs from prior analyses
4. **GTM gaps**: Identify missing features that could drive growth

## GTM gap categories to consider

What's missing that could drive growth?
- **User onboarding**: Tutorials, guided setup, welcome flows
- **Viral mechanisms**: Sharing, referrals, invitations, embeds
- **Analytics**: Usage insights, dashboards, reporting
- **Monetization**: Payment integration, subscription management, usage limits
- **Engagement**: Notifications, gamification, email sequences
- **Community**: Forums, comments, user profiles, social features

## Output format

For basic manifest (v1.0):

```json
{
  "version": "1.0",
  "project_name": "string - inferred from codebase",
  "description": "string or null - brief project description",
  "tech_stack": {
    "framework": "string or null",
    "language": "string",
    "database": "string or null",
    "auth": "string or null",
    "deployment": "string or null",
    "package_manager": "string or null",
    "services": []
  },
  "growth_hubs": [],
  "gtm_gaps": [
    {
      "feature_name": "string",
      "description": "string - what's missing and why it matters",
      "priority": "high | medium | low"
    }
  ],
  "generated_at": "ISO 8601 datetime"
}
```

For extended manifest (v2.0) - use when product_overview and features are available:

```json
{
  "version": "2.0",
  "project_name": "string",
  "description": "string or null",
  "tech_stack": {},
  "product_overview": {
    "tagline": "string or null",
    "value_proposition": "string or null",
    "target_audience": "string or null"
  },
  "features": [],
  "growth_hubs": [],
  "gtm_gaps": [],
  "generated_at": "ISO 8601 datetime"
}
```

## Guidelines

- Set priority based on potential impact: high = significant growth lever, medium = helpful improvement, low = nice to have
- Be specific in gap descriptions - explain what's missing and why it matters
- If the project already has strong growth features, acknowledge this and suggest optimizations instead
