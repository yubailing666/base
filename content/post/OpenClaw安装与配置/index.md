---
title: "三分钟装好 OpenClaw"
description: "一行命令安装，配 API key 就能用。还支持微信插件，手机也能聊。"
date: 2026-05-12
draft: false
tags: [openclaw, 安装]
categories: [工具]
---

打开终端，一行命令：

```
npm install -g openclaw
```

装完跑 openclaw 看有没有成功。

然后配一个模型。去 deepseek.com 拿 API key，终端跑：

```
openclaw config set model-provider deepseek
openclaw config set model deepseek/deepseek-v4-flash
openclaw config set api-key 你的key
```

也支持 Claude、GPT。配完就能聊了。

想在微信上用同一个 AI，装 openclaw-weixin 插件，GitHub 搜一下按 README 配。

确保先装了 Node.js。
