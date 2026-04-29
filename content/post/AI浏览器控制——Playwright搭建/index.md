---
title: "AI 浏览器控制 —— Playwright 搭建笔记"
description: "让 AI 可以操控浏览器：截图、填表、抓取"
date: 2026-04-29
draft: false
math: false
tags: [Playwright, 浏览器自动化, AI, 工具]
categories: [技术笔记]
---

## 为什么需要这个

AI 只能读文本、跑命令，但很多信息在网页里——登录后才能看的内容、需要 JavaScript 渲染的页面、图表截图。

装上 Playwright 后，AI 可以通过脚本操控浏览器：打开网页、点击、填表单、截图、抓取内容。

## 安装

```bash
npm install -g playwright
npx playwright install chromium
```

安装后会在 `AppData\Local\ms-playwright\` 下下载 Chromium 浏览器内核（约 180MB）。

## 测试是否能用

写一个测试脚本 `test.js`：

```javascript
const { chromium } = require("playwright");
(async () => {
  const browser = await chromium.launch({ headless: true });
  const page = await browser.newPage();
  await page.goto("https://yubailing666.github.io");
  const title = await page.title();
  console.log("Page title:", title);
  await page.screenshot({ path: "screenshot.png", fullPage: true });
  await browser.close();
})();
```

跑：`node test.js`

成功的话会输出页面标题并保存截图。

## 注意事项

- 国内网络下 `npx playwright install chromium` 下载可能慢（约 180MB 的 Chromium 包）
- `headless: true` 表示无头模式（不弹出浏览器窗口）
- 截图默认保存在当前目录

## 后续可能的应用

- 截图验证博客部署效果（不用等 GitHub Actions 跑完）
- 自动登录网站抓取校园网数据
- 监控网页变化
- 截图调试前端页面
