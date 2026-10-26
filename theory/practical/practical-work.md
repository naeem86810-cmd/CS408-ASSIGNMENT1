# Practical Work: Development Environment and Git/GitHub

## 1. Introduction

This practical work demonstrates the setup of a basic Node.js project, execution of a JavaScript program, and management of project files using Git and GitHub.

## 2. Software and Tools

The following tools are used:

* Visual Studio Code
* Node.js
* npm
* Git
* GitHub

## 3. Check Node.js and npm

Open the terminal in Visual Studio Code and run:

```bash
node -v
npm -v
```

These commands display the installed versions of Node.js and npm.

## 4. Initialize the Project

Run the following command inside the project directory:

```bash
npm init -y
```

This command creates a default `package.json` file containing project information and configuration.

## 5. Create the JavaScript Program

Create a file named `app.js` in the root directory.

Add the following code:

```javascript
const student = "CS-408 Student";

console.log("Welcome to Node.js!");
console.log("Course:", student);
console.log("Project is running successfully.");
```

## 6. Execute the Program

Run the following command:

```bash
node app.js
```

### Expected Output

```text
Welcome to Node.js!
Course: CS-408 Student
Project is running successfully.
```

The program uses `console.log()` to display messages in the terminal.

## 7. Git Commands

The following commands are useful for managing project changes.

### Check Repository Status

```bash
git status
```

Displays the current status of tracked and untracked files.

### Stage Changes

```bash
git add .
```

Stages changes for the next commit, except files excluded by Git rules.

### Commit Changes

```bash
git commit -m "Update assignment files"
```

Records staged changes in the local Git history.

### View Commit History

```bash
git log --oneline
```

Displays a concise history of commits.

## 8. GitHub Repository

GitHub hosts the project repository online.

The general workflow is:

1. Create or open the GitHub repository.
2. Connect the local repository to GitHub if it is not already connected.
3. Stage and commit the required changes.
4. Push the commits to GitHub.

To check the configured remote:

```bash
git remote -v
```

If the remote is already configured correctly, upload your latest commit with:

```bash
git push
```

## 9. The .gitignore File

The `.gitignore` file specifies untracked files and directories that Git should ignore.

Example:

```gitignore
node_modules/
.env
```

The `node_modules/` directory contains installed packages, while `.env` files may contain sensitive configuration information.

## 10. Conclusion

This practical work demonstrates how to initialize a Node.js project, execute a JavaScript program, and use Git commands to manage project changes. GitHub provides online hosting for the repository and makes it easier to share and review the completed assignment.
