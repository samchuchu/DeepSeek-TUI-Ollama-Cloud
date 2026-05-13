# DeepSeek TUI (Ollama Cloud Edition)

> **Fork of [Hmbown/DeepSeek-TUI](https://github.com/Hmbown/DeepSeek-TUI)** — pre-configured for **Ollama Cloud** with `deepseek-v4-pro:cloud`.

Terminal coding agent for DeepSeek V4. Runs from the `deepseek` command via your local Ollama instance — no GPU needed, inference is offloaded to Ollama Cloud. Streams reasoning blocks, edits local workspaces with approval gates, and includes an auto mode that chooses both model and thinking level per turn.

## What's Different

This fork is wired to Ollama Cloud instead of DeepSeek's API:

- **Provider:** `ollama` (not `deepseek`)
- **Model:** `deepseek-v4-pro:cloud` via Ollama Cloud
- **No DeepSeek API key needed** — just an [Ollama account](https://ollama.com)

## Setup

```bash
# 1. Install
npm install -g deepseek-tui

# 2. Pull the cloud model
ollama pull deepseek-v4-pro:cloud

# 3. Sign in to Ollama (if not already)
ollama signin

# 4. Configure
mkdir -p ~/.deepseek
cat > ~/.deepseek/config.toml << 'TOML'
provider = "ollama"
default_text_model = "deepseek-v4-pro:cloud"

[providers.ollama]
base_url = "http://localhost:11434/v1"
TOML

# 5. Run
deepseek
```

For full documentation, see the [upstream repo](https://github.com/Hmbown/DeepSeek-TUI).
