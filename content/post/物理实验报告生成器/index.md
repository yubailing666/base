---
title: "物理实验报告生成器 —— SUSTech 物理实验 Skill"
description: "南方科技大学物理实验报告 AI 辅助生成工具"
date: 2026-04-29
draft: false
math: true
tags: [物理, 实验报告, OpenClaw, Skill]
categories: [工具]
---

## 这是什么

一个 OpenClaw Skill，专门帮你写 **南方科技大学基础物理实验报告**。

大一必修的基础物理实验，每次实验要交一份报告：实验名称、目的、原理、仪器、步骤、数据、数据处理、误差分析、讨论、思考题——十来个大块。这个 skill 按学校的标准格式生成初版，省去排版和格式上的重复劳动。

## 仓库地址

**GitHub：** [github.com/yubailing666/physics-lab-report-skill](https://github.com/yubailing666/physics-lab-report-skill)

## 使用方式

### 前提

- 编辑器用 VS Code（装好 Markdown 预览插件）
- 文件格式用 `.md`（Markdown）
- 数据处理可以用 Jupyter Notebook，做完再贴进来

### 第一步：改学号

在 `references/customization.md` 里把学号改成自己的。

### 第二步：让 AI 生成初版

对 AI 说类似这样的话：

> "帮我写物理实验报告，实验名称是 xxx，数据如下……"

AI 会自动套用 skill，按标准格式生成初版。

### 第三步：自己改

AI 给的只是初版。在 VS Code 里打开 `.md` 文件，调格式、插图片、改数据，最后导出提交。

## 文件结构

```
基础物理实验报告/
├── README.md                         ← 使用说明书
├── SKILL.md                          ← AI 用的指令文件
├── references/
│   ├── customization.md              ← 这里改你的学号
│   ├── error-analysis-template.md    ← 误差分析写法参考
│   └── full-template.md              ← 实验报告完整空白模板
└── scripts/                          ← 预处理和数据分析脚本
```

## 几点提醒

- 实验原理部分建议对着教材/课件改，AI 推导公式可能出错
- 数据处理和误差分析要核对自己的原始数据
- 思考题可以让 AI 给思路，最好自己写
- 这只是一个排版和格式的辅助工具，不保证实验内容本身的正确性
