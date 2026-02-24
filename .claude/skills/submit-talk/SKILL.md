---
name: submit-talk
description: Use when submitting a talk proposal to the BoulderJS talks repo, creating a lightning or feature talk issue on GitHub.
---

# Submit a BoulderJS Talk Proposal

Creates a GitHub issue in `boulder-js/talks` using the correct format and label. Labels cannot be applied by regular users — they must be set via `--label` in the CLI.

## Required Information

Collect from context or ask the user one at a time:

| Field | Notes |
| --- | --- |
| **Title** | Short talk title |
| **Type** | Feature (25 min) or Lightning (10 min) |
| **Abstract** | ~500 chars, what the talk covers |
| **Date** | Earliest available date (`dd.mm.yyyy`), or `TBD` |
| **First talk?** | Whether this is the speaker's first tech talk |

Code of Conduct is always checked — include it unconditionally.

## Talk Types & Labels

| Type | Duration | Label |
| --- | --- | --- |
| Feature | 25 min | `Talk: Feature :cinema:` |
| Lightning | 10 min | `Talk: Lightning :zap:` |

## Create the Issue

```bash
gh issue create \
  --repo boulder-js/talks \
  --title "TITLE" \
  --label "Talk: Feature :cinema:" \
  --body "$(cat <<'EOF'
### Abstract

ABSTRACT

### Date

DD.MM.YYYY

### This will be my first tech talk

- [ ] This will be my first tech talk

### Code of Conduct

- [x] I agree to follow this project's [Code of Conduct](https://github.com/boulder-js/.github/blob/main/CODE_OF_CONDUCT.md)
EOF
)"
```

Set `- [x]` on the first-talk checkbox if applicable. Swap the label for `Talk: Lightning :zap:` for lightning talks.

## After Creating

Return the issue URL to the user.
