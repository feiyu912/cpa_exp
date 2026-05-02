# Claude Code + CLI Proxy API 使用指南

[English](README.md) | 中文

一个为 CLI 提供 OpenAI/Gemini/Claude/Codex 兼容 API 接口的代理服务器。

现已支持通过 OAuth 使用 OpenAI Codex 和 Claude Code。

> 注：以下所有路径都是我自己的本机路径，实际使用时请按你的电脑路径修改。

## 1. 下载 CLIProxyAPI

下载 CLIProxyAPI，并选择适合自己系统的版本。

<img width="1259" height="652" alt="image" src="https://github.com/user-attachments/assets/be62bd43-d3db-4150-9f02-ab5556dc185d" />

## 2. 准备配置文件

先复制示例配置文件，并去掉 `example`，得到 `config.yaml`。

```bash
cp config.example.yaml config.yaml
```

然后根据自己的情况修改配置文件。

## 3. 启动 CLIProxyAPI

我的启动命令如下：

```bash
./cli-proxy-api --config /Users/kaicheng/coding/CLIProxyAPI_6.9.45_darwin_arm64/config.yaml
```

启动成功后，可以访问管理页面：

```text
http://localhost:8317/management.html
```

## 4. OAuth 配置

进入管理页面后，配置 OAuth。

<img width="1069" height="415" alt="image" src="https://github.com/user-attachments/assets/41ed1525-6bb4-4ae1-abf0-8d389c7768ad" />

## 5. API Configuration 配置

进入 `api_configuration` 页面，添加或修改自己的 API 配置。

<img width="981" height="586" alt="image" src="https://github.com/user-attachments/assets/16963541-a170-4a62-8e96-0fad2c83a0e9" />

## 6. 选择模型

点击 `/model`，选择自己想要使用的模型。

## 7. Claude Code 使用示例

后续使用这里只给出 Claude Code 的案例。
Codex 类似，但需要修改对应的 `config.toml`。

修改文件：

```bash
/Users/kaicheng/.claude/settings.json
```

改成类似下面的格式：

```json
{
  "env": {
    "ANTHROPIC_BASE_URL": "http://127.0.0.1:8317",
    "ANTHROPIC_AUTH_TOKEN": "coding",
    "API_TIMEOUT_MS": "3000000",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1",
    "ANTHROPIC_MODEL": "claude-opus-4-7",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "gpt-5.5",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "claude-opus-4-7",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "MiniMax-M2.7-highspeed"
  },
  "effortLevel": "xhigh",
  "model": "opus"
}
```

说明：

- `ANTHROPIC_BASE_URL`：CLIProxyAPI 的本地代理地址。
- `ANTHROPIC_AUTH_TOKEN`：你在 proxy 中自己设置的 API Key，不要直接照抄我的。
- `ANTHROPIC_MODEL`：填写你实际可用的模型。
- `ANTHROPIC_DEFAULT_SONNET_MODEL`、`ANTHROPIC_DEFAULT_OPUS_MODEL`、`ANTHROPIC_DEFAULT_HAIKU_MODEL`：可以按自己在 OAuth 和 API 配置中添加的模型来填写。

## 8. 添加模型或账号

之前自己添加过什么，就在 OAuth 和 API 配置里选择对应内容。

<img width="933" height="561" alt="image" src="https://github.com/user-attachments/assets/c95f89a4-da55-4eb3-815e-163f2771db55" />

## 9. 检查 Claude 配置文件

检查文件：

```bash
/Users/kaicheng/.claude.json
```

如果没有完成初始化，可以新增：

```json
{
  "hasCompletedOnboarding": true
}
```
