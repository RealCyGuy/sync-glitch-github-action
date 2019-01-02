# GitHub Action for Glitch

Wraps the [sync-glitch CLI](https://github.com/glitch-tools/sync-glitch-cli) to enable execute the command.

## Usage

```hcl
# .github/main.workflow

workflow "Sync changes in your GitHub repository to glitch.com" {
  on = "push"
  resolves = ["Deploy"]
}

action "Deploy" {
  uses = "glitch-tools/sync-glitch-github-action@master"
  secrets = ["GLITCH_PROJECT_ID", "GLITCH_TOKEN"]
}
```

### Secrets

- `GLITCH_PROJECT_ID` - **Required** The `projectId` of yours.
- `GLITCH_TOKEN` – **Required** The `authorization` of yours.

For more details on [glitch-tools/sync-glitch-cli#how-to-get-required-environment-variables](https://github.com/glitch-tools/sync-glitch-cli#how-to-get-required-environment-variables)
