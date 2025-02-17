# Software-Engineering-Assignment
Software engineering project
# Branching and Merging Strategy

This document outlines the **branching and merging strategy** used in this repository to manage development workflows, handle changes in code, and maintain project organization. This strategy will ensure that we can effectively collaborate, develop features independently, and maintain a stable version of the project at all times.

## **Branching Strategy**

### 1. **Main Branch (`main`)**
- **Purpose**: 
  - The `main` branch will always reflect the **production-ready** version of the project. This branch is considered stable and deployable at all times.
  - Any code that reaches this branch should have been thoroughly tested and reviewed.
  
- **Usage**: 
  - Only merge into `main` after feature development, testing, and validation are complete.
  - This is the branch from which releases will be made.

### 2. **Development Branch (`development`)**
- **Purpose**: 
  - The `development` branch acts as the **integration branch** for all new features and updates.
  - It is used for integrating feature branches and testing them in combination, making sure that everything works together before merging into `main`.

- **Usage**:
  - Developers will merge their feature branches into `development` after the completion of their features.
  - All ongoing development will be done here until the features are ready to be deployed.

### 3. **Feature Branches (`feature/<feature-name>`)**
- **Purpose**: 
  - Feature branches are used to develop individual features or changes in isolation. Each feature branch corresponds to a specific task or improvement.
  - These branches are short-lived and used to track the progress of a single feature.

- **Naming Convention**: 
  - Feature branches should follow the naming convention: `feature/<feature-name>`.
  - Example: `feature/requirements-documentation`, `feature/spiral-model-analysis`, `feature/comparison-report`.

- **Usage**:
  - When starting work on a new feature, create a new feature branch from the `development` branch.
  - Once the feature is complete, it will be tested and merged back into `development`.

### 4. **Bugfix Branches (`bugfix/<bug-name>`)**
- **Purpose**: 
  - Bugfix branches are used to address issues, bugs, or errors found during development or testing.
  - These branches are created when a problem is identified in the codebase that needs to be resolved urgently.

- **Naming Convention**: 
  - Bugfix branches should be named following the pattern: `bugfix/<bug-name>`.
  - Example: `bugfix/fix-requirements-typos`, `bugfix/fix-spiral-model-error`.

- **Usage**:
  - Bugfixes should always be based on the `development` branch, not `main`.
  - After a bug is fixed, the changes will be committed and merged into the `development` branch.

### 5. **Release Branches (`release/<version-number>`)**
- **Purpose**: 
  - Release branches are used when preparing for a production release. They allow for final adjustments, testing, and bug fixes before making the code production-ready.
  - Once the features and bug fixes in `development` are stable, a release branch will be created.

- **Naming Convention**:
  - Release branches follow the format: `release/<version-number>`.
  - Example: `release/v1.0.0`, `release/v2.0.0`.

- **Usage**:
  - The release branch will be used for final testing, and minor adjustments or bug fixes can be applied here.
  - Once the release is deemed stable, the release branch will be merged into `main`.

---

## **Merging Strategy**

### 1. **Pull Requests (PRs)**
- **Workflow**:
  - Feature branches will be merged into the `development` branch using pull requests (PRs). 
  - Pull requests will be reviewed by team members to ensure quality before merging.
  - PRs will be created for both feature branches and bugfix branches before merging into the `development` or `main` branch.

### 2. **Merge Commit Strategy**
- **Merging Process**:
  - We will use the **"Merge Commit"** strategy for merging feature and bugfix branches into `development` and `main`.
  - Merge commits will keep the project history clean and provide a clear record of when specific features were added.

### 3. **Squash and Merge (Optional)**
- **Purpose**:
  - If a feature branch contains multiple small commits, we may use **Squash and Merge** to combine all changes into a single commit before merging into `development` or `main`.
  - This strategy helps to maintain a concise commit history and avoids unnecessary clutter from small or intermediate commits.

### 4. **Rebase (Optional)**
- **Purpose**:
  - Rebasing is allowed to ensure that feature branches are updated with the latest changes from `development` before merging back.
  - Rebasing will be used carefully to ensure no loss of commit history and to keep the branch history linear.

### 5. **Merge Conflicts**
- **Handling Merge Conflicts**:
  - Merge conflicts may arise when changes made in different branches conflict with each other. When this happens:
    - The developer will manually resolve the conflict in the affected files.
    - After resolving the conflict, the changes should be staged and committed.
    - Once the conflict is resolved, the developer should continue the merging process and push the changes.

---

## **Best Practices**

- **Commit Messages**: Use clear, descriptive commit messages that explain the purpose of the change.
  - Example: `feat: added initial requirements document`, `fix: resolved merge conflict in report.md`, `docs: updated project README.md`.
  
- **Code Reviews**: All pull requests will undergo code reviews before merging to ensure that the code meets the project standards and is free of bugs.

- **Testing**: All features must pass unit tests and integration tests before they are merged into the `development` or `main` branches.

---

## **Project Workflow**

1. **Start a new feature**: Create a feature branch from `development`.
   ```bash
   git checkout -b feature/<feature-name> development
