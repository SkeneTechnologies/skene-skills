---
name: generate-growth-template
description: Generate a PLG growth template with actionable strategies from a growth manifest. Use after generating a growth manifest to get specific growth recommendations.
---

Generate a PLG (Product-Led Growth) template with actionable strategies based on a growth manifest.

## Prerequisites

This skill should be run after `/generate-growth-manifest` to have the necessary context about:
- Tech stack capabilities
- Existing growth hubs
- Identified GTM gaps
- Product overview (if available)

## Business type classification

First, classify the project into one of these business types:
- **b2b-saas**: Business software sold to companies
- **developer-tools**: APIs, SDKs, CLIs, developer platforms
- **marketplace**: Two-sided platforms connecting buyers/sellers
- **consumer**: B2C applications for end users
- **enterprise**: Large-scale business solutions

## Growth lever categories

Strategies should target these growth levers:
- **viral**: User-driven distribution (sharing, referrals, invites)
- **retention**: Keeping users engaged (notifications, habits, value)
- **monetization**: Revenue optimization (pricing, upsells, expansion)
- **activation**: Getting users to first value (onboarding, aha moments)
- **acquisition**: Bringing new users in (SEO, content, integrations)

## Output format

```json
{
  "business_type": "b2b-saas | marketplace | consumer | developer-tools | enterprise",
  "growth_strategies": [
    {
      "name": "string - clear strategy name",
      "description": "string - what to implement and expected outcome",
      "priority": "high | medium | low",
      "effort": "low | medium | high",
      "growth_lever": "viral | retention | monetization | activation | acquisition"
    }
  ],
  "quick_wins": [
    "string - immediate actions that can be done in days"
  ],
  "long_term_initiatives": [
    "string - strategic initiatives requiring weeks/months"
  ]
}
```

## Guidelines

- Prioritize strategies that leverage existing tech stack capabilities
- Address the highest-priority GTM gaps first
- Balance quick wins (low effort, fast impact) with strategic initiatives
- Be specific and actionable - avoid generic advice
- Consider the business type when recommending strategies (B2B vs consumer, etc.)
- Provide 3-5 growth strategies, 3-5 quick wins, and 2-3 long-term initiatives
