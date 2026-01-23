---
name: setup-skene-growth
description: Setup skene-growth dependencies and guide the user through configuration
---

# Setup skene-growth

Guide the user through setting up skene-growth step by step.

## Step 1: Check and install uvx

1. Check if uvx is installed: `which uvx` or `uvx --version`
2. If not installed, run: `curl -LsSf https://astral.sh/uv/install.sh | sh`

## Step 2: Choose LLM provider

Ask the user which LLM provider they want to use:

| Provider | Model Default | API Key Required |
|----------|---------------|------------------|
| **openai** | gpt-4o-mini | Yes |
| **gemini** | gemini-2.0-flash | Yes |
| **anthropic** | claude-sonnet-4-20250514 | Yes |
| **lmstudio** | (local) | No |
| **ollama** | llama2 | No |

For local providers (lmstudio, ollama), no API key is needed.

## Step 3: Help user get an API key (if needed)

If the user needs help getting an API key, guide them:

### OpenAI
1. Go to https://platform.openai.com/api-keys
2. Sign in or create an account
3. Click "Create new secret key"
4. Copy the key (it won't be shown again)

### Google Gemini
1. Go to https://aistudio.google.com/apikey
2. Sign in with a Google account
3. Click "Create API key"
4. Copy the generated key

### Anthropic
1. Go to https://console.anthropic.com/settings/keys
2. Sign in or create an account
3. Click "Create Key"
4. Copy the key

## Step 4: Create the config file

Create the directory and config file at `~/.config/skene-growth/config.toml`:

```toml
[llm]
provider = "<selected-provider>"
api_key = "<user-provided-api-key>"

[output]
output_dir = "./skene-context"
verbose = false
```

 - Replace `<user-provided-api-key>` with the actual key and `<selected-provider>` with the chosen provider, leave the other fields unchanged. 
 - For local providers (lmstudio, ollama), the api_key line can be omitted or left empty.

## Guidelines

- Be friendly and helpful throughout the process
- If the user already has a config file, ask if they want to update it or start fresh
- Confirm the provider choice before creating the config
- Never log or display the full API key after the user provides it
- Even if the user has API keys stored in environment variables, it is required to add the api_key field to the config file
- Offer to test the package by running `uvx skene-growth analyze .`
