# CS408 — Advanced Web Development

## Assignment 1: Development Tools, Git, GitHub, and Node.js

---

## Student Information

| Field           | Details                                                   |
| --------------- | --------------------------------------------------------- |
| Course Code     | CS408                                                     |
| Course Title    | Advanced Web Development                                  |
| Assignment      | Assignment 1                                              |
| Submitted To    | Mam Tasmiya                                               |
| Student Names   | Tehreem Fayaz (016), Gule Sandal (017), Saira Akram (018) |
| Submission Date | 25 October 2026                                           |

---

# Table of Contents

1. [Introduction](#1-introduction)
2. [Objectives](#2-objectives)
3. [Question 1: Development Tools and Node.js](#3-question-1-development-tools-and-nodejs)
4. [Question 2: Git and GitHub](#4-question-2-git-and-github)
5. [Practical Work](#5-practical-work)
6. [Project Setup and Execution](#6-project-setup-and-execution)
7. [Git Workflow](#7-git-workflow)
8. [Common Git Problems and Solutions](#8-common-git-problems-and-solutions)
9. [Conclusion](#9-conclusion)

---

# 1. Introduction

Advanced Web Development involves creating, testing, managing, and deploying web applications. Developers use different tools and technologies to make the development process easier and more efficient.

This assignment introduces important web development tools, Node.js, npm, Git, and GitHub. It also demonstrates practical commands used to create a Node.js project, manage project files, track changes, and upload work to a GitHub repository.

The assignment combines theoretical concepts and practical implementation in one GitHub repository.

# 2. Objectives

The main objectives of this assignment are:

* To understand commonly used web development tools.
* To understand Node.js and npm.
* To learn the purpose of `package.json` and `package-lock.json`.
* To understand browser Developer Tools.
* To learn Git version control.
* To understand the difference between Git and GitHub.
* To create and manage a project repository.
* To practice essential Git commands.
* To upload and maintain project files on GitHub.
* To organize theory and practical work in a single repository.

# 3. Question 1: Development Tools and Node.js

## 3.1 What Are Web Development Tools?

Web development tools are software applications and utilities that help developers write, test, debug, and manage websites and web applications.

These tools make development easier by providing features such as code editing, error detection, debugging, package management, and version control.

### Common Web Development Tools

**1. Visual Studio Code**

Visual Studio Code (VS Code) is a source-code editor used to write and manage code. It supports many programming languages, including HTML, CSS, JavaScript, and TypeScript.

Important features include:

* Syntax highlighting
* Code completion
* Integrated terminal
* Extensions
* Debugging support
* Git integration

**2. Web Browsers**

Browsers such as Google Chrome, Microsoft Edge, and Mozilla Firefox are used to open and test websites.

They also provide Developer Tools for inspecting HTML, CSS, JavaScript, and network requests.

**3. Node.js**

Node.js is a JavaScript runtime environment that allows JavaScript code to run outside a web browser. It is commonly used for backend development and server-side applications.

**4. npm**

npm stands for Node Package Manager. It helps developers install, update, and manage JavaScript packages and project dependencies.

**5. Git**

Git is a distributed version control system used to track changes in source code. It allows developers to maintain project history and work on different versions of a project.

**6. GitHub**

GitHub is an online platform for hosting Git repositories. It enables developers to share code, collaborate, review changes, and manage projects.

## 3.2 What Is Node.js?

Node.js is an open-source, cross-platform JavaScript runtime environment. It uses the V8 JavaScript engine to execute JavaScript outside the browser.

Traditionally, JavaScript was mainly used in web browsers to make web pages interactive. Node.js allows developers to use JavaScript for server-side programming as well.

### Uses of Node.js

* Building web servers
* Developing REST APIs
* Creating backend applications
* Reading and writing files
* Connecting applications to databases
* Building real-time applications
* Developing command-line tools

### Advantages of Node.js

* It allows JavaScript to run outside the browser.
* It supports asynchronous, non-blocking input/output.
* It has a large package ecosystem.
* It can be used for both frontend and backend development.
* It works on Windows, macOS, and Linux.

### Checking Node.js and npm Versions

Run these commands in the VS Code terminal:

```bash
node --version
npm --version
```

If both commands display version numbers, Node.js and npm are available in the terminal.

## 3.3 What Is npm?

npm stands for Node Package Manager. It is used to install and manage packages required by a JavaScript project.

A package is reusable code that provides particular functionality.

For example, a developer can install a package for handling HTTP requests, validating data, or creating a web server.

### Important npm Commands

```bash
npm init -y
```

Creates a default `package.json` file.

```bash
npm install
```

Installs the dependencies specified in the project configuration when the required package information is available.

```bash
npm install express
```

Installs Express as a project dependency.

```bash
npm install --save-dev nodemon
```

Installs Nodemon as a development dependency.

```bash
npm uninstall express
```

Removes Express from the project dependencies.

## 3.4 What Is package.json?

`package.json` is an important configuration file in a Node.js project. It stores project information and defines scripts, dependencies, and other configuration details.

### Example

```json
{
  "name": "cs408-assignment-1",
  "version": "1.0.0",
  "description": "CS408 Advanced Web Development Assignment 1",
  "main": "app.js",
  "scripts": {
    "start": "node app.js"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}
```

### Important Fields

* **name:** The name of the project.
* **version:** The current version of the project.
* **description:** A short explanation of the project.
* **main:** The main entry file.
* **scripts:** Commands that can be executed using npm.
* **dependencies:** Packages required by the application.
* **devDependencies:** Packages mainly required during development.
* **license:** Information about the project's license.

The exact fields in `package.json` depend on how the project is created and configured.

## 3.5 What Is package-lock.json?

`package-lock.json` records the specific versions of installed packages and their dependency information.

It helps npm reproduce a consistent dependency installation across different computers.

### Difference Between package.json and package-lock.json

| package.json                             | package-lock.json                               |
| ---------------------------------------- | ----------------------------------------------- |
| Contains project configuration.          | Records the resolved dependency tree.           |
| Defines dependency requirements.         | Records specific installed package versions.    |
| Can contain scripts and project details. | Focuses on dependency installation information. |
| Is edited by developers and npm.         | Is generally generated and updated by npm.      |

Both files are important in a Node.js project when the project uses npm-managed dependencies.

## 3.6 What Are Browser Developer Tools?

Browser Developer Tools are built-in utilities used to inspect, test, and debug websites.

They are available in browsers such as Google Chrome and Microsoft Edge.

To open Developer Tools, press:

```text
F12
```

You can also right-click a web page and select **Inspect**.

### Main Panels

**1. Elements**

Displays the page's HTML structure and allows developers to inspect and temporarily modify HTML and CSS.

**2. Console**

Displays JavaScript errors, warnings, and messages. Developers can also execute JavaScript commands.

**3. Network**

Shows requests made by the browser, including resources, API calls, status codes, and loading times.

**4. Sources**

Helps developers inspect source files and debug JavaScript using breakpoints.

**5. Application**

Displays information such as local storage, session storage, cookies, and service workers.

**6. Performance**

Helps identify performance problems and analyze how a web page behaves while running.

### Benefits of Developer Tools

* Finding JavaScript errors
* Inspecting HTML and CSS
* Debugging website behavior
* Monitoring network requests
* Checking browser storage
* Improving website performance

# 4. Question 2: Git and GitHub

## 4.1 What Is Version Control?

Version control is a system for tracking changes made to files over time.

It allows developers to review previous changes, restore earlier versions, and collaborate with other developers.

Without version control, managing multiple versions of a project manually can become difficult.

## 4.2 What Is Git?

Git is a distributed version control system. It records changes to project files and maintains a history of those changes.

Git allows developers to work locally, create branches, compare changes, and combine work from different contributors.

### Advantages of Git

* Tracks file changes.
* Maintains project history.
* Supports branches.
* Helps teams collaborate.
* Allows previous versions to be recovered.
* Works without a constant internet connection for local operations.

## 4.3 What Is GitHub?

GitHub is an online platform that hosts Git repositories.

It allows developers to upload their projects, share repositories, review code, and collaborate with other people.

### Difference Between Git and GitHub

| Git                                            | GitHub                                               |
| ---------------------------------------------- | ---------------------------------------------------- |
| A version control system.                      | An online repository hosting platform.               |
| Runs on a local computer.                      | Provides online access to repositories.              |
| Tracks changes and commits.                    | Hosts repositories and supports collaboration.       |
| Can work offline for local operations.         | Requires an internet connection for online features. |
| Is used through commands and compatible tools. | Provides a website and collaboration features.       |

Git and GitHub are related, but they are not the same thing.

## 4.4 What Is a Repository?

A repository, or repo, is a location where a project's files and version history are stored.

A Git repository includes the project files and the history maintained by Git.

Repositories can be local or hosted remotely, such as on GitHub.

## 4.5 Important Git Commands

### Check Git Version

```bash
git --version
```

Displays the installed Git version.

### Initialize a Repository

```bash
git init
```

Creates a new Git repository in the current directory if one does not already exist.

### Check File Status

```bash
git status
```

Shows modified, untracked, and staged files.

### Add Files to the Staging Area

```bash
git add .
```

Stages eligible changes in the current directory and its subdirectories.

### Create a Commit

```bash
git commit -m "Add assignment files"
```

Records the staged changes in the repository history.

### View Commit History

```bash
git log --oneline
```

Displays a compact history of commits.

### View the Remote Repository

```bash
git remote -v
```

Displays configured remote repository URLs.

### Upload Changes

```bash
git push
```

Uploads local commits to the configured remote branch when the repository is correctly configured.

### Download Remote Changes

```bash
git pull
```

Fetches and integrates changes from the remote repository into the current branch.

## 4.6 What Is a Commit?

A commit is a recorded snapshot of staged changes in a Git repository.

Each commit has a unique identifier and a message describing the changes.

Example:

```bash
git add .
git commit -m "Complete assignment documentation"
```

A useful commit message should briefly explain what changed.

## 4.7 What Is a Branch?

A branch is an independent line of development within a Git repository.

Branches allow developers to work on new features or changes without directly modifying another branch's work.

For example:

```bash
git branch
```

Displays the local branches.

```bash
git switch -c new-feature
```

Creates and switches to a new branch named `new-feature`.

## 4.8 What Is .gitignore?

`.gitignore` is a text file that tells Git which untracked files or directories to ignore.

It is commonly used for temporary files, logs, local environment files, and installed dependencies.

### Example

```gitignore
node_modules/
.env
*.log
.DS_Store
```

Important: `.gitignore` does not automatically remove files that Git is already tracking. Also, sensitive information such as passwords and API keys should never be committed to a public repository.

# 5. Practical Work

## 5.1 Project Setup

The project was created and managed using Node.js, npm, VS Code, Git, and GitHub.

### Step 1: Open the Project Folder

Open the assignment folder in Visual Studio Code.

### Step 2: Open the Integrated Terminal

Select **Terminal → New Terminal**.

### Step 3: Check the Installed Tools

```bash
node --version
npm --version
git --version
```

### Step 4: Initialize the npm Project

```bash
npm init -y
```

This creates the default `package.json` file if it does not already exist.

## 5.2 Creating a JavaScript File

Create a file named `app.js` in the project root.

Add the following code:

```javascript
console.log("CS408 Advanced Web Development Assignment 1");
console.log("Node.js is working successfully!");
```

### Running the JavaScript File

In the VS Code terminal, execute:

```bash
node app.js
```

### Expected Output

```text
CS408 Advanced Web Development Assignment 1
Node.js is working successfully!
```

This practical example demonstrates how Node.js executes a JavaScript file outside the browser.

## 5.3 Creating the Assignment Documentation

The assignment documentation can be organized using Markdown.

Markdown is a lightweight formatting language used to create headings, lists, tables, links, and code blocks.

Examples:

```markdown
# Main Heading

## Subheading

- First point
- Second point

**Bold text**

`inline code`
```

GitHub automatically renders Markdown files, making them easier to read.

## 5.4 Practical Git Workflow

The following commands demonstrate how to track and upload project changes:

```bash
git status
git add .
git commit -m "Add CS408 assignment work"
git push
```

These commands check the repository status, stage changes, create a commit, and push the commit to the configured remote repository.

If the project has not yet been connected to GitHub, the remote repository must be configured before pushing.

# 6. Project Setup and Execution

## 6.1 Requirements

The following tools are used for this assignment:

* Visual Studio Code
* Node.js
* npm
* Git
* A GitHub account
* An internet connection for GitHub operations

## 6.2 Verify the Project

Open the terminal in the project directory and run:

```bash
node --version
npm --version
git --version
```

To execute the example JavaScript file, run:

```bash
node app.js
```

To inspect the current Git status, run:

```bash
git status
```

If the project contains npm dependencies, use the appropriate npm installation command before running the application.

# 7. Git Workflow

The following workflow summarizes how changes are managed and uploaded to GitHub.

### Step 1: Check Changes

```bash
git status
```

### Step 2: Stage Changes

```bash
git add .
```

### Step 3: Commit Changes

```bash
git commit -m "Update assignment files"
```

### Step 4: Push to GitHub

```bash
git push
```

### Step 5: Verify the Repository

Open the GitHub repository in a browser and refresh the page. Confirm that the latest files and README content are visible.

Repository:

**[CS408 Assignment 1 — GitHub Repository](https://github.com/naeem86810-cmd/CS408-ASSIGNMENT1)**

# 8. Common Git Problems and Solutions

## Problem 1: Changes Are Not Visible on GitHub

**Possible cause:** The changes were saved locally but not committed or pushed.

**Solution:**

```bash
git status
git add .
git commit -m "Update assignment"
git push
```

If there are no new changes to commit, check whether the correct folder and repository are open.

## Problem 2: Git Says There Is Nothing to Commit

**Possible cause:** All changes have already been committed, or the file was not modified or saved.

**Solution:** Save the file and check:

```bash
git status
```

If the working tree is clean, inspect the latest commit and confirm that the correct branch is selected.

## Problem 3: Push Is Rejected

**Possible cause:** The remote branch may contain commits that are missing locally, or the current branch may not have an upstream branch configured.

**Solution:** Read the exact Git error message before changing the repository. If the remote contains new commits, fetch or pull and reconcile the changes before trying again. Avoid using `git push --force` as a routine fix.

## Problem 4: Git Is Not Recognized

**Possible cause:** Git is not installed, or the terminal cannot find its executable.

**Solution:** Verify the installation and reopen VS Code after installation. Then run:

```bash
git --version
```

# 9. Conclusion

This assignment introduced essential tools and concepts used in modern web development. It explained Node.js, npm, project configuration files, browser Developer Tools, Git, GitHub, repositories, commits, branches, and `.gitignore`.

The practical section demonstrated how to execute a JavaScript file using Node.js, organize assignment documentation using Markdown, and use Git commands to manage and upload project changes.

Keeping the theoretical and practical work in one repository makes the assignment easier to review, maintain, and share.

---

**End of Assignment 1**
