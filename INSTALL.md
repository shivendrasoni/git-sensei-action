
## Installation
---


#### Run as a GitHub Action

You can use our pre-built Github Action Docker image to run Git-Sensei as a Github Action. 

1. Add the following file to your repository under `.github/workflows/gitsensei.yml`:

```yaml
on:
  pull_request:
  issue_comment:
jobs:
  gitsensei_job:
    runs-on: ubuntu-latest
    name: Run pr agent on every pull request, respond to user comments
    steps:
      - name: Git Sensei
        id: gitsensei
        uses: shivendrasoni/gitsensei-action@main
        env:
          OPENAI_KEY: ${{ secrets.OPENAI_KEY }}
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

2. Add the following secret to your repository under `Settings > Secrets`:

```
OPENAI_KEY: <your key>
```

The GITHUB_TOKEN secret is automatically created by GitHub.

3. Merge this change to your main branch. 
When you open your next PR, you should see a comment from `github-actions` bot with a review of your PR, and instructions on how to use the rest of the tools.

4. You may configure Git-Sensei by adding environment variables under the env section corresponding to any configurable property in the [configuration](./CONFIGURATION.md) file. Some examples:
```yaml
      env:
        # ... previous environment values
        PR_REVIEWER.REQUIRE_TESTS_REVIEW: "false" # Disable tests review
        PR_CODE_SUGGESTIONS.NUM_CODE_SUGGESTIONS: 6 # Increase number of code suggestions
```

