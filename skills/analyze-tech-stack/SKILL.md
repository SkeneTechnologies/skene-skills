---
name: analyze-tech-stack
description: Analyze a codebase to detect its technology stack including framework, language, database, auth, deployment, package manager, and third-party services. Use when the user wants to understand what technologies a project uses.
---

Analyze the current codebase to detect the technology stack.

## What to examine

1. **Configuration files**: Look for `package.json`, `pyproject.toml`, `Cargo.toml`, `go.mod`, `Gemfile`, `pom.xml`, `build.gradle`, etc.
2. **Source files**: Examine actual source file extensions (.py, .ts, .js, .go, .rs, .rb, etc.)
3. **Environment files**: Check `.env.example`, `.env.local` for service integrations
4. **Deployment configs**: Look for `Dockerfile`, `docker-compose.yml`, `vercel.json`, `netlify.toml`, kubernetes manifests, etc.

## Critical detection rules

**Language detection**: Prioritize actual source files over configuration files. For example, if you see Python source files (.py) but only a `package.json` config file, the language is Python, not JavaScript. Look at file extensions and code syntax in source files.

**Services detection**: Look for dependencies and environment variables indicating:
- Payment processors: Stripe, PayPal, Paddle, LemonSqueezy
- Email services: SendGrid, Mailgun, Postmark, Resend
- Analytics: Segment, Mixpanel, Amplitude, PostHog
- Monitoring: Sentry, DataDog, New Relic, LogRocket
- Communication: Twilio, Plivo
- Search: Algolia, Elasticsearch, Typesense
- Storage: AWS S3, Cloudflare R2, Cloudinary

## Output format

Return your analysis as JSON:

```json
{
  "framework": "string or null (e.g., Next.js, FastAPI, Rails)",
  "language": "string - required (e.g., Python, TypeScript)",
  "database": "string or null (e.g., PostgreSQL, MongoDB)",
  "auth": "string or null (e.g., JWT, OAuth, Clerk)",
  "deployment": "string or null (e.g., Vercel, AWS, Docker)",
  "package_manager": "string or null (e.g., npm, poetry)",
  "services": ["array of service names"]
}
```

Be conservative - only include values you're confident about. Use null for uncertain fields. Return an empty array for services if none are detected.
