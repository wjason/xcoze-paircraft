# Install XCoze-PairCraft in English

The English skill is in the `xcoze-paircraft-en/` subdirectory of the [repository](https://github.com/wjason/xcoze-paircraft). Keep the entire directory, including `SKILL.md` and `references/`. For Simplified Chinese, choose `xcoze-paircraft`. [Chinese installation guide](https://github.com/wjason/xcoze-paircraft/blob/main/xcoze-paircraft/INSTALL.zh-CN.md)

## Skills CLI

From the project where you want to use the skill, run the following with a [supported Node.js version](https://github.com/vercel-labs/skills#install-a-skill):

```bash
npx skills add wjason/xcoze-paircraft --skill xcoze-paircraft-en
```

Choose your agent when prompted. Use `--agent codex` or `--agent claude-code` to select one directly. Add `-g` for user-wide installation.

You can also ask your agent: “Install the English `xcoze-paircraft-en` subdirectory from https://github.com/wjason/xcoze-paircraft and tell me how to invoke it here.”

For manual installation, clone or download the repository, then copy the entire `xcoze-paircraft-en/` subdirectory to one of the locations below. Check for an existing copy before replacing it.

## Codex

Copy the skill to `~/.agents/skills/` for personal use or to `.agents/skills/` in the target project. Alternatively, ask Codex to use `$skill-installer` on the `xcoze-paircraft-en` subdirectory of `wjason/xcoze-paircraft`. Invoke `$xcoze-paircraft-en` or select it from the skill list. Restart Codex if it does not appear. [Codex documentation](https://learn.chatgpt.com/docs/build-skills)

## DSH

With the default filesystem skill provider, copy the skill to `~/.dsh/skills/` or the shared `~/.agents/skills/`. For project scope, use `.dsh/skills/` or `.agents/skills/` at the project root. If `DSH_HOME` or `DSH_AGENTS_HOME` is configured, use the appropriate `skills/` subdirectory. Ask the agent to load `xcoze-paircraft-en` by name. [DSH filesystem skill documentation](https://github.com/deepseek-ai/deepseek-harness/blob/master/packages/skill/skill-filesystem/README.md)

## Claude Code

Copy the skill to `~/.claude/skills/` for personal use or `.claude/skills/` in the target project. Invoke `/xcoze-paircraft-en` with your task. [Claude Code documentation](https://code.claude.com/docs/en/skills)

## XCoze

If your version has a custom skill importer, try importing the complete English directory and check the skill list. Native import has yet to be verified. If the host supports attachments or custom instructions, provide the English [SKILL.md](SKILL.md) and relevant [templates](references/artifact-templates.md) or [examples](references/worked-example.md) as session context. Apply the same approach to other chat tools that can read these materials.

## Verify

Check that `<skill root>/xcoze-paircraft-en/SKILL.md` and its adjacent `references/` are available to the agent. Reload the skill list or start a new session if needed. Then try:

```text
Use xcoze-paircraft-en to help me plan a small event signup tool.
Keep this round to discussion. Give me target users, one core flow,
and the decisions I need to make.
```

If the host shows skill activity, check that it loaded the English edition. You should get a brief in English and the decisions still open for discussion. Building files or testing previews depends on the tools available in that host.
