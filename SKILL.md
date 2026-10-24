---
name: moyu-qiantong
display_name: 摸鱼签筒
display_name_en: Moyu Career Fortune Stick
description: 生成可离线打开的「打工人赛博求签」单文件网页，红漆签筒带摇签动画、60 支原创签、弹层签文卡可存图转发、集签图鉴、自由抽/今日签双模式。当用户说"做个求签网页/摸鱼签筒/职场求签/摇签玩具"时触发。
description_zh: 一个单文件、可离线打开的打工人求签网页，红漆签筒会摇会飞，60 支原创签，弹层签文卡可一键存图转发，带集签图鉴，数据不出本机。
description_en: A single-file, offline "career fortune stick" web toy with a shaking tube animation, 60 original signs, a popup ticket that exports to a shareable PNG, a collection compendium, and free/daily modes.
category: productivity
version: 1.1.0
author: 番茄排骨
license: MIT
allowed-tools:
  - Read
  - Write
  - Edit
  - Bash
  - Glob
  - Grep
  - present_files
---

# 摸鱼签筒

一个单文件、可离线打开的「打工人赛博求签」网页。打开就能摇签：红漆签筒会左右摇晃、飞出一签，随后**弹出**一张签文卡片，告诉你今天的运势、一首打油诗、一句大白话解签，还有一个「今日宜」的小动作。卡片可一键存成竖版海报转发，摇过的签会点亮左栏图鉴。它是图一乐的玩具，不是量表，不联网、不上传。

## 这个 Skill 做什么

- **核心产物**：一份单文件 HTML（`assets/quiz.html`），离线双击即可使用，零外部依赖。
- **结构要点**：红漆签筒（CSS 手绘 + 22 支竹签）→ 摇签动画（筒身摇晃 → 飞出一签）→ 模态弹层签文卡（不撑开布局）→ 60 支原创签，分 8 档运势（鸿运/顺遂/安稳/小满/佛系/水逆/想跑/玄学）→ 自由抽 / 今日签 双模式 → 集签图鉴（localStorage 进度）→ 本机历史（上限 30 笔，可清空）→ Canvas 生成 750×1420 竖版分享海报（PNG 本地下载）。
- **数据边界**：全部计算在浏览器端完成，历史与集签进度存 `localStorage`，无任何网络请求，数据不出本机。

## 何时使用

- 用户说「做个求签网页」「生成摸鱼签筒」「我要个职场求签/摇签玩具」「做个抽签小工具」。
- 用户想把这个网页发给同事、嵌进文章，或作为解压小玩具分发。

## 如何使用（给智能体的工作流）

1. 把 `assets/quiz.html` 复制到用户当前工作区（默认文件名 `quiz.html` 或 `index.html`）。
2. 用 `present_files` 打开预览，让用户直接使用。
3. 若用户要改签文 / 改配色 / 加减签数 / 换海报版式，在本文件同目录的代码基础上调整（签数改 `SIGNS` 数组即可，页面各处数字为动态 `TOTAL`）。

## 说明与免责

- 这是按"求签解签"形式做的**自评 / 自测玩具**，不是标准化量表，未做信效度检验，不做临床诊断或职业建议。
- 全部计算在本地浏览器完成，不联网、不上传。
