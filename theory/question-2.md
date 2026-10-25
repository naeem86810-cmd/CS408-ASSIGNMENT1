# Question 2: Git and GitHub Workflow

## (a) Basic Git Workflow

Git is a version control system that tracks changes in project files. GitHub is an online platform for hosting Git repositories.

### Important Git Commands

**1. Check Repository Status**

```bash
git status
```

Displays modified, staged, and untracked files.

**2. Add Files to the Staging Area**

```bash
git add .
```

Stages changes for the next commit.

**3. Commit Changes**

```bash
git commit -m "Add assignment files"
```

Saves a snapshot of the staged changes.

**4. Check the Current Branch**

```bash
git branch
```

Displays the local branches.

**5. Connect a Remote Repository**

```bash
git remote add origin YOUR_REPOSITORY_URL
```

Connects the local repository to a remote repository. Replace `YOUR_REPOSITORY_URL` with the actual GitHub repository URL. If `origin` is already configured, do not run this command again.

**6. Push Changes to GitHub**

```bash
git push -u origin main
```

Uploads local commits to the remote `main` branch.

## (b) Understanding .gitignore

The `.gitignore` file specifies files and folders that Git should not track.

For example:

```gitignore
node_modules/
.env
.DS_Store
```

### Why Is node_modules Ignored?

The `node_modules` folder contains installed packages. It can be recreated using `npm install`, so it is generally unnecessary to upload this folder to GitHub.

The `.env` file may contain private configuration values and secrets. It should not be committed to a public repository.

## (c) Commit, Branch, Push, Pull, and Clone

### Commit

A commit records a snapshot of staged changes.

```bash
git commit -m "Update project"
```

### Branch

A branch allows developers to work on changes separately from the main branch.

```bash
git branch feature
git switch feature
```

### Push

Push uploads local commits to a remote repository.

```bash
git push origin main
```

### Pull

Pull downloads and integrates changes from a remote branch.

```bash
git pull origin main
```

### Clone

Clone creates a local copy of a remote repository.

```bash
git clone YOUR_REPOSITORY_URL
```

Replace `YOUR_REPOSITORY_URL` with the actual repository URL.

## (d) Troubleshooting a Rejected Push

A push may be rejected when the remote repository contains commits that are missing from the local branch.

### Safe Troubleshooting Steps

**Step 1: Check the Current Status**

```bash
git status
```

**Step 2: Pull Remote Changes**

```bash
git pull --rebase origin main
```

This attempts to replay local commits on top of the latest remote commits.

**Step 3: Resolve Conflicts if Necessary**

If Git reports conflicts:

1. Open the files identified by Git.
2. Review the conflicting changes.
3. Edit the files to keep the correct content.
4. Stage the resolved files:

```bash
git add .
```

5. Continue the rebase:

```bash
git rebase --continue
```

If you are unsure how to resolve a conflict, stop and ask for help before continuing.

**Step 4: Push Again**

```bash
git push origin main
```

### Important Safety Note

Do not use `git push --force` as a routine solution. It can overwrite remote branch history. Pulling and integrating remote changes is generally safer.

## Conclusion

Git and GitHub help developers track changes, collaborate, maintain project history, and share their work. Commands such as `git add`, `git commit`, `git push`, `git pull`, and `git clone` are essential for an effective development workflow.
