
# Feature Branches Workflow

This GitHub Actions workflow is designed to automate the creation of development (`-dev`) and main (`-main`) branches when a new feature branch is created. It ensures the seamless setup of branches for parallel development and subsequent merging.

## Trigger

The workflow is triggered whenever a branch with the prefix `feature/` is created.

```yaml
on:
  create:
    branches:
      - "feature/*" # Trigger on any branch starting with 'feature/'
```

## Permissions

This workflow requires specific permissions to perform various actions within the repository. It is configured with the following permissions:

- Actions
- Checks
- Contents
- Deployments
- ID token
- Issues
- Discussions
- Packages
- Pages
- Pull requests
- Repository projects
- Security events
- Statuses

## Workflow Steps

### Step 1: Checkout Code

Checks out the code from the repository.

### Step 2: Get Branch Name

Retrieves the name of the newly created branch.

### Step 3: Create and Push Branches

1. Extracts the branch name and defines the development and main branches (`-dev` and `-main` respectively).
2. Obtains the current local branch name.
3. Creates and pushes the new `dev` and `main` branches to the remote repository.
4. Sets upstream for the development and main branches.

#### Note

- This workflow assumes the local branch name is the same as the feature branch being created (`feature/your-branch-name`).
