# Branchless Git Workflow

This repository demonstrates a branchless Git workflow, inspired by Nick Humrich, designed to streamline development by working directly on the `main` branch. This approach mimics trunk-based development (TBD) locally and simplifies version control without the need for managing multiple branches.

**Nick Humrich's LinkedIn**: [Nick Humrich](https://www.linkedin.com/in/nhumrich/)

## Workflow Overview

In this workflow, you work directly on the `main` branch and use the following commands to handle different development scenarios:

1. **No In-Progress Work Update**
2. **In-Progress Work, but Need to Change Contexts**
3. **In-Progress Work, but Don't Care About It**
4. **Push Changes for a PR**
5. **Update Changes on a PR**
6. **Restore Something in the Stash**

## Scenario 1: No In-Progress Work Update

**Situation**: You have no local changes and want to update your `main` branch to the latest version from the remote `main` branch.

**Command**:
```sh
git pull
```

**Steps**:
1. Open your terminal and navigate to your project directory.
   ```sh
   cd my-branchless-project
   ```
2. Pull the latest changes from the remote `main` branch.
   ```sh
   git pull
   ```

## Scenario 2: In-Progress Work, but Need to Change Contexts

**Situation**: You have changes that you want to keep but need to switch tasks or update your branch with the latest changes from the remote `main` branch.

**Commands**:
```sh
git stash
git pull
```

**Steps**:
1. Open your terminal and navigate to your project directory.
   ```sh
   cd my-branchless-project
   ```
2. Stash your current changes.
   ```sh
   git stash
   ```
3. Pull the latest changes from the remote `main` branch.
   ```sh
   git pull
   ```
4. Reapply your stashed changes.
   ```sh
   git stash pop
   ```

## Scenario 3: In-Progress Work, but Don't Care About It

**Situation**: You have local changes that you don't care about and want to discard them to update your branch with the latest changes from the remote `main` branch.

**Commands**:
```sh
git fetch
git reset --hard origin/main
```

**Steps**:
1. Open your terminal and navigate to your project directory.
   ```sh
   cd my-branchless-project
   ```
2. Fetch the latest changes from the remote repository.
   ```sh
   git fetch
   ```
3. Reset your local `main` branch to match the remote `main` branch, discarding any local changes.
   ```sh
   git reset --hard origin/main
   ```

## Scenario 4: Push Changes for a PR

**Situation**: You have completed your changes and want to push them to a remote branch for a pull request.

**Command**:
```sh
git push origin main:<branch-name>
```

**Steps**:
1. Make your changes and commit them locally. For example, create a new file and commit it.
   ```sh
   echo "This is a new feature" > feature.txt
   git add feature.txt
   git commit -m "Add new feature"
   ```
2. Push your changes to a remote branch for a pull request.
   ```sh
   git push origin main:my-pr-that-does-a-thing
   ```

## Scenario 5: Update Changes on a PR

**Situation**: You need to update your changes on an existing pull request.

**Commands**:
```sh
git commit --amend
git push -f origin main:<branch-name>
```

**Steps**:
1. Make updates to your changes and commit them.
   ```sh
   echo "Update feature" >> feature.txt
   git add feature.txt
   git commit --amend -m "Update new feature"
   ```
2. Force push the amended commit to the remote branch.
   ```sh
   git push -f origin main:my-pr-that-does-a-thing
   ```

## Scenario 6: Restore Something in the Stash

**Situation**: You need to bring back your stashed changes.

**Command**:
```sh
git stash pop
```

**Steps**:
1. Open your terminal and navigate to your project directory.
   ```sh
   cd my-branchless-project
   ```
2. Apply the stashed changes back to your working directory.
   ```sh
   git stash pop
   ```

## Summary of Commands

1. **Initialize Repository**:
   ```sh
   git init
   git remote add origin https://github.com/yourusername/branchless-git-workflow.git
   ```

2. **Commit Initial Changes**:
   ```sh
   echo "# Branchless Git Workflow" > README.md
   git add README.md
   git commit -m "Initial commit"
   git push -u origin main
   ```

3. **Update without In-Progress Work**:
   ```sh
   git pull
   ```

4. **Stash In-Progress Work**:
   ```sh
   git stash
   git pull
   git stash pop
   ```

5. **Discard In-Progress Work**:
   ```sh
   git fetch
   git reset --hard origin/main
   ```

6. **Push Changes for PR**:
   ```sh
   git push origin main:my-pr-that-does-a-thing
   ```

7. **Update Changes on PR**:
   ```sh
   git commit --amend -m "Updated PR with latest changes"
   git push -f origin main:my-pr-that-does-a-thing
   ```

8. **Restore Stashed Work**:
   ```sh
   git stash pop
   ```

## Acknowledgments

This workflow was initially created by Nick Humrich. You can find more about him on his [LinkedIn profile](https://www.linkedin.com/in/nhumrich/).
