# Question 2: Git and GitHub Workflow

## (a) Introduction to Git and GitHub

### 1. What Is Git?

**Definition:**
Git is a distributed version control system used to track changes in source code and other project files.

It allows developers to maintain project history, create branches, and return to earlier versions when necessary.

**Advantages of Git:**

* **Tracks Changes:** Records changes made to project files.
* **Maintains History:** Allows developers to review previous commits.
* **Supports Branching:** Allows developers to work on different features separately.
* **Helps Resolve Conflicts:** Provides tools to identify and resolve conflicting changes.
* **Supports Collaboration:** Allows multiple developers to work on the same project.

**Example:**
A developer can use Git to track changes made to a JavaScript file and restore an earlier version if necessary.

### 2. What Is GitHub?

**Definition:**
GitHub is an online platform that hosts Git repositories and provides tools for collaboration.

**Main Features:**

* Stores repositories online.
* Allows developers to share their projects.
* Supports code reviews and pull requests.
* Helps teams collaborate on software projects.
* Provides access to project history and documentation.

**Justification:**
GitHub allows developers to store their work online and share it with teachers, teammates, and other developers.

### 3. Difference Between Git and GitHub

| Git                                                      | GitHub                                                 |
| -------------------------------------------------------- | ------------------------------------------------------ |
| Git is a version control system.                         | GitHub is an online repository hosting platform.       |
| It can work locally on a computer.                       | It provides online hosting and collaboration features. |
| It tracks changes in files.                              | It hosts repositories and supports collaboration.      |
| It is commonly used through commands or graphical tools. | It can be accessed through a website and other tools.  |
| Example: `git commit`                                    | Example: Creating a repository on GitHub.              |

### 4. Important Git Commands

Git commands help developers manage project files and maintain version history.

#### Command 1: Initialize a Repository

```bash
git init
```

**Purpose:** Initializes a new Git repository in the current directory.

**Note:** If the project is already a Git repository, this command is usually unnecessary.

#### Command 2: Check Repository Status

```bash
git status
```

**Purpose:** Displays the current repository status, including modified, staged, and untracked files.

#### Command 3: Stage Changes

```bash
git add .
```

**Purpose:** Stages changes in the current directory and its subdirectories, subject to Git's ignore rules.

Staging prepares the selected changes for the next commit.

#### Command 4: Create a Commit

```bash
git commit -m "Initial commit"
```

**Purpose:** Records staged changes in the local repository history.

The message describes the changes included in the commit.

#### Command 5: View Commit History

```bash
git log --oneline
```

**Purpose:** Displays a concise list of previous commits.

It helps developers review the project's history.

#### Command 6: Push Changes to GitHub

```bash
git push
```

**Purpose:** Sends local commits to the configured remote repository.

The branch and remote must be configured correctly, and the user must have permission to push.

---

## (b) The Purpose of .gitignore

### 1. What Is .gitignore?

**Definition:**
The `.gitignore` file specifies files and directories that Git should ignore when identifying untracked files.

It helps prevent unnecessary files, generated files, and sensitive local configuration files from being added to a repository.

### 2. Example of a .gitignore File

```gitignore
node_modules/
.env
```

**Explanation:**

* `node_modules/` — Excludes the directory containing installed npm packages.
* `.env` — Excludes a local environment configuration file that may contain sensitive information.

**Important:**
The `.gitignore` file should be created in the project's root directory.

### 3. Why Is .gitignore Important?

The `.gitignore` file helps developers:

1. Keep the repository organized.
2. Avoid uploading unnecessary generated files.
3. Reduce repository size.
4. Prevent accidental exposure of local configuration files.
5. Avoid tracking files that can be generated again.

**Important Note:**
Adding a file to `.gitignore` does not automatically stop Git from tracking it if it has already been committed. Sensitive information should never be committed to a public repository.

---

## (c) Steps for Uploading a Project to GitHub

The following steps explain how to upload a local project to GitHub.

### Step 1: Create a GitHub Repository

Open GitHub and create a new repository.

Give the repository an appropriate name, such as:

```text
CS408-ASSIGNMENT1
```

Copy the repository URL.

**Note:** If a repository already exists for the assignment, use that repository instead of creating another one.

### Step 2: Open the Project Folder

Open the project folder in Visual Studio Code.

Select:

**Terminal → New Terminal**

Make sure the terminal is open in the correct project directory.

### Step 3: Initialize Git

If the folder is not already a Git repository, run:

```bash
git init
```

This command initializes Git in the current directory.

If Git has already been initialized, there is no need to run this command again.

### Step 4: Check the Repository Status

Run:

```bash
git status
```

This command displays the files Git recognizes as modified, staged, or untracked.

It helps developers identify which changes need to be committed.

### Step 5: Stage Project Files

Run:

```bash
git add .
```

This command stages the project changes that are not excluded by Git's ignore rules.

### Step 6: Commit the Changes

Run:

```bash
git commit -m "Add assignment files"
```

This command records the staged changes in the local Git history.

A meaningful commit message describes the changes being saved.

### Step 7: Connect to the GitHub Repository

If a remote repository has not been configured, run:

```bash
git remote add origin YOUR_REPOSITORY_URL
```

Replace `YOUR_REPOSITORY_URL` with the actual URL of the GitHub repository.

If the remote is already configured, check it using:

```bash
git remote -v
```

**Important:** Do not add the same remote again unnecessarily.

### Step 8: Push the Changes

Check the current branch:

```bash
git branch --show-current
```

If the branch is named `main`, use:

```bash
git push -u origin main
```

This command uploads the local commits to the remote `main` branch and sets up upstream tracking.

If the branch has a different name, use the actual branch name.

### Step 9: Verify the Upload

Open the repository on GitHub.

Check that the required files and folders are visible.

For example:

* `README.md`
* `theory/`
* `practical/`
* `app.js`
* `package.json`

**Conclusion:**
After verifying the upload, the repository link can be shared with the instructor.

---

## (d) Troubleshooting Common Git and GitHub Problems

### 1. Rejected Push

**Problem:**
A push may be rejected when the remote repository contains commits that are missing from the local branch.

**Step 1:** Check the current repository status.

```bash
git status
```

**Step 2:** Check the remote repository.

```bash
git remote -v
```

**Step 3:** If the remote branch contains changes that need to be preserved, integrate them before pushing.

For example, if the remote branch is named `main`, run:

```bash
git pull --rebase origin main
```

If conflicts occur, resolve them before continuing the rebase.

**Step 4:** Push the changes.

```bash
git push
```

**Important:** The correct solution depends on the error message and repository history. Avoid using `git push --force` as a first solution because it can overwrite remote history.

### 2. Merge Conflicts

**Definition:**
A merge conflict occurs when Git cannot automatically combine different changes to the same part of a file.

**Common Causes:**

* Two developers edit the same lines.
* Local and remote changes cannot be combined automatically.
* Different branches contain conflicting modifications.

**Steps to Resolve a Conflict:**

1. Identify the conflicted files using Git's output or `git status`.
2. Open each conflicted file in VS Code.
3. Locate the conflict markers.
4. Decide which changes to keep or combine.
5. Remove the conflict markers.
6. Save the corrected file.
7. Stage the resolved files.

For a merge operation, finish with:

```bash
git add .
git commit -m "Resolve merge conflicts"
```

For a rebase operation, continue with:

```bash
git add .
git rebase --continue
```

**Note:** The correct continuation command depends on whether Git is performing a merge or a rebase.

### 3. Authentication Problems

**Problem:**
GitHub may reject a push if authentication fails or the user does not have permission to access the repository.

**Possible Solutions:**

* Follow the authentication instructions provided by Git or VS Code.
* Confirm that the repository belongs to the correct account or organization.
* Check that the remote URL is correct.
* Verify that you have permission to push changes.
* Use an authentication method supported by GitHub.

**Security Tip:**
Never publish passwords, personal access tokens, or private keys in a public repository.

### 4. Files Are Missing from GitHub

**Problem:**
Some files may not appear on GitHub after uploading a project.

**Possible Causes:**

* The files have not been staged.
* The changes have not been committed.
* The latest commit has not been pushed.
* The files are excluded by `.gitignore`.
* The files are on a different branch.

**Solution:**

First, check the repository status:

```bash
git status
```

Stage the required changes:

```bash
git add .
```

Create a commit:

```bash
git commit -m "Add missing assignment files"
```

Push the changes:

```bash
git push
```

If the files are still missing, check `.gitignore` and confirm that you are viewing the correct repository and branch.

---

## Overall Conclusion

Git and GitHub are important tools in modern software development.

Git tracks changes, maintains project history, and supports branching. GitHub hosts repositories online and provides features for sharing and collaboration.

The `.gitignore` file helps prevent unnecessary files from being tracked. By understanding Git commands and learning how to troubleshoot common problems, developers can manage projects more effectively and collaborate with other team members.
