# DeepSeek TUI (Ollama Cloud Edition)

> **Fork of [Hmbown/DeepSeek-TUI](https://github.com/Hmbown/DeepSeek-TUI)** — pre-configured for **Ollama Cloud** with `deepseek-v4-pro:cloud`.

Terminal coding agent for DeepSeek V4, running through Ollama Cloud. No GPU needed — inference is offloaded to Ollama. Streams reasoning blocks, edits local workspaces, and includes auto mode that chooses the best model + thinking level per turn.

🙏 Huge thanks to [@Hmbown](https://github.com/Hmbown) and all [contributors](https://github.com/Hmbown/DeepSeek-TUI/graphs/contributors) for building this fantastic tool.

## What's Different

| | Upstream | This Fork |
|---|---|---|
| Provider | DeepSeek API | Ollama Cloud |
| Model | `deepseek-v4-pro` | `deepseek-v4-pro:cloud` |
| API key | DeepSeek | Ollama account |
| GPU needed | No | No |

## Setup

```bash
# 1. Install
npm install -g deepseek-tui

# 2. Pull the cloud model
ollama pull deepseek-v4-pro:cloud

# 3. Sign in to Ollama
ollama signin

# 4. Create config
mkdir -p ~/.deepseek
cat > ~/.deepseek/config.toml << 'TOML'
provider = "ollama"
default_text_model = "deepseek-v4-pro:cloud"

[providers.ollama]
base_url = "http://localhost:11434/v1"
TOML

# 5. Launch
deepseek
```

For full documentation, features, and advanced configuration, head to the [upstream repo](https://github.com/Hmbown/DeepSeek-TUI).
