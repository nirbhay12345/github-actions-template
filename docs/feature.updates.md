
# Push Changes Workflow

This GitHub Actions workflow is designed to automatically push changes from a feature branch to its corresponding development (`-dev`) and main (`-main`) branches within the repository.

## Trigger

The workflow is triggered whenever changes are pushed to a branch starting with the prefix `feature/`.

```yaml
on:
  push:
    branches:
      - "feature/*" # Trigger on any branch starting with 'feature/'
```

## Permissions

The workflow requires write permissions to perform branch creation and force pushing changes to the repository.

- Permissions: Write-All

## Workflow Steps

### Step 1: Checkout Code

Checks out the code from the repository.

### Step 2: Get Branch Name

Retrieves the name of the branch where changes were pushed.

### Step 3: Push Changes to Dev and Main Branches

1. Extracts the branch name and defines the development and main branches (`-dev` and `-main` respectively).
2. Obtains the current local branch name.
3. Forces push the changes from the current branch to the respective `dev` and `main` branches on the remote repository.

#### Note

- **Caution:** The `-f` flag used in `git push` enforces a force push, potentially overwriting history. Exercise caution when using force pushes in a shared repository.
