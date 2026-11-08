# XCoze-PairCraft

**简体中文** | [English](README.en.md)

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**和 AI 一起梳理产品需求、做评审原型、按客户反馈改版。**

PairCraft 是一个面向产品经理和设计协作者的 Agent Skill。你可以带着一句想法、一份旧需求或一条客户反馈开始。比如客户说「报名成功后这里不明显」，PairCraft 会让 AI 先定位具体页面，弄清应该怎么改、哪些地方要保留，再检查改完的流程。

[安装](#安装) · [使用](#使用) · [设计思路](#设计思路) · [兼容性](#兼容性) · [参与贡献](#参与贡献)

## 安装

先选工作语言，再选 Agent。两个版本的工作流程相同，分别包含对应语言的 Skill 指令、模板和示例。通常按项目安装其中一个版本即可。

| 工作语言 | Skill 名和目录 | 安装指南 |
| --- | --- | --- |
| 简体中文 | [`xcoze-paircraft`](xcoze-paircraft/SKILL.md) | [中文](xcoze-paircraft/INSTALL.zh-CN.md) |
| English | [`xcoze-paircraft-en`](xcoze-paircraft-en/SKILL.md) | [English](xcoze-paircraft-en/INSTALL.en.md) |

### 交给 Agent 安装

把这句话发给你平时使用的 Agent：

```text
请安装 https://github.com/wjason/xcoze-paircraft 里的中文版 xcoze-paircraft。
```

要装英文版，把提示里的「中文版 xcoze-paircraft」换成「英文版 xcoze-paircraft-en」。让 Agent 安装对应的完整目录，并告诉你怎么调用。如果列表里没有出现，按宿主提示重新加载或新开会话。

### 用 Skills CLI 安装

有满足 [Skills CLI 要求](https://github.com/vercel-labs/skills#install-a-skill)的 Node.js 时，在要使用 Skill 的项目里运行：

```bash
# 简体中文
npx skills add wjason/xcoze-paircraft --skill xcoze-paircraft
# English
npx skills add wjason/xcoze-paircraft --skill xcoze-paircraft-en
```

只运行你需要的语言命令。按提示选择 Agent，也可加 `--agent codex` 或 `--agent claude-code`。默认装到当前项目，需要跨项目使用时加 `-g`。原生安装器、手动复制和排查方法见[详细安装指南](xcoze-paircraft/INSTALL.zh-CN.md)。

## 使用

安装后，可以直接把第一段提示词发给 Agent。下面用一个虚构的活动报名工具演示三个场景。你也可以从已有需求、线框或客户反馈直接开始。

### 1. 从想法梳理首版

```text
请用 xcoze-paircraft 帮我梳理一个小团队活动报名工具。
组织者现在用群消息收集报名，常漏记，参与者也不知道自己是否报上。
这轮只讨论。请给我目标用户、最小主流程、首版范围和必须由我决定的问题。
```

可以得到一页可确认的需求摘要。例如主路径是「填写信息 → 提交 → 确认结果」，登录和名额规则等由产品负责人决定。如果已经有访谈或旧方案，附上它们并指出哪份是目前有效版本。

### 2. 做一个能回答评审问题的原型

```text
请用 xcoze-paircraft。根据已确认的需求做一条可点击的报名路径。
本次评审只验证：报名成功后，参与者能否自己找到结果。
使用演示数据，给我可打开的预览、一个评审任务和后续改文案的入口。
```

评审任务可以是「完成报名并找到自己的报名详情」。交接时说明从哪里开始、哪些数据是演示数据、以后从哪里改。客户按任务操作，产品经理据此判断流程是否清楚。

### 3. 把反馈落实成一次可控改版

```text
请用 xcoze-paircraft。客户反馈报名完成后找不到详情入口。
修改报名确认页的主按钮，文案改为「查看我的报名」，点击进入详情。
保留表单字段和提交规则。请更新可编辑源稿和预览，
检查提交后能进入详情并返回，最后列出已验证和待验证的项。
```

建议附上页面名、截图标注、选中图层或组件 ID。若反馈指向的是业务规则，就给出触发条件和预期结果。例如「同一参与者再次提交时，进入已有详情」。

## 设计思路

AI 生成一份 HTML Demo 很快。客户评审过后，产品经理还要能找到地方修改，团队也要能确认改的是当初讨论的那个问题。PairCraft 把这件事拆成四个协作动作。

| 容易卡在哪 | PairCraft 怎么做 | 你可以检查什么 |
| --- | --- | --- |
| 聊了几轮，建议和已确认需求混在一起 | 先读现有材料，分清决定、假设、演示内容和待定项 | 这轮沿用什么，哪些选择还需要你拍板 |
| 一句需求做出一整套页面 | 先定评审要回答的问题，再选摘要、流程图、线框或可点击原型 | 这份成果能否回答评审问题，是否只做了必要的范围 |
| 预览很好看，后来却不知道从哪改 | 交接可编辑源稿，给常改的页面、图层或组件清楚的名字 | 文案、布局、业务规则分别在哪改，怎么更新预览 |
| 「这里再优化一下」越改越偏 | 把反馈写成目标位置、目标表现、保留项和检查方法 | 实际改了哪些地方，相关路径和保留项是否正常 |

产品负责人决定用户、范围和关键业务取舍。AI 可以整理材料、提出选项、制作和验证。一次小改动，说清目标、保留项和怎么检查就能开始。工作跨多轮或需要交接时，再把重要决定留在团队现有的文档、设计稿或任务记录里。

### 如果交付的是 HTML，怎么留出编辑入口？

给评审者一份可以直接打开的预览，同时给维护者一个找得到的修改入口。可以沿用团队已有的设计画布，也可以把经常修改的文案或演示数据放在配置中，把交互留在对应组件里。例如「表单提示语改配置，页面布局改组件，提交规则看流程说明」。附上改完怎样更新预览，下一次就能接着这份成果迭代。

## 兼容性

PairCraft 使用 [Agent Skills 开放格式](https://agentskills.io/specification)。Skill 本身无需额外 API Key 或脚本。制作文件、打开预览和验证交互所需的能力由宿主提供。

| 宿主 | 怎么用 |
| --- | --- |
| Codex | 安装后用 `$xcoze-paircraft`（中文）或 `$xcoze-paircraft-en`（英文）。[步骤](xcoze-paircraft/INSTALL.zh-CN.md#codex) |
| DSH（DeepSeek Harness） | 按配置将所选语言目录放到共享目录或 DSH 专用目录，在会话中按 Skill 名加载。[步骤](xcoze-paircraft/INSTALL.zh-CN.md#dsh) |
| Claude Code | 安装后用 `/xcoze-paircraft`（中文）或 `/xcoze-paircraft-en`（英文）。[步骤](xcoze-paircraft/INSTALL.zh-CN.md#claude-code) |
| XCoze 与其他对话工具 | 支持附件或自定义指令时，可提供 `SKILL.md` 和相关参考文件在会话中使用。XCoze 原生导入待验证。[步骤](xcoze-paircraft/INSTALL.zh-CN.md#xcoze) |

换 Agent 或开新会话时，带上当前有效的需求、设计源和上轮决定。Skill 提供协作方法，项目材料让新会话能接着做。

## 文档与示例

- [安装与排查](xcoze-paircraft/INSTALL.zh-CN.md)
- [Skill 入口](xcoze-paircraft/SKILL.md)和[工作模式](xcoze-paircraft/references/modes.md)
- [本轮简报、评审任务和变更记录模板](xcoze-paircraft/references/artifact-templates.md)
- [完整示例](xcoze-paircraft/references/worked-example.md)和[质量检查](xcoze-paircraft/references/quality-gates.md)

## 参与贡献

欢迎用 Issue 或 PR 分享脱敏案例。附上原始请求、AI 实际做了什么，以及你希望它在哪一步作出不同判断，方便我们改进这套协作方法。

## 许可证

[MIT License](LICENSE)
