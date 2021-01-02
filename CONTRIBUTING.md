# Contributing

This guide is open to contributions.

## Code formatting conventions

All code must be correctly formatted.
Codestyles should be added for a project.
However, there are often things that auto-format cannot account for.

The codestyle should adhere to these rules.
This will vary from language to language, based on capability.
The general principle is that like constructs should be clearly evident from the formatting.
This is in keeping with [Clean Up Your Mess - A Guide to Visual Design for Everyone](www.visualmess.com)
This principle will stand out with the choice of brace and parameter styles.
Besides the rules listed below, stick to language default recommendations and keep individual files consistent.
See the examples below to help clarify some of the rules listed.

- Add comments to document WHY code is the way it is.
- Prefer to make code functionality clear instead of commenting WHAT it does.
- Do not add excess newlines around type/function boundaries.
- It is good to use newlines to make groups of statements clear.
- Wherever possible, use Allman or Stroustrup style braces and indenting.
  - Put opening braces (`{`) on a new line, at very least for high-level constructs like types or functions.
  - Nothing should ever trail a closing brace (`}`). So `else` should start its own line for example.
- Parentheses may follow the brace formatting when they cover multiple lines, but this is less important.
- Indent with 2 spaces.
- Function parameters and chained method calls should be knocked down when 'long'.
  The term 'long' is flexible and involves a consideration for both line length and number of parameters/calls.
  - Anything more than three parameters/calls should most likely be knocked down.
  - Whenever knocking down, all items must be at the same indent level
  - Knocked down items should NOT be aligned to any previous code structure.

### Example 1 - Brace (block) style

Prefer the earlier construct wherever possible.

```kotlin
// Prefer
if (...)
{
  ...
}
else
{
  ...
}

// Over
if (...) {
  ...
}
else {
  ...
}

// Over
if (...) {
  ...
} else {
  ...
}
```

### Example 2 - Multi-item knock down

```kotlin
// Correct
function(
  param1,
  param2,
  param3)

// Not correct - similar elements not visually connected
function(param1,
  param2,
  param3)

function(param1, param2, param3,
  param4, param5, param6)

// Not correct - formatting dependent on previous code element
function(param1,
         param2,
         param3)
```

## Source control conventions

### Commit messages

This spec is similar to most other online references, with some small adaptations.

- The summary must be only a single line.
- Capitalize the summary.
- Do not end the summary with a period.
- Use the imperative mood in the subject line (i.e `Add` vs `Added`/`Adding`).
- Separate the summary line from the body with a blank line.
- Limit all content to 100 characters in width.
- Use the body to explain what and why vs. how.

### Branch structure

- Never merge `master` into a development branch.
  If you need changes from master or to resolve conflicts, please rebase.
- All other branches should be considered ephemeral and prone to change at any time.
  Naturally, if developers are collaborating on a branch they should establish a way to do so effectively.
- Branches should preferably, but not necessarily, be rebased onto the latest `master` commit.
- Merges to `master` should force a merge commit. i.e. `git merge --no-ff`.
