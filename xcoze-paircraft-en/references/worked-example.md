# Worked example: Event signup tool

This fictional example takes one product from discussion through review and revision.

## 1. Start with a rough idea

A product manager says, “I'd like to make an event signup tool. Let's talk it through first.” The agent identifies the organizer's and attendee's tasks and suggests testing only the first-version path: fill in the form, submit it, and see the result. The product manager confirms that sign-in is unnecessary and leaves capacity limits for a later discussion. This round ends with a short brief, the flow, and the remaining decisions.

## 2. Choose something reviewers can use

The next question is whether attendees understand the signup result. The team chooses a clickable path, keeps copy and demo data in one place, and shares a preview people can open directly. The review task is “Register, then find your signup details.” An annotated wireframe would be enough if the only question were the order of the steps.

## 3. Turn feedback into a specific change

The reviewer says, “It's hard to tell where to go after success.” The agent identifies the primary button on the confirmation page and confirms with the product manager that the problem is finding the signup details.

- **Target** — The primary button on the signup confirmation page.
- **Expected behavior** — Label it “View my signup” and open the details page on click.
- **Preserve** — Existing form fields and submission rules.
- **Verify** — Submit the form, check that the new button appears, open the details, return, and check that repeat submissions follow the existing rules.

The agent updates the editable source and the review preview. The product manager can use the same page name, selected layer, or copy configuration to specify the next edit.
