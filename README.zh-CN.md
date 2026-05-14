# DeepSeek TUI（Ollama Cloud 版）

> **基于 [Hmbown/DeepSeek-TUI](https://github.com/Hmbown/DeepSeek-TUI) 的分支** — 预配置为 **Ollama Cloud**，使用 `deepseek-v4-pro:cloud`。

面向 DeepSeek V4 的终端编程助手，通过 Ollama Cloud 运行。无需 GPU——推理由 Ollama 云端处理。支持思考模式流式推理、工作区编辑、以及自动模式（每轮自动选择最佳模型 + 思考级别）。

🙏 感谢 [@Hmbown](https://github.com/Hmbown) 和所有[贡献者](https://github.com/Hmbown/DeepSeek-TUI/graphs/contributors)打造了这个出色的工具。

## 有什么不同

| | 上游 | 本分支 |
|---|---|---|
| 服务商 | DeepSeek API | Ollama Cloud |
| 模型 | `deepseek-v4-pro` | `deepseek-v4-pro:cloud` |
| API 密钥 | DeepSeek | Ollama 账号 |
| 需要 GPU | 否 | 否 |

## 安装配置

```bash
# 1. 安装
npm install -g deepseek-tui

# 2. 拉取云端模型
ollama pull deepseek-v4-pro:cloud

# 3. 登录 Ollama
ollama signin

# 4. 创建配置
mkdir -p ~/.deepseek
cat > ~/.deepseek/config.toml << 'TOML'
provider = "ollama"
default_text_model = "deepseek-v4-pro:cloud"

[providers.ollama]
base_url = "http://localhost:11434/v1"
TOML

# 5. 启动
deepseek
```

完整文档、高级功能及配置请参阅[上游仓库](https://github.com/Hmbown/DeepSeek-TUI)。
