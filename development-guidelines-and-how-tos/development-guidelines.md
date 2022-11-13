---
description: >-
  In this section you will read about best practicies when adding new features
  to this project
---

# 📒 Development guidelines

### Pull Requests

When adding a new feature, start by creating a git branch whith the following command.

```
git checkout -b name_of_your_branch main
```

R-THAÏ project follow a commit convention forked from the [Angular](https://github.com/angular/angular/blob/main/CONTRIBUTING.md) one. Here are the possible commit types.

```git
build: Changes that affect the build system or external dependencies (example scopes: cmake, npm)
ci: Changes to our CI configuration files and scripts (examples: GitHubActions)
docs: Documentation only changes
feat: A new feature
fix: A bug fix
perf: A code change that improves performance
refactor: A code change that neither fixes a bug nor adds a feature
test: Adding missing tests or correcting existing tests
```

So your commit must look as this one for example.

```
git commit -m "feat: add sound when clicking a button" -S
```

After pushing your branch and made sure your feature is done and tested, here come the time of creating a Pull Request on GitHub whith detailed description of your feature. It will be reviewed and merged afterward if accepted. Don't forgot to delete your branch afterward.
