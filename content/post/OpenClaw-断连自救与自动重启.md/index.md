---
title: "OpenClaw 断连自救与自动重启"
description: "AI 助手失联了怎么办？从清 session 到写自动重启脚本的实战记录"
date: 2026-05-05
draft: false
math: false
tags: [OpenClaw, 运维, 自恢复, Windows]
categories: [技术笔记]
---

## 发生了什么

某天越雨突然不回消息了。重启 gateway 也没用，进程卡死在启动阶段。

排查发现：**sessions 目录里的微信会话文件损坏了**。OpenClaw 在启动时尝试加载这些文件，遇到坏数据直接堵住，整个 gateway 起不来。

## 快速恢复

如果你也遇到类似情况，最直接的恢复方式：

```powershell
# 1. 清空会话文件（聊天记录会丢失，但长时记忆还在）
rmdir /s /q C:\Users\Administrator\.openclaw\agents\main\sessions\
mkdir C:\Users\Administrator\.openclaw\agents\main\sessions\

# 2. 清 temp
del /q %TEMP%\openclaw\*.*

# 3. 重启
openclaw gateway
```

**注意：** `MEMORY.md` 和 `memory/` 目录不会受影响，长时记忆完好。丢失的只是当次的对话上下文。

## 根治方案：自动重启脚本

手动恢复太慢了。写一个批处理，崩了自动重开：

```batch
@echo off
chcp 65001 >nul
title OpenClaw Gateway - Auto Restart

:loop
echo [%date% %time%] Starting OpenClaw Gateway...

:: 自动清理 temp
if exist "%TEMP%\openclaw\" (
    del /q "%TEMP%\openclaw\*.*" 2>nul
)

openclaw gateway

echo Gateway exited (code %ERRORLEVEL%). Restarting in 3s...
timeout /t 3 /nobreak >nul
goto loop
```

## 从中学到什么

### 1. 会话文件是脆弱的
OpenClaw 把每个微信用户的对话存为 session 文件。如果这些文件损坏（断电、非正常退出都可能导致），gateway 就起不来。

### 2. 自动恢复 > 手动抢救
写一个循环重启的 wrapper 是最低成本的自救方案。之后可以考虑用 `nssm` 把它包装成 Windows 服务。

### 3. 配置项的安全警告
启动日志里有 `allowInsecureAuth=true` 的警告。这个配置方便开发调试，但生产环境应该关掉。

### 4. 升级修复
从 `2026.4.24` 升级到 `2026.5.3-1` 后稳定了许多。版本更新往往包含底层的稳定性修复，值得定期检查：

```bash
npm view openclaw version    # 查看最新版
npm install -g openclaw@latest  # 升级
```

## 附：HEARTBEAT 健康检查

在日常 heartbeat 里挂一个检查：

```
Gateway process still running?
Session dir not bloated (>50MB → flag)
New OpenClaw versions available?
```

越雨会定期检查这几个指标，有问题就汇报，不需要你主动盯着。
