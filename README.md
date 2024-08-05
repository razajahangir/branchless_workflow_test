# Branchless Git Workflow

This repository demonstrates a branchless Git workflow inspired by Nick Humrich. The goal is to streamline development by eliminating the complexity of managing multiple branches, mimicking trunk-based development (TBD) locally.

**Nick Humrich's LinkedIn**: [Nick Humrich](https://www.linkedin.com/in/nhumrich/)

## Workflow Steps

### No In-Progress Work Update

If you have no local changes and want to update your `main` branch to the latest version from the remote `main` branch:

```sh
git pull
```

### In-Progress Work, but Need to Change Contexts

If you have changes but need to switch tasks, stash your work:

```sh
git stash
git pull
```

### In-Progress Work, but Don't Care About It

If you have changes that you don't care about and want to discard them, fetch the latest changes and reset your local `main` branch to match the remote `main`:

```sh
git fetch
git reset --hard origin/main
```

### Push Changes for a PR

If you have completed your changes and want to push them to a remote branch for a pull request:

```sh
git push origin main:my-pr-that-does-a-thing
```

### Update Changes on a PR

If you need to update your changes on the PR, amend the commit and force push:

```sh
git commit --amend
git push -f origin main:my-pr-that-does-a-thing
```

### Restore Something in the Stash

If you need to bring back your stashed changes:

```sh
git stash pop
```

## Summary of Commands

### Initialize Repository

```sh
git init
git remote add origin https://github.com/yourusername/branchless-git-workflow.git
```

### Commit Initial Changes

```sh
echo "# Branchless Git Workflow" > README.md
git add README.md
git commit -m "Initial commit"
git push -u origin main
```

### Update without In-Progress Work

```sh
git pull
```

### Stash In-Progress Work

```sh
git stash
git pull
```

### Discard In-Progress Work

```sh
git fetch
git reset --hard origin/main
```

### Push Changes for PR

```sh
git push origin main:my-pr-that-does-a-thing
```

### Update Changes on PR

```sh
git commit --amend -m "Updated PR with latest changes"
git push -f origin main:my-pr-that-does-a-thing
```

### Restore Stashed Work

```sh
git stash pop
```

## Acknowledgments

This workflow was initially created by Nick Humrich. You can find more about him on his [LinkedIn profile](https://www.linkedin.com/in/nhumrich/).
```

Copy and paste the above content into your `README.md` file in your repository. This single markdown file contains all the instructions and information about the branchless Git workflow. If you have any further questions or need additional help, feel free to ask!
