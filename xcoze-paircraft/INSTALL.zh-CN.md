# XCoze-PairCraft 安装指南

要安装的是仓库里的 `xcoze-paircraft/` 子目录。保留 `SKILL.md` 和整个 `references/`，这样宿主可以按需读取模板、示例与检查项。

## 获取 Skill

从 [GitHub 仓库](https://github.com/wjason/xcoze-paircraft) 下载 ZIP 并解压，或运行：

```bash
git clone https://github.com/wjason/xcoze-paircraft.git
cd xcoze-paircraft
```

以下复制命令从克隆或解压后的**仓库根目录**运行。macOS / Linux 可直接使用这些命令，Windows 可用文件管理器复制同一份文件夹。若目标已经有同名版本，先核对原来的来源和改动，再决定是否更新。

## Codex

**用 Agent 安装。** 在 Codex 会话里输入：

```text
使用 $skill-installer 从 GitHub 仓库 wjason/xcoze-paircraft 的 main 分支
安装 xcoze-paircraft 子目录。请报告安装位置和识别结果。
```

**手动安装。** 个人使用：

```bash
mkdir -p "$HOME/.agents/skills"
cp -R xcoze-paircraft "$HOME/.agents/skills/"
```

如果要随项目共享，放在目标项目的 `.agents/skills/xcoze-paircraft/`。装好后输入 `$xcoze-paircraft` 或在 Skill 列表里选择它。如果没有出现，重启 Codex 后再试。[Codex 官方文档](https://learn.chatgpt.com/docs/build-skills)

## DSH

DSH 指 DeepSeek Harness。启用默认文件系统 Skill provider 时，可以使用个人共享目录 `~/.agents/skills/`，也可以只为 DSH 安装到 `~/.dsh/skills/`。如配置了 `DSH_AGENTS_HOME` 或 `DSH_HOME`，使用对应配置根目录下的 `skills/`。目标项目也可使用根目录的 `.dsh/skills/` 或 `.agents/skills/`。

例如，安装到个人 DSH 目录：

```bash
mkdir -p "${DSH_HOME:-$HOME/.dsh}/skills"
cp -R xcoze-paircraft "${DSH_HOME:-$HOME/.dsh}/skills/"
```

启动 DSH 会话后输入「请加载 `xcoze-paircraft` Skill，先帮我梳理需求，这轮只讨论」。共享目录可被当前环境中的 Codex 和 DSH 共用，前提是两者都扫描这个位置。路径以你所用版本和配置为准。[DSH 文件系统 Skill 文档](https://github.com/deepseek-ai/deepseek-harness/blob/master/packages/skill/skill-filesystem/README.md)

## Claude Code

个人使用：

```bash
mkdir -p "$HOME/.claude/skills"
cp -R xcoze-paircraft "$HOME/.claude/skills/"
```

项目共享可放到目标项目的 `.claude/skills/xcoze-paircraft/`。在 Claude Code 中输入 `/xcoze-paircraft` 并附上任务。[Claude Code 官方文档](https://code.claude.com/docs/en/skills)

## XCoze

- 如果所用版本有自定义 Skill 导入界面，可按界面要求选取完整的 `xcoze-paircraft/`，然后检查是否出现在技能列表里。本仓库尚未验证 XCoze 原生导入。
- 如果会话支持附件或自定义指令，把 [SKILL.md](SKILL.md) 提供给当前会话，按需附上 [工作模式](references/modes.md)、[协作模板](references/artifact-templates.md) 或其他参考文件。若只能粘贴文本，可直接粘贴 `SKILL.md` 正文，再附上本轮需求。生效范围由会话或自定义指令的保存范围决定。
- 如果 XCoze 提供项目资料，而任务在另一个 Agent 里运行，可以把项目资料提供给该 Agent，同时在该 Agent 中安装 PairCraft。

## 其他 Agent

支持 [Agent Skills 格式](https://agentskills.io/specification) 的宿主可以按其官方说明复制目录或导入包。如果界面要求单技能 ZIP，把 `xcoze-paircraft/` 目录打包，按宿主要求核对解压后的层级。GitHub 自动生成的仓库 ZIP 含 README 和许可证，下载后需要从中取出 Skill 子目录。

如果只能加载文本或附件，可以这样发给 Agent：

```text
请先读取我提供的 SKILL.md，把它用作本轮的产品设计协作说明。
这轮只讨论活动报名工具。请给出目标用户、首版主流程和待决项。
需要用到模板时，告诉我你需要 references/ 中的哪个文件。
```

## 验证与排查

1. 检查实际入口是不是 `<宿主的 Skill 目录>/xcoze-paircraft/SKILL.md`，并确认 `references/` 与它同级。
2. 在目标宿主查找或显式调用 `xcoze-paircraft`，按宿主要求刷新、重启或新开会话。支持显示加载记录时，检查本次是否实际读取了 Skill。
3. 试跑上面的「这轮只讨论」示例，预期得到用户、主流程和待决项，并以讨论结果收尾。这个试跑也适合检验会话加载方式。
4. 在多个工作区或目录都装了同名版本时，检查宿主实际使用哪一份。旧版 `ai-product-design-sop` 如仍在匹配同类任务，可先验证新版，再将旧目录移出扫描范围备份。
5. 如果会话能读 Skill，却做不了原型或浏览器验证，检查宿主是否有文件写入、预览或运行所需的工具。Skill 提供协作方法，工具访问仍由宿主管理。

验证状态：已在临时项目中确认 Codex 能发现该目录中的 Skill。DSH 和 Claude Code 的安装步骤依据上面链接的官方文档，本项目尚未逐端试跑。XCoze 的会话用法取决于当前版本能提供的附件或自定义指令能力。
