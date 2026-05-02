# CLI Proxy API

English | [中文](README.zh-CN.md)

A proxy server that provides OpenAI/Gemini/Claude/Codex compatible API interfaces for CLI.

It now also supports OpenAI Codex and Claude Code via OAuth.

> Note: All paths below are my local paths. Please replace them with your own paths.

## 1. Download CLIProxyAPI

Download CLIProxyAPI and choose the correct version for your operating system.

<img width="1259" height="652" alt="image" src="https://github.com/user-attachments/assets/be62bd43-d3db-4150-9f02-ab5556dc185d" />

## 2. Prepare the Configuration File

Copy the example configuration file and rename it by removing `example`.

```bash
cp config.example.yaml config.yaml
```

Then edit `config.yaml` according to your own environment.

## 3. Start CLIProxyAPI

```bash
./cli-proxy-api --config /Users/kaicheng/coding/CLIProxyAPI_6.9.45_darwin_arm64/config.yaml
```

After the service starts successfully, open:

```text
http://localhost:8317/management.html
```

## 4. OAuth Configuration

Configure OAuth in the management page.

<img width="1069" height="415" alt="image" src="https://github.com/user-attachments/assets/41ed1525-6bb4-4ae1-abf0-8d389c7768ad" />

## 5. API Configuration

Go to `api_configuration` and add or modify your API settings.

<img width="981" height="586" alt="image" src="https://github.com/user-attachments/assets/16963541-a170-4a62-8e96-0fad2c83a0e9" />

## 6. Select a Model

Click `/model` and choose the model you want to use.

## 7. Claude Code Example

This example is for Claude Code.
Codex is similar, but you need to modify its `config.toml`.

Edit:

```bash
/Users/kaicheng/.claude/settings.json
```

Example:

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

Notes:

- `ANTHROPIC_BASE_URL`: local CLIProxyAPI proxy address.
- `ANTHROPIC_AUTH_TOKEN`: the API key you configured in the proxy. Do not copy mine directly.
- `ANTHROPIC_MODEL`: use an available model name.
- The default Sonnet/Opus/Haiku models can be changed according to your OAuth and API configuration.

## 8. Add Models or Accounts

Select the models or accounts you added in OAuth and API configuration.

<img width="933" height="561" alt="image" src="https://github.com/user-attachments/assets/c95f89a4-da55-4eb3-815e-163f2771db55" />

## 9. Check Claude Configuration

Check:

```bash
/Users/kaicheng/.claude.json
```

If needed, add:

```json
{
  "hasCompletedOnboarding": true
}
```
