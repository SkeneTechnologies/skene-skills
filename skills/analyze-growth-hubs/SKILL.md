---
name: analyze-growth-hubs
description: Identify features with growth potential including viral mechanisms, engagement features, onboarding flows, and monetization capabilities. Use for PLG (Product-Led Growth) analysis.
---

Analyze the current codebase to identify features with growth potential ("growth hubs").

## What qualifies as a growth hub

A growth hub is a feature or area of the codebase that:

1. **Viral growth**: Enables sharing, invitations, referrals, social features, embed codes, public profiles
2. **User engagement**: Notifications, gamification, progress tracking, streaks, achievements, leaderboards
3. **Onboarding**: Tutorials, tooltips, guided flows, setup wizards, welcome emails
4. **Monetization**: Payments, subscriptions, billing, upgrades, premium features, usage limits
5. **Analytics**: Dashboards, reporting, insights, usage tracking, data exports

## What to examine

- Look for invitation/sharing/referral code patterns
- Check for notification systems (email, push, in-app)
- Identify payment integration code (Stripe, PayPal, etc.)
- Find onboarding flows or tutorial components
- Locate analytics/tracking implementations
- Search for gamification elements (points, badges, levels)

## Output format

Return your analysis as a JSON array:

```json
[
  {
    "feature_name": "string - clear, descriptive name",
    "file_path": "string - primary implementation file",
    "detected_intent": "string - what growth purpose this serves",
    "confidence_score": 0.0-1.0,
    "entry_point": "string or null - URL path or function name users interact with",
    "growth_potential": ["array of specific improvement suggestions"]
  }
]
```

## Guidelines

- Focus on quality over quantity - identify the most impactful growth opportunities
- Be specific about file paths and entry points
- Provide actionable suggestions in growth_potential
- Confidence score should reflect how clearly the feature serves a growth purpose
- If no growth hubs are found, return an empty array with a note explaining what growth features could be added
