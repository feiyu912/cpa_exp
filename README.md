# cpa_exp
注：以下所有的路径都是本人路径，需要按照实际情况改

下载cliproxyapi, 选择合适自己的

<img width="1259" height="652" alt="image" src="https://github.com/user-attachments/assets/be62bd43-d3db-4150-9f02-ab5556dc185d" />

先cp，去掉example,得到comfig.yaml
改自己的配置文件

启动： ./cli-proxy-api --config /Users/kaicheng/coding/CLIProxyAPI_6.9.45_darwin_arm64/config.yaml
management_url: http://localhost:8317/management.html

oath:
<img width="1069" height="415" alt="image" src="https://github.com/user-attachments/assets/41ed1525-6bb4-4ae1-abf0-8d389c7768ad" />

api_configuration

<img width="981" height="586" alt="image" src="https://github.com/user-attachments/assets/16963541-a170-4a62-8e96-0fad2c83a0e9" />

点击/model, 选择想要的



后续使用，只给出claudecode案例,codex类似要改config.toml

/Users/kaicheng/.claude/settings.json修改成这个格式
{
  "env": {
    "ANTHROPIC_BASE_URL": "http://127.0.0.1:8317",
    "ANTHROPIC_AUTH_TOKEN": "coding", //在proxy中自己设置的
    "API_TIMEOUT_MS": "3000000",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1",
    "ANTHROPIC_MODEL": "claude-opus-4-7",//有什么写什么
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "gpt-5.5",
    "ANTHROPIC_DEFAULT_OPUS_MODEL": "claude-opus-4-7",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "MiniMax-M2.7-highspeed"
  },
  "effortLevel": "xhigh",
  "model": "opus"
}

注：之前自己添加的有什么选什么，在oauth 和 api添加

<img width="933" height="561" alt="image" src="https://github.com/user-attachments/assets/c95f89a4-da55-4eb3-815e-163f2771db55" />



检查/Users/kaicheng/.claude.json


新增 `hasCompletedOnboarding` 参数
{
  "hasCompletedOnboarding": true
}
