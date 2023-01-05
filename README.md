# github-actions-more-on-events

- I have created this repository to understand how event filtering and action types work with events. I searched plenty of events while doing this.

```yaml
...
on:
  pull_request:
    types:
      - opened  # trigger the workspace whenever new pull request is opened on the branches declared below.
    branches:
      - main
  push:
    branches:
      - main  # targets main branch
      - 'feature-*'  # targets all branches named feature-1 feature-new (except / character)
      - 'dev/**'  # targets all branches named dev/new dev/new/button (includes / character)
    paths-ignore:
      - '.github/workspaces/*' # ignore the changes in this path whenever pushing occurs on branches declared above. (don't trigger the workflow due to changes in this path)
```
- Later, I searched what causes that the workflow to be canceled and how I should cancel workflow manually.
- Then, I searched how to skip a workflow when a push occurs with a small change that does not affect the work of project. 
(like adding just comments and then creating a new commit as well)

- I experienced how to "approve & run" the triggering request of workflow when a new contributor forks the repo and then creates new pull request.
- I studied what kind of impact would occur on workflow when contributors or collaborators make a new pull request.
