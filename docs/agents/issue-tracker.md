# Issue tracker

Issues and specs live in GitHub Issues for `hvnxdr/openbot`.
Use the `gh` CLI from this clone.

## Operations

- Publish a ticket with `gh issue create --title "..." --body-file <path>`.
- Fetch a ticket with `gh issue view <number> --comments`.
- List tickets with `gh issue list`, using state and label filters.
- Comment with `gh issue comment <number> --body-file <path>`.
- Apply or remove labels with `gh issue edit <number> --add-label "..."`
  or `--remove-label "..."`.
- Close a ticket with `gh issue close <number> --comment "..."`.

Use files containing actual newlines for multiline bodies.

## Pull requests

PRs as a request surface: no.

GitHub issues and pull requests share a number space. When a reference
might identify a pull request, resolve it with `gh pr view <number>`
before falling back to `gh issue view <number>`.

## Wayfinding

The map is one issue labelled `wayfinder:map`, containing notes,
decisions, and unresolved questions.

Create child tickets as GitHub sub-issues. If sub-issues are unavailable,
use a task list in the map and add `Part of #<map>` to each child.
Use `wayfinder:research`, `wayfinder:prototype`, `wayfinder:grilling`,
or `wayfinder:task` labels.

Record blockers with GitHub issue dependencies. If unavailable,
add `Blocked by: #<number>` to the child body.
A child is unblocked when every blocker is closed.

Choose the first open, unassigned, unblocked child in map order.
Claim it with `gh issue edit <number> --add-assignee @me`.
When resolved, comment with the answer, close the child, and add
a summary and link to the map's decisions.
