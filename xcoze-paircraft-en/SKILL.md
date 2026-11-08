---
name: xcoze-paircraft-en
description: Work with the user in English to shape product requirements, build reviewable prototypes from agreed flows, and turn feedback into specific, verifiable changes. Use for product discovery, requirements discussions, prototype reviews, and product revisions. Handle simple copy edits or small, well-defined code fixes directly.
---

# XCoze-PairCraft

Help the product manager and AI work from the same understanding of the product and hand over work that can be edited later. Conversation decisions, editable sources, and review artifacts serve different purposes. Make it easy to find where a change belongs and tell whether it matches the user's intent. Use English by default and follow the user's requested language.

## Start with this round's goal

- Read the accessible requirements, prototypes, feedback, and decisions. Fill only the gaps that affect the current round. Point out specific conflicts and their consequences.
- Identify whether the user wants to discuss requirements, prepare a review, or implement agreed feedback. Respect instructions such as “discussion only,” “draft first,” and “make the change.” For complex work, state the intended deliverable in one sentence.
- Separate confirmed facts, user decisions, provisional assumptions, demo content, and open questions. For small tasks, explain the relevant distinctions in prose. State low-impact, reversible assumptions and proceed. Leave decisions that change product scope, core flows, or business rules to the user. Carry out routine choices the user has already authorized.

## Choose the deliverable that fits

- **Shape requirements.** Identify who faces what problem, in what situation, and what outcome they need. Pick one valuable primary flow. Define the scope for this round and the unknowns that affect decisions. If the user wants to discuss first, finish with a brief or draft flow they can make decisions from.
- **Prepare a review.** Define what the reviewer needs to decide, then choose a flow diagram, wireframe, or clickable prototype. Label demo data where it appears. For self-guided reviews, provide a task reviewers can start on their own and a way to reset the demo when needed.
- **Implement or revise.** Locate the requirement, flow, page, component, or rule affected by the feedback. Clarify the expected behavior and what should stay as it is. Update the corresponding source. Check related entry points, states, and dependencies when a change affects several places. Complete and verify small, clearly scoped changes directly.

Read [working modes](references/modes.md) when switching modes or clarifying scope.

## Leave a clear place for the next edit

- Reuse the project's editable designs, specs, code, and version history. For things people will edit again, give them a clear point of reference, such as a selected layer, page name, or stable ID.
- When handing over a prototype, identify where the user can edit content, data, styles, or rules. Choose a canvas, spreadsheet, configuration file, or modular source based on the tools and scale. When a single HTML file is needed for sharing, provide it as an export and explain how to regenerate it after editing.
- Locate the target of vague feedback first. Turn “make this more prominent” into an observable change and clarify important things to preserve. When a change spans people, artifacts, or rounds, record the goal, change, impact, and checks. Read the [collaboration templates](references/artifact-templates.md) when a ready-to-use format would help.

## Verify and hand over

Match the check to the goal. Can the user make a decision from the requirements? Can the reviewer finish the key task? Can someone reproduce the change, and do the preserved parts still work? Report each deliverable separately. State what was actually checked, what remains open, and who needs to act next. Read [quality checks](references/quality-gates.md) for complex reviews or delivery.

The [worked example](references/worked-example.md) shows how a rough idea becomes a prototype and how feedback becomes a precise change.
