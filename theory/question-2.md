# Question 2: Git and GitHub Workflow

## (a) Introduction to Git and GitHub

### 1. What Is Git?

Git is a distributed version control system used to track changes in source code and other project files. It allows developers to maintain different versions of a project and return to earlier versions when necessary.

**Advantages of Git:**

* Tracks changes made to files.
* Maintains project history.
* Allows developers to create branches.
* Helps identify and resolve conflicts.
* Supports collaboration among team members.

### 2. What Is GitHub?

GitHub is an online platform that hosts Git repositories. It allows developers to store projects online, share their work, review changes, and collaborate with other developers.

### 3. Difference Between Git and GitHub

| Git                                                 | GitHub                                                 |
| --------------------------------------------------- | ------------------------------------------------------ |
| Git is a version control system.                    | GitHub is an online repository hosting platform.       |
| It can work locally on a computer.                  | It provides online hosting and collaboration features. |
| It tracks changes in files.                         | It hosts repositories and supports collaboration.      |
| It is operated through commands or graphical tools. | It can be used through a website and other tools.      |

### 4. Important Git Commands

**Initialize a repository:**

```bash
git init
```

This command initializes a Git repository in the current directory.

**Check repository status:**

```bash
git status
```

This command displays modified, staged, and untracked files.

**Stage changes:**

```bash
git add .
```

This command stages changes in the current directory and its subdirectories, subject to Git's ignore rules.

**Create a commit:**

```bash
git commit -m "Initial commit"
```

A commit records the staged changes in the repository history.

**View commit history:**

```bash
git log --oneline
```

This command displays a concise history of commits.

**Push changes to GitHub:**

```bash
git push
```

This command sends local commits to the configured remote repository when the branch and remote are properly configured.

---

## (b) The Purpose of .gitignore

### 1. What Is .gitignore?

The `.gitignore` file specifies files and directories that Git should ignore when identifying untracked files.

It helps prevent unnecessary files, generated files, and sensitive local configuration files from being added to a repository.

### 2. Example of a .gitignore File

```gitignore
node_modules/
.env
```

**Explanation:**

* `node_modules/` excludes the directory containing installed npm packages.
* `.env` excludes a local environment configuration file that may contain sensitive values.

### 3. Why Is .gitignore Important?

The `.gitignore` file helps to:

1. Keep the repository organized.
2. Avoid uploading unnecessary generated files.
3. Reduce repository size.
4. Prevent accidental exposure of local configuration files.

**Important:** Adding a file to `.gitignore` does not automatically remove it if Git is already tracking it. Sensitive information should never be committed to a public repository.

---

## (c) Steps for Uploading a Project to GitHub

The following steps explain how to upload a local project to a GitHub repository.

### Step 1: Create a GitHub Repository

Create a repository on GitHub and note its remote URL.

If a repository already exists, use that repository instead of creating another one.

### Step 2: Open the Project Folder

Open the project folder in Visual Studio Code and open its integrated terminal.

### Step 3: Initialize Git

If the folder is not already a Git repository, run:

```bash
git init
```

If Git is already initialized, there is no need to run this command again.

### Step 4: Check the Repository Status

```bash
git status
```

This command shows which files Git recognizes as modified, staged, or untracked.

### Step 5: Stage Project Files

```bash
git add .
```

This command stages the project files that are not excluded by Git's ignore rules.

### Step 6: Commit the Changes

```bash
git commit -m "Add assignment files"
```

This command records the staged changes in the local Git history.

### Step 7: Connect the GitHub Repository

If a remote has not already been configured, use:

```bash
git remote add origin YOUR_REPOSITORY_URL
```

Replace `YOUR_REPOSITORY_URL` with the actual URL of your GitHub repository.

If the remote already exists, inspect it with:

```bash
git remote -v
```

Do not add the same remote again unnecessarily.

### Step 8: Push the Changes

Check the current branch:

```bash
git branch --show-current
```

If your branch is named `main`, you can push it using:

```bash
git push -u origin main
```

Use the actual branch name if it is different.

### Step 9: Verify the Upload

Open your GitHub repository in a web browser and check that the required project files and folders are visible.

---

## (d) Troubleshooting Common Git and GitHub Problems

### 1. Rejected Push

A push may be rejected when the remote repository contains commits that are missing from the local branch.

**Possible solution:**

First, inspect the current status:

```bash
git status
```

Check the configured remote:

```bash
git remote -v
```

If the remote contains changes that need to be preserved, integrate them carefully before pushing.

For example, if the remote branch is `main`:

```bash
git pull --rebase origin main
```

After resolving any conflicts and completing the rebase, push again:

```bash
git push
```

The exact solution depends on the error message and the repository's history.

**Important:** Do not use `git push --force` as a first solution because it can overwrite remote history.

### 2. Merge Conflicts

A merge conflict occurs when Git cannot automatically combine changes to the same part of a file.

**Steps to resolve a conflict:**

1. Run the relevant Git command and identify the conflicted files.
2. Open each conflicted file in VS Code.
3. Find the conflict markers.
4. Decide which changes to keep or combine.
5. Remove the conflict markers.
6. Save the corrected file.
7. Stage the resolved file.

For a merge, continue with:

```bash
git add .
git commit -m "Resolve merge conflicts"
```

For a rebase, use the appropriate continuation command:

```bash
git rebase --continue
```

The continuation command depends on whether the operation was a merge or a rebase.

### 3. Authentication Problems

GitHub may require authentication when pushing changes.

**Possible solutions:**

* Follow the authentication instructions provided by Git or VS Code.
* Confirm that you have permission to access the repository.
* Check that the remote URL points to the correct repository.
* Use an authentication method supported by GitHub.

Never publish passwords, personal access tokens, or private keys in your repository.

### 4. Files Are Missing from GitHub

If files are not visible on GitHub, check the repository status:

```bash
git status
```

Stage and commit the required changes:

```bash
git add .
git commit -m "Add missing assignment files"
```

Then push:

```bash
git push
```

Also check whether the missing files are excluded by `.gitignore`.

---

## Conclusion

Git and GitHub are important tools in modern software development. Git tracks changes and maintains project history, while GitHub provides online hosting and collaboration features.

By using Git commands correctly, maintaining a suitable `.gitignore` file, and understanding how to resolve common errors, developers can organize their projects and collaborate more effectively.
