# agy-plugin-development

Google Antigravity CLI (`agy`) plugin providing workflow instructions and guidance
for designing, scaffolding, securing, and documenting Antigravity plugins.

## Features

- **`plugin-development` skill**: Comprehensive multi-phase workflow guide for plugin creation.

## Installation & Local Setup

To install this plugin into your local Antigravity environment, create a symlink in the user
plugins directory:

```bash
mkdir -p ~/.gemini/config/plugins
ln -s /Users/chris/Development/agy-plugin-development \
  ~/.gemini/config/plugins/agy-plugin-development
```

## Repository Structure & Conventions

- `plugin.json` / `plugin.yaml`: Plugin manifest definitions.
- `skills/plugin-development/SKILL.md`: Core skill instructions.
- Australian English spelling register across documentation and manifests.
- Lightweight implementation adhering strictly to YAGNI principles.
