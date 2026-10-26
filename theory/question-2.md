# Question 2: Git and GitHub Workflow

## (a) Introduction to Git and GitHub

### 1. What Is Git?

Git is a distributed version control system used to track changes in source code and other project files. It allows developers to maintain a history of their work and return to earlier versions when necessary.

**Advantages of Git:**

* Tracks changes made to files.
* Maintains project history.
* Supports branching and merging.
* Helps multiple developers work on the same project.
* Makes it easier to identify and resolve problems.

### 2. What Is GitHub?

GitHub is an online platform used to host Git repositories. It allows developers to upload projects, share code, collaborate with others, and review changes.

### 3. Difference Between Git and GitHub

| Git                                 | GitHub                                                     |
| ----------------------------------- | ---------------------------------------------------------- |
| A version control system.           | An online platform for hosting repositories.               |
| Can work locally on a computer.     | Provides online storage and collaboration features.        |
| Tracks changes in files.            | Allows developers to share and review repositories.        |
| Uses commands such as `git commit`. | Supports pull requests, issues, and repository management. |

## (b) Important Git Commands

The following commands are commonly used to manage a project with Git.

### 1. Initialize a Repository

```bash
git init
```

This command initializes a Git repository in the current directory.

### 2. Check the Repository Status

```bash
git status
```

This command displays modified, staged, and untracked files.

### 3. Add Files to the Staging Area

```bash
git add .
```

This command stages changes in the current directory and its subdirectories, except files excluded by Git rules.

### 4. Commit Changes

```bash
git commit -m "Initial commit"
```

A commit records the staged changes in the repository's history.

### 5. View Commit History

```bash
git log
```

This command displays the repository's commit history.

### 6. Connect a Remote Repository

```bash
git remote add origin <repository-url>
```

This command connects the local repository to a remote repository. Replace `<repository-url>` with the actual GitHub repository URL.

### 7. Rename the Current Branch

```bash
git branch -M main
```

This command renames the current branch to `main`.

### 8. Upload Changes to GitHub

```bash
git push -u origin main
```

This command uploads the local branch to GitHub and establishes an upstream relationship for future pushes.

## (c) Purpose of the .gitignore File

The `.gitignore` file tells Git which untracked files and directories should be ignored.

It helps prevent unnecessary files and sensitive information from being added to a repository.

Example:

```gitignore
node_modules/
.env
```

### Explanation

* `node_modules/` contains installed npm packages. It can usually be recreated by installing the dependencies.
* `.env` commonly contains environment variables and may include passwords, tokens, or API keys.

**Important:** `.gitignore` does not automatically remove files that Git is already tracking. Sensitive information should never be committed to a public repository.

## (d) GitHub Workflow and Troubleshooting

### 1. Basic GitHub Workflow

A typical workflow consists of the following steps:

1. Create or open a project folder.
2. Initialize Git if the folder is not already a repository.
3. Create and edit project files.
4. Check changes using `git status`.
5. Stage changes using `git add .`.
6. Commit changes using `git commit -m "Descriptive message"`.
7. Connect the GitHub repository if necessary.
8. Upload changes using `git push`.

Example:

```bash
git status
git add .
git commit -m "Update assignment files"
git push
```

These commands should be executed in the correct project directory.

### 2. What Is a Rejected Push?

A rejected push occurs when Git cannot upload local changes because the remote repository has changes or another issue prevents the update.

One common reason is that the remote repository contains commits that are missing from the local branch.

### 3. How to Troubleshoot a Rejected Push

First, inspect the repository status and remote configuration:

```bash
git status
git remote -v
git branch
```

If the remote branch contains changes that are missing locally, retrieve and integrate those changes before pushing again.

For example:

```bash
git pull --rebase origin main
git push
```

This example assumes that the remote branch is named `main` and that the local repository is configured to use it.

If Git reports conflicts, resolve them carefully before continuing.

**Important:** Do not use `git push --force` as the first solution because it can overwrite remote history.

### 4. Collaboration Through GitHub

GitHub supports collaboration through shared repositories, branches, pull requests, and code reviews.

A typical collaborative workflow is:

1. A team member creates a branch.
2. The team member makes changes and commits them.
3. The branch is pushed to GitHub.
4. A pull request is created.
5. Other team members review the changes.
6. The changes are merged after approval.

This process helps teams review their work and manage changes systematically.

## Conclusion

Git and GitHub are important tools in modern software development. Git tracks changes and maintains project history, while GitHub provides online repository hosting and collaboration features. Commands such as `git add`, `git commit`, `git pull`, and `git push` help developers manage their work. A properly configured `.gitignore` file also helps keep unnecessary files and sensitive information out of the repository.
