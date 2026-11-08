# XCoze-PairCraft

[简体中文](README.md) | **English**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**An Agent Skill for shaping product requirements, building reviewable prototypes, and making precise revisions with AI.**

Start with a rough idea, an existing spec, or a piece of customer feedback. PairCraft helps your agent find what needs a decision, produce something you can review, and leave a clear place to make the next change.

[Install](#install) · [Use it](#use-it) · [Design principles](#design-principles) · [Compatibility](#compatibility)

## Install

Choose the language you work in, then select your agent. Both editions follow the same workflow and ship with localized instructions, templates, and examples. Install the edition you want for the current project.

| Language | Skill name and folder | Installation guide |
| --- | --- | --- |
| English | [`xcoze-paircraft-en`](xcoze-paircraft-en/SKILL.md) | [English](xcoze-paircraft-en/INSTALL.en.md) |
| 简体中文 | [`xcoze-paircraft`](xcoze-paircraft/SKILL.md) | [中文](xcoze-paircraft/INSTALL.zh-CN.md) |

Ask your agent:

```text
Install the English xcoze-paircraft-en skill from https://github.com/wjason/xcoze-paircraft
```

Install the complete `xcoze-paircraft-en/` subdirectory. Ask how to invoke it, then reload or start a new session if it does not appear.

With a [supported Node.js version](https://github.com/vercel-labs/skills#install-a-skill), run this from your project:

```bash
npx skills add wjason/xcoze-paircraft --skill xcoze-paircraft-en
```

Select your agent when prompted, or add `--agent codex` or `--agent claude-code`. The default scope is the current project. Add `-g` for all projects. See the [installation guide](xcoze-paircraft-en/INSTALL.en.md) for native installers and manual setup.

## Use it

These examples follow a fictional event signup tool. Start at the step that matches the materials you already have.

### Shape the first version

```text
Use xcoze-paircraft-en to help me plan an event signup tool for a small team.
Signups get lost in group chat and attendees are unsure whether they registered.
Keep this round to discussion. Give me the target users, one initial flow,
and the decisions I need to make.
```

Expect a short brief you can discuss. Decisions about sign-in and capacity stay with the product owner.

### Build a prototype for review

```text
Use xcoze-paircraft-en to prototype the agreed signup flow.
The review should answer one question: can attendees find their result
after submitting? Give me a preview, a review task, and a place to edit the copy.
```

A review task might be “Register, then find your signup details.” A wireframe can be enough if the question is about flow order. A clickable prototype lets reviewers try the task themselves.

### Revise a specific part after feedback

```text
Use xcoze-paircraft-en. Reviewers could not find their signup details.
On the confirmation page, change the primary button to "View my signup"
and open the details page on click. Keep the form fields and submission rules.
Update the editable source and preview, then check the forward and return paths.
```

A marked-up screenshot, a selected design layer, or a component name helps the agent identify the target.

## Design principles

| Problem | How PairCraft handles it |
| --- | --- |
| Decisions and AI suggestions are mixed together | Read existing materials and distinguish decisions, assumptions, demo content, and open questions. |
| A rough idea turns into too many screens | Pick the review question first, then make the smallest artifact that answers it. |
| A shareable demo is hard to revise | Hand over an editable design or source, identify where common edits belong, and explain how to refresh the preview. |
| Feedback is too vague to check | Identify the target, expected behavior, what to keep, and how to verify the change. |

People make decisions about users, scope, and core business rules. The agent can organize context, propose options, make artifacts, and verify changes. Keep a record when work spans people or rounds. A small, clear change can go straight to execution and a focused check.

## Compatibility

PairCraft follows the [Agent Skills specification](https://agentskills.io/specification). The skill requires no extra API key or scripts. File creation, preview, and interaction checks depend on the host.

- **Codex.** Invoke `$xcoze-paircraft-en`. [Setup](xcoze-paircraft-en/INSTALL.en.md#codex)
- **DeepSeek Harness and Claude Code.** Ask DSH to load `xcoze-paircraft-en`, or use `/xcoze-paircraft-en` in Claude Code. [DSH setup](xcoze-paircraft-en/INSTALL.en.md#dsh) · [Claude Code setup](xcoze-paircraft-en/INSTALL.en.md#claude-code)
- **XCoze and other chat tools.** If the host supports attachments or custom instructions, provide the English `SKILL.md` and relevant references as session context. Native XCoze import has yet to be verified. [Setup](xcoze-paircraft-en/INSTALL.en.md#xcoze)

See the [English skill instructions](xcoze-paircraft-en/SKILL.md), [templates](xcoze-paircraft-en/references/artifact-templates.md), and [worked example](xcoze-paircraft-en/references/worked-example.md).

## Contribute

Issues and pull requests are welcome. An anonymized request, what the agent did, and what you expected it to do differently make for a good report.

## License

[MIT License](LICENSE)
