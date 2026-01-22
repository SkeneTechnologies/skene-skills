---
name: setup-skene-growth
description: Setup skene-growth dependencies, guide the user with the configuration
---

To setup skene-growth:

1. **Check if uvx is already installed**: Check if uvx is already installed, try e.g. `which uvx` or `uvx --version`
2. **Install uvx if needed**: If needed, run installer script `curl -LsSf https://astral.sh/uv/install.sh | sh`
3. **Ask user for API key**: Ask the API key to call google Generative Language API, will be needed for the configuration file
4. **Create skene-growth config file**: Create a file `~/.config/skene-growth/config.toml` with content `api_key = <API key>` (replace the placeholder with the key from step 3)

Be polite and engaging, help the user if he/she has no idea about how to get the API key
