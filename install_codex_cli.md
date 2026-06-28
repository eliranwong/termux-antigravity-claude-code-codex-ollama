# Install Codex CLI

## Login Unbuntu Environment

For details, read [install_ubuntu.md](install_ubuntu.md).

```
ubuntu
```

## Install Node.js

Follow instructions at:

https://nodejs.org/en/download

## Install Codex CLI

```
curl -fsSL https://chatgpt.com/codex/install.sh | sh
```

## Use Azure / Ollama Models in Codex CLI [Optional]

For example, edit the ~/.codex/config.toml file with:

```
model = "glm-5.1:cloud"
model_provider = "ollama-launch"
#model = "gpt-5.3-codex"
#model_provider = "azure"
model_reasoning_effort = "medium"

# Uncomment to use the five lines below at your own risk
#sandbox_mode = "danger-full-access"
#approval_policy = "never"
#web_search = "live"
#[sandbox_workspace_write]
#network_access = true

[profiles.ollama-launch]
openai_base_url = "http://127.0.0.1:11434/v1/"
model_provider = "ollama-launch"
forced_login_method = "api"

[model_providers.ollama-launch]
name = "Ollama"
base_url = "http://127.0.0.1:11434/v1/"
wire_api = "responses"

[model_providers.azure]
name = "Azure OpenAI"
base_url = "https://<resource-name>.openai.azure.com/openai/v1"
env_key = "AZURE_OPENAI_API_KEY"
wire_api = "responses"
```

### Export Environment Variables for Codex CLI

In case you want to use Azure / Ollama models in Codex CLI, you need to export the environment variables for Codex CLI:

```
export AZURE_OPENAI_API_KEY="your-key"
export OLLAMA_API_KEY="your-key"
```