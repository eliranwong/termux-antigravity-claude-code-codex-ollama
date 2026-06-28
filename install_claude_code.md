# Install Claude Code

## Login Unbuntu Environment

For details, read [install_ubuntu.md](install_ubuntu.md).

```
ubuntu
```

## Install Claude Code

```
curl -fsSL https://claude.ai/install.sh | bash
```

## Bypass Permissions [Optional]

**Warning**: The following method overrides ALL permissions and allows Claude to perform any action it deems necessary. Use this ONLY if you understand the risks involved.

If you want to bypass the repetitive permission prompts during the deep research, you can add the following to your `~/.claude/settings.json` file:

```
  "permissions": {
    "defaultMode": "bypassPermissions"
  },
  "skipDangerousModePermissionPrompt": true,
  "skipWorkflowUsageWarning": true
```

**Disclaimer**: Use this setting with caution. It overrides all permissions and allows Claude to perform any action it deems necessary. Use at your own risk.  I take no responsibility for any damages caused by using this setting.

## Use Claude Code with Azure Models [Optional]

Assuming you have models deployed via Azure, run or add to your shell profile (`~/.zshrc`, `~/.bashrc`, etc.) the following commands (replace the placeholders with your actual values):

```bash
export ANTHROPIC_AUTH_TOKEN=<your_api_key>
export ANTHROPIC_BASE_URL=https://<your_project_name>.services.ai.azure.com/anthropic/
export ANTHROPIC_FOUNDRY_API_KEY=<your_api_key>
export ANTHROPIC_FOUNDRY_BASE_URL=https://<your_project_name>.services.ai.azure.com/anthropic/
export ANTHROPIC_MODEL=opusplan
export ANTHROPIC_DEFAULT_OPUS_MODEL=claude-opus-4-5
export ANTHROPIC_DEFAULT_SONNET_MODEL=claude-sonnet-4-5
```

# Use Claude Code with Ollama Models [Optional]

Assuming you have ollama installed and running, run or add to your shell profile (`~/.zshrc`, `~/.bashrc`, etc.) the following commands:

```bash
export ANTHROPIC_AUTH_TOKEN=ollama
export ANTHROPIC_API_KEY=""
export ANTHROPIC_BASE_URL=http://localhost:11434
export ANTHROPIC_MODEL=glm-5.2:cloud
```
