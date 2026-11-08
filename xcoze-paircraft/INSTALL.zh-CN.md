# 安装与使用

## Codex

1. 下载或克隆仓库，找到其中的 `xcoze-paircraft/`。
2. 将该文件夹完整复制到个人 Skill 目录 `~/.agents/skills/`。确认入口为 `~/.agents/skills/xcoze-paircraft/SKILL.md`。
3. 在任务里调用 `$xcoze-paircraft`。列表里没有显示时，重启 Codex。

团队也可以把完整文件夹纳入项目的 `.agents/skills/xcoze-paircraft/`，并通过 Git 共享版本。

已安装旧版 `ai-product-design-sop` 的用户可以在验证新版后，将旧文件夹移出 Skill 扫描目录备份，减少重复匹配。

## 其他支持 Agent Skills 的工具

按工具的安装方式复制 `xcoze-paircraft/`。如果工具只支持自定义指令，可提供 `SKILL.md`，并按任务补充 `references/` 中相关的内容。调用语法和界面元数据取决于宿主。
