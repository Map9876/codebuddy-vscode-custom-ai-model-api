# codebuddy-vscode-custom-ai-model-api
vscode 插件版 codebuddy 使用自己的ai api 进行对话 的方法，与codebuddy.exe的方法一致，都是创建 ~/.codebuddy/models.json文件即可，官方文档 https://www.codebuddy.ai/docs/zh/ide/Features/models

## 方法:

直接告诉ai以下内容:

```
创建
~/.codebuddy/models.json
文件写入以下内容

{
  "models": [
    {
      "id": "mimo-v2.5-pro",
      "name": "Mimo-V2.5-Pro",
      "vendor": "user",
      "url": "https://token-plan-cn.xiaomimimo.com/v1",
      "apiKey": "tp-csf2hacsl7ri9fzd5f28solmf7ov",
      "configured": true,
      "tag": [
        "custom"
      ],
      "maxOutputTokens": 32000,
      "maxInputTokens": 128000,
      "maxAllowedSize": 128000,
      "supportsToolCall": true,
      "supportsImages": false,
      "supportsReasoning": true,
      "temperature": 1
    }
  ],
  "availableModels": [
    "mimo-v2.5-pro"
  ]
}
```

注意 目前仅支持 OpenAI 接口格式的 API



还有一个环境变量是 ACC_PRODUCT_CONFIG_V3 和 ACC_PRODUCT_CONFIG_V2 ，可在https://cnb.cool 文档看到，v3可设置models，v2设置models会无作用

```

{
  "endpoint": "https://api.cnb.cool/kfc60/kfc60-kemono-downloader-and-gofile-downloadef/-/ai-ide",
  "networkEnvironment": "internal",
  "authentication": {
    "type": "custom-token",
    "attributes": {
      "token": "00367DDGMzsh5ZHbTYR9jzdHb0A"
    }
  },
  "models": [
    {
      "id": "mimo-v2.5-pro",
      "name": "Mimo-V2.5-Pro",
      "vendor": "user",
      "url": "https://token-plan-cn.xiaomimimo.com/v1",
      "apiKey": "tp-csf2hacsl7ri9fzd5f28sol",
      "configured": true,
      "tag": ["custom"],
      "maxOutputTokens": 32000,
      "maxInputTokens": 128000,
      "maxAllowedSize": 128000,
      "supportsToolCall": true,
      "supportsImages": false,
      "supportsReasoning": true,
      "temperature": 1
    }
  ],
  "availableModels": ["mimo-v2.5-pro"],
  "productFeatures": {
    "CustomModel": true,
    "CustomModelsJSON": true
  },
  "agents": [
    {"name": "craft", "models": ["mimo-v2.5-pro"]},
    {"name": "ask", "models": ["mimo-v2.5-pro"]},
    {"name": "chat", "models": ["mimo-v2.5-pro"]}
  ],
  "updates": false
}

```
