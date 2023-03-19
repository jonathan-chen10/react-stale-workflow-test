# Update State Workflow

For use in [this issue](https://github.com/Northeastern-Electric-Racing/FinishLine/issues/481) in the NER FinishLine repo.

## Specifications

We want a workflow with the following:

- Triggers when assignee is added to issue.
- Immediately remove "stale" tag if there is one.
- X days later:
  - If there is no open PR linked to the issue: add "stale" tag
- Ignore "epic" tickets (probably easy to implement)

## Possible Solutions

### actions/stale

The convenient [Action](https://github.com/actions/stale) the GitHub has is very nice. But it has a limitations. There are two options (`ignore-updates` on/off) for update detection: either check a fixed time (since issue creation?) or reset with any activity, which includes comments and commits and a whole lot of other things.

I'm not too sure how to rig this up, but I can look into it if we are OK with these limitations.

### ChatGPT Prompt

This is the prompt I gave to ChatGPT.

> Write a GitHub workflow YAML that activates when an issue gets a new assignee. At this time, the "stale" label should be cleared. Fifteen days afterward, if the issue has no open PR, it should then add the "stale" label to the issue. This should occur for all issues that do not have the "epic" label.

You can see the outputs, with comments, in the YAML files in this directory.
