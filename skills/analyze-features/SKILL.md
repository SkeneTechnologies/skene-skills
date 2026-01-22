---
name: analyze-features
description: Document user-facing features from source code with human-readable descriptions, categories, and usage examples. Use when creating feature documentation.
---

Analyze the current codebase to document user-facing features.

## What to focus on

- Features users interact with directly
- Core functionality, not internal utilities or helpers
- Clear, non-technical descriptions where possible
- The value each feature provides to users

## Feature categories

Common categories to use:
- **Authentication**: Login, signup, password reset, SSO
- **API**: Endpoints, webhooks, integrations
- **Data Management**: CRUD operations, imports, exports
- **UI**: Components, pages, layouts
- **Communication**: Email, notifications, messaging
- **Billing**: Payments, subscriptions, invoices
- **Admin**: Dashboard, settings, user management
- **Collaboration**: Sharing, teams, permissions

## Output format

Return your analysis as a JSON array:

```json
[
  {
    "name": "string - human-readable feature name (not code identifiers)",
    "description": "string - user-facing description, 1-2 sentences, non-technical",
    "file_path": "string or null - primary implementation file",
    "usage_example": "string or null - short code snippet or usage example",
    "category": "string or null - feature category"
  }
]
```

## Guidelines

- Prioritize the most important 5-10 features
- Quality over quantity
- Write descriptions that a non-technical person could understand
- Include usage examples only when they add value (API endpoints, CLI commands, etc.)
- Use consistent category names across features
