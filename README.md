# github-actions-sample

## Auto Create Pull Request

```yaml
on:
  push:
    branch: develop

jobs:
  pull_request:
    name: Create Pull Request to main
    runs-on: ubuntu-latest

    steps:
      - name: Create Pull Request
        uses: actions/github-script@v4
        with:
          script: |
            return github.pulls.create({
              owner: context.repo.owner,
              repo: context.repo.repo,
              title: 'develop to master',
              head: 'develop',
              base: 'main'
            })
```
