# CS-408: Advanced Web Development

## Assignment 1 — Development Environment and Git/GitHub Workflow

---

## Student Information

| Field             | Details                                                   |
| ----------------- | --------------------------------------------------------- |
| Course Code       | CS-408                                                    |
| Course Title      | Advanced Web Development                                  |
| Assignment Number | 1                                                         |
| Submitted To      | Mam Tasmiya                                               |
| Student Names     | Tehreem Fayaz (016), Gule Sandal (017), Saira Akram (018) |
| Submission Date   | 25 October 2026                                           |

---

# Table of Contents

* [Introduction](#introduction)
* [Question 1: Development Environment](#question-1-design-set-up-and-justify-a-development-environment)

  * [1(a) Essential Development Tools](#1a-select-and-justify-the-essential-development-tools)
  * [1(b) Package Management](#1b-packagejson-dependencies-and-lockfile)
  * [1(c) Node.js Project Setup](#1c-create-and-run-a-basic-nodejs-project)
  * [1(d) Browser Troubleshooting](#1d-troubleshooting-incorrect-output-and-failed-image-requests)
* [Question 2: Git/GitHub Workflow](#question-2-gitgithub-workflow-and-troubleshooting)

  * [2(a) Commands and Remote Setup](#2a-check-stage-commit-connect-and-push)
  * [2(b) node_modules and .gitignore](#2b-excluding-node_modules-and-managing-dependencies)
  * [2(c) Git Concepts and Collaboration](#2c-commit-branch-push-pull-and-clone)
  * [2(d) Troubleshooting a Rejected Push](#2d-safely-troubleshooting-a-rejected-push)
* [Practical Implementation](#practical-implementation)
* [Project Structure](#project-structure)
* [Screenshots Required](#screenshots-required)
* [Conclusion](#conclusion)

---

# Introduction

Modern web development requires a consistent development environment, effective debugging tools, reliable package management, and a safe version-control workflow. When several team members use different computers, differences in installed packages, formatting rules, and development tools can create problems.

This assignment presents a practical plan for setting up a JavaScript development environment and managing a Node.js project using Git and GitHub. It explains the purpose of essential development tools, package management, browser debugging, Git commands, repository collaboration, and safe troubleshooting.

The recommended approach is to use consistent project configuration, record dependency versions, exclude unnecessary generated files, and maintain a clear history of changes. These decisions help team members reproduce the project environment and collaborate with less risk.

# Question 1: Design, Set Up, and Justify a Development Environment

## 1(a) Select and Justify the Essential Development Tools

A student team needs tools for writing code, running JavaScript, maintaining consistent formatting, managing packages, and identifying browser errors. The following tools address these requirements.

### 1. Visual Studio Code

Visual Studio Code (VS Code) is a source-code editor used to create and maintain project files.

**Purpose:**

* Write and edit JavaScript, HTML, CSS, and configuration files.
* Organize files into folders.
* Use an integrated terminal to run commands.
* Inspect Git changes and manage source code.
* Debug supported applications using extensions and built-in features.

**Justification:**

VS Code is suitable for a student team because it is lightweight, supports JavaScript development, and provides an integrated terminal. Team members can use the same editor settings and recommended extensions to reduce differences in their development environments.

### 2. VS Code Extensions

Extensions add features to VS Code. The team should choose a small, consistent set of extensions rather than installing unnecessary tools.

| Extension or Tool                                            | Purpose                                                              | Reason for Selection                                 |
| ------------------------------------------------------------ | -------------------------------------------------------------------- | ---------------------------------------------------- |
| ESLint                                                       | Identifies JavaScript problems and applies configured linting rules. | Helps detect common coding mistakes.                 |
| Prettier                                                     | Formats code consistently.                                           | Reduces formatting differences between team members. |
| JavaScript debugger or built-in JavaScript debugging support | Helps inspect execution and debug supported applications.            | Makes errors easier to investigate.                  |
| React Developer Tools browser extension                      | Inspects React components and their props and state.                 | Useful if the application uses React.                |

The team should share relevant configuration files, such as ESLint and Prettier configuration, through Git. This is more reliable than asking each member to select formatting rules independently.

**Important distinction:** ESLint checks code against configured rules, while Prettier focuses primarily on code formatting. They serve related but different purposes.

### 3. Node.js

Node.js is a JavaScript runtime environment that allows JavaScript to execute outside a web browser.

**Purpose:**

* Run JavaScript files from the terminal.
* Build backend applications and web servers.
* Develop APIs.
* Execute project scripts.
* Support JavaScript development tools.

**Justification:**

Node.js allows all team members to execute the same project using a JavaScript runtime. The team should agree on a supported Node.js version and document it so that differences between installed versions are less likely to cause problems.

Check the installed version with:

```bash
node --version
```

### 4. Package Manager: npm

npm stands for Node Package Manager. It is commonly installed with Node.js and manages packages required by JavaScript projects.

**Purpose:**

* Install project dependencies.
* Remove or update packages.
* Manage dependency versions through project files.
* Run commands defined in `package.json`.

**Justification:**

Using npm provides a consistent way to install dependencies instead of asking each team member to download and configure packages manually. A shared `package.json` and lockfile help team members install the intended dependency versions.

Check the installed npm version:

```bash
npm --version
```

### 5. Browser Developer Tools

Browser Developer Tools are built-in browser utilities available in browsers such as Google Chrome and Microsoft Edge.

Open them by pressing `F12` or right-clicking a webpage and selecting **Inspect**.

Their main panels include:

* **Elements:** Inspects HTML and CSS.
* **Console:** Displays JavaScript errors, warnings, and messages.
* **Network:** Shows network requests and their responses.
* **Sources:** Helps inspect source files and debug JavaScript.
* **Application:** Inspects browser storage, cookies, and related application data.
* **Performance:** Helps investigate performance problems.

**Justification:**

A website can load successfully while still displaying incorrect information or failing to load certain resources. Developer Tools help identify whether a problem originates from JavaScript, HTML/CSS, a network request, or another browser-related issue.

### 6. React Developer Tools

React Developer Tools is a browser extension used to inspect applications built with React.

It provides a component-inspection interface and can show component hierarchy, props, and state. Its available features depend on the React application and the installed version of the extension.

**Justification:**

If the team develops a React application, this extension helps trace which component is responsible for incorrect output. For example, if a component displays the wrong text, the developer can inspect its props and state to determine whether the incorrect value is being passed to it.

**Important:** React Developer Tools is optional for a plain JavaScript application. It is useful when React is actually part of the project, rather than being a requirement for every website.

### Recommended Team Setup

To make the environment more consistent, the team should:

1. Agree on a supported Node.js version.
2. Use the same package manager.
3. Share project configuration files through Git.
4. Configure a common code formatter and linter.
5. Keep dependency information in `package.json` and the lockfile.
6. Use browser Developer Tools for debugging.
7. Install React Developer Tools only if the application uses React.

This approach reduces differences between computers and makes problems easier to reproduce.

---

## 1(b) package.json, Dependencies, Development Dependencies, and Lockfile

A Node.js project often relies on packages written by other developers. Package management records which packages the project needs and helps other team members install them.

### What Is package.json?

`package.json` is a configuration file that stores project information, scripts, and dependency requirements.

Example:

```json
{
  "name": "cs408-assignment-1",
  "version": "1.0.0",
  "description": "CS-408 Advanced Web Development Assignment 1",
  "main": "app.js",
  "scripts": {
    "start": "node app.js"
  },
  "dependencies": {},
  "devDependencies": {}
}
```

**Important fields:**

* `name`: The project name.
* `version`: The project version.
* `description`: A brief description of the project.
* `main`: The main entry file for the package.
* `scripts`: Commands that can be run using npm.
* `dependencies`: Packages needed to run the application.
* `devDependencies`: Packages primarily needed during development.

The fields shown above are an example. A real project may contain additional configuration.

### What Are Dependencies?

Dependencies are packages that an application needs to function at runtime.

For example, an Express-based web server uses Express to handle HTTP requests.

Install Express with:

```bash
npm install express
```

npm records Express under `dependencies` in `package.json`.

### What Are Development Dependencies?

Development dependencies are packages used mainly while writing, testing, formatting, or building the application.

For example, Prettier formats code, while ESLint checks it against configured coding rules.

Install them with:

```bash
npm install --save-dev prettier eslint
```

npm records these packages under `devDependencies`.

### Runtime Dependency vs. Development Dependency

| Runtime Dependency                                | Development Dependency                                                                             |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------- |
| Required by the application while it runs.        | Primarily used during development or testing.                                                      |
| Example: Express in an Express server.            | Example: Prettier for code formatting.                                                             |
| Installed when runtime dependencies are required. | May be omitted from a production-only installation if the application does not need it at runtime. |

**Example scenario:**

Suppose the team creates a Node.js web server using Express and uses Prettier to format JavaScript files.

Express is a runtime dependency because the server needs it to handle requests. Prettier is a development dependency because it formats the source code before execution; the deployed server does not need Prettier to handle requests.

This distinction avoids treating every development tool as part of the application's runtime requirements.

### What Is a Lockfile?

For npm projects, the lockfile is normally named `package-lock.json`.

It records the resolved versions of installed packages and dependency information. It helps npm install a consistent dependency tree on different computers.

When a team member installs the project dependencies, the lockfile helps reproduce the versions selected for the project.

For example:

```bash
npm ci
```

This command installs dependencies from the existing npm lockfile and is useful for reproducible installations in automated environments or when setting up a clean working copy. It expects a compatible lockfile and `package.json`.

If the project has no lockfile yet, an initial installation can be performed with:

```bash
npm install
```

This can create or update `package-lock.json`.

### How These Files Work Together

| File or Section     | Main Role                                                         |
| ------------------- | ----------------------------------------------------------------- |
| `package.json`      | Defines project metadata, scripts, and dependency requirements.   |
| `dependencies`      | Lists packages needed by the application at runtime.              |
| `devDependencies`   | Lists packages mainly used during development.                    |
| `package-lock.json` | Records resolved dependency versions and dependency-tree details. |

Together, these files make project setup easier and reduce inconsistencies between team members' computers.

---

## 1(c) Create and Run a Basic Node.js Project

The following steps demonstrate how to create a small Node.js project and verify that it runs.

### Step 1: Install and Verify Node.js

Install a supported Node.js release if it is not already available. Then open the VS Code terminal and run:

```bash
node --version
npm --version
```

**Reason:** These commands verify that the Node.js runtime and npm are available. If the commands are not recognized, check the installation and terminal environment.

### Step 2: Create a Project Folder

In the terminal, run:

```bash
mkdir node-demo
cd node-demo
```

**Reason:** A separate project directory keeps the application's files organized.

If a suitable project folder already exists, use that folder instead.

### Step 3: Initialize the npm Project

Run:

```bash
npm init -y
```

**Reason:** This command creates a default `package.json` file so npm can manage the project.

### Step 4: Create app.js

Create a file named `app.js` in the project directory.

Add the following JavaScript code:

```javascript
console.log("CS-408 Advanced Web Development");
console.log("Node.js project is running successfully!");
```

**Reason:** `console.log()` prints messages to the terminal, making it a simple way to verify JavaScript execution.

### Step 5: Add a Start Script

Open `package.json` and ensure that it contains a `scripts` section similar to the following:

```json
"scripts": {
  "start": "node app.js"
}
```

Add the section inside the main JSON object. If a `scripts` section already exists, update it rather than creating a duplicate.

**Reason:** The start script provides a standard command for running the application.

### Step 6: Run the JavaScript File

Execute:

```bash
node app.js
```

Expected output:

```text
CS-408 Advanced Web Development
Node.js project is running successfully!
```

### Step 7: Run Through npm

Execute:

```bash
npm start
```

The same messages should appear.

**Reason:** Running `node app.js` verifies direct execution, while `npm start` verifies that the configured start script works.

### Step 8: Check the Project Files

The basic project should contain:

```text
node-demo/
├── app.js
└── package.json
```

Depending on the installation and configuration, the directory may also contain `package-lock.json` and other files.

### Verification

The project can be considered successfully executed when:

* Node.js and npm commands work.
* `app.js` executes without errors.
* The expected messages appear.
* `npm start` runs the configured script.

These steps provide a minimal, repeatable setup that can be extended into a larger application.

---

## 1(d) Troubleshooting Incorrect Output and Failed Image Requests

Consider a webpage that loads, but displays incorrect output and fails to load an image. These problems should be investigated separately because they may have different causes.

### Problem 1: The Webpage Displays Incorrect Output

**First panel: Console**

The Console displays JavaScript errors, warnings, and developer messages.

Evidence may include:

* `ReferenceError`, indicating that a variable or function is unavailable.
* `TypeError`, indicating an invalid operation on a value.
* Messages showing unexpected values.
* Failed script loading messages.

**Reasoning:** If the webpage displays the wrong result, a JavaScript error or incorrect data may be responsible. Console messages can reveal where execution failed.

**Second panel: Elements**

The Elements panel shows the live HTML structure and applied CSS.

Evidence may include:

* An unexpected text element.
* Incorrect HTML nesting.
* A class or ID that does not match the intended element.
* CSS rules that hide, move, or change the appearance of content.

**Reasoning:** If the expected data exists but appears in the wrong place or is styled incorrectly, inspecting the live DOM and CSS helps identify the problem.

**Third panel: Sources**

The Sources panel allows developers to inspect source files, set breakpoints, and step through supported JavaScript execution.

Evidence may include:

* A variable containing an unexpected value.
* A function receiving incorrect input.
* A conditional statement taking the wrong branch.
* A line where execution fails or behaves unexpectedly.

**Reasoning:** Breakpoints help trace how the program reaches the incorrect result rather than relying only on the final displayed output.

### Problem 2: An Image Request Fails

**First panel: Network**

The Network panel is the main place to investigate a failed image request.

Select the image resource and inspect its URL, status code, request details, response headers, and timing.

Possible evidence includes:

| Evidence                                    | Possible Meaning                                                           |
| ------------------------------------------- | -------------------------------------------------------------------------- |
| `404 Not Found`                             | The requested image was not found at that URL.                             |
| `403 Forbidden`                             | Access to the image may be denied.                                         |
| `500`-series status                         | The server may have encountered an error.                                  |
| Failed request with no normal HTTP response | A network, browser, DNS, or other request-level problem may have occurred. |
| Unexpected response content type            | The server may be returning something other than an image.                 |

A `200 OK` response does not necessarily guarantee that the browser can display the resource correctly. The response content and browser messages should also be inspected.

**Reasoning:** The Network panel provides direct evidence about whether the image request was sent successfully and what response was received.

**Second panel: Console**

The Console may report:

* A failed resource request.
* A Content Security Policy restriction.
* A mixed-content warning or block.
* A cross-origin issue where applicable.

**Reasoning:** The Console helps identify browser security restrictions and other errors that are not obvious from the page itself.

### Recommended Troubleshooting Process

1. Open Developer Tools using `F12`.
2. Open the Console and record relevant errors.
3. Open Network and reload the page.
4. Filter the requests to locate the image.
5. Inspect the request URL and status.
6. Check the image path in the HTML or JavaScript.
7. Use Elements to inspect the rendered page.
8. Use Sources to debug JavaScript if the incorrect output is caused by application logic.
9. Correct the underlying problem and reload the page to verify the result.

This process uses evidence from several panels rather than assuming that every visual problem is caused by JavaScript.

---

# Question 2: Git/GitHub Workflow and Troubleshooting

## 2(a) Check, Stage, Commit, Connect, and Push

Assume that a Node.js project already contains `app.js` and `package.json`, Git has been initialized, and an initial commit has been made.

The following workflow shows how to check changes, stage and commit them, connect to GitHub, and publish the `main` branch.

### Step 1: Check Repository Status

```bash
git status
```

**Purpose:** Shows the current branch and identifies modified, staged, and untracked files.

**Reasoning:** Checking status first helps the developer understand which changes will be included in the next commit.

### Step 2: Stage Changes

```bash
git add .
```

**Purpose:** Stages eligible changes in the current directory and its subdirectories.

**Reasoning:** Git commits staged changes. Reviewing `git status` before committing helps avoid including unintended files.

### Step 3: Commit Changes

```bash
git commit -m "Add project updates"
```

**Purpose:** Records the staged changes as a commit in the local repository.

**Reasoning:** A commit creates a checkpoint that can be reviewed later. Meaningful messages help team members understand the project history.

If Git reports that there is nothing to commit, check whether the files have been saved and whether any new changes exist.

### Step 4: Connect the Local Repository to GitHub

Create an empty repository on GitHub, then connect it using the repository URL.

Replace the placeholder with the actual URL of the repository:

```bash
git remote add origin <REPOSITORY_URL>
```

**Purpose:** Configures a remote named `origin` for the GitHub repository.

**Reasoning:** The remote tells Git where the local repository should send and receive changes.

Check the configured remote:

```bash
git remote -v
```

If `origin` already exists, inspect its URL rather than adding the same remote again.

### Step 5: Ensure the Branch Is Named main

```bash
git branch -M main
```

**Purpose:** Renames the current branch to `main`.

**Reasoning:** Using a consistent branch name helps align the local workflow with the expected remote branch. Confirm that the current branch is the one you intend to publish.

### Step 6: Push the Main Branch

```bash
git push -u origin main
```

**Purpose:** Uploads the local `main` branch to the remote repository and sets its upstream tracking relationship.

**Reasoning:** The upstream relationship makes subsequent pushes and pulls simpler.

**Important:** This is suitable when the local and remote histories can be pushed safely. If Git rejects the push because the remote contains commits not present locally, follow the troubleshooting process in Question 2(d). Do not try to overwrite the remote history blindly.

---

## 2(b) Excluding node_modules and Managing Dependencies

### What Is node_modules?

`node_modules` is the directory where npm normally installs a project's dependencies.

It may contain thousands of files, including packages and their own dependencies. The directory can become very large.

### Why Should node_modules Normally Be Excluded?

The directory should normally be excluded from Git because:

1. It can significantly increase repository size.
2. Its contents can be recreated by installing the project's dependencies.
3. It may contain platform-specific or generated files.
4. Tracking all installed package files creates unnecessary repository changes.
5. Sharing dependency configuration is generally more maintainable than committing the entire installed directory.

### .gitignore Entry

Create a file named `.gitignore` in the project root and add:

```gitignore
node_modules/
.env
*.log
```

**Explanation:**

* `node_modules/` ignores the installed dependency directory.
* `.env` ignores a common local environment configuration file.
* `*.log` ignores files ending in `.log`.

A `.gitignore` file helps prevent accidental tracking of unwanted files, but it does not automatically remove files that Git already tracks.

Credentials, passwords, tokens, and API keys must never be committed. If a secret has already been exposed, removing it from a later commit may not remove it from the repository's history; the credential should be revoked or rotated as appropriate.

### How package.json and package-lock.json Help

When another developer clones the repository, they should use the project's package configuration to install its dependencies.

For an npm project with a compatible `package-lock.json`, run:

```bash
npm ci
```

This installs the dependency versions recorded in the lockfile and is useful for clean, reproducible installations.

If a lockfile does not yet exist, the project may require an initial installation using:

```bash
npm install
```

This can create or update the lockfile.

**Role of each file:**

* `package.json` declares the project's dependency requirements and scripts.
* `package-lock.json` records the resolved dependency versions and dependency-tree information.
* `node_modules/` contains the locally installed packages and can be recreated.

This arrangement reduces repository size and helps different developers install a consistent set of dependencies.

---

## 2(c) Commit, Branch, Push, Pull, and Clone

These Git terms describe different parts of version control and collaboration.

### Commit

A commit is a saved snapshot of staged changes in the repository history.

Example:

```bash
git add app.js
git commit -m "Fix application output"
```

A commit creates a checkpoint that can be inspected or compared with other commits.

### Branch

A branch is a separate line of development. It allows a developer to make changes without immediately modifying another branch's work.

Create a branch for a feature:

```bash
git switch -c teammate-feature
```

The branch can contain commits that are separate from the `main` branch until the work is reviewed and integrated.

### Push

Push uploads local commits to a remote repository.

```bash
git push
```

This updates the remote branch when the push is accepted.

### Pull

Pull fetches changes from a remote repository and integrates them into the current branch.

```bash
git pull
```

The integration may use a merge or another configured strategy. If changes conflict, Git may require the developer to resolve the conflicts.

### Clone

Clone creates a local copy of a remote repository, including its Git history.

```bash
git clone <REPOSITORY_URL>
```

The placeholder should be replaced with the actual repository URL.

Cloning is useful when a teammate needs to start working on a repository on another computer.

### Comparison

| Term   | Meaning                                      | Example Use                         |
| ------ | -------------------------------------------- | ----------------------------------- |
| Commit | Records staged changes locally.              | Save a completed code fix.          |
| Branch | Provides a separate line of development.     | Develop a new feature.              |
| Push   | Uploads local commits to a remote.           | Publish work on GitHub.             |
| Pull   | Fetches and integrates remote changes.       | Update the local branch.            |
| Clone  | Creates a local copy of a remote repository. | Set up a project on a new computer. |

### Applying These Concepts to the Team Scenario

Suppose one teammate is developing a feature while another is fixing a bug.

They can work on separate branches and create commits describing their changes. This keeps unfinished work separate from the main branch and makes it easier to review each contribution.

Before integrating the feature, the team can inspect the changes and resolve conflicts if the same lines of code were modified.

A typical workflow is:

```bash
git switch -c feature-update
git status
git add .
git commit -m "Implement feature update"
git push -u origin feature-update
```

The teammate can then open a pull request on GitHub for review and integration.

Branches and commits do not automatically eliminate every conflict, but they make changes easier to isolate, review, and recover.

---

## 2(d) Safely Troubleshooting a Rejected Push

### Scenario

A developer attempts to push local changes, but Git rejects the push because the remote branch contains commits that are missing from the local branch.

This may occur when another collaborator has pushed changes or when the remote repository was initialized with a README or other commit.

### Why Is the Push Rejected?

Git normally prevents a push that would discard commits from the remote branch through a non-fast-forward update.

The rejection protects existing remote work from being overwritten by a local branch that does not contain the remote history.

### Step 1: Inspect the Local Repository

Run:

```bash
git status
git branch --show-current
git remote -v
```

These commands show the working-tree status, current branch, and configured remote.

**Reasoning:** Confirming the current branch and remote avoids making changes to the wrong repository or branch.

### Step 2: Fetch Remote Changes

Run:

```bash
git fetch origin
```

**Purpose:** Downloads information about remote commits without automatically integrating them into the current branch.

**Reasoning:** Fetching allows the developer to inspect the remote changes before deciding how to integrate them.

### Step 3: Compare the Histories

For example, if the relevant remote branch is `main`, run:

```bash
git log --oneline --graph --decorate --all
```

This displays the commit history in a compact graph.

**Reasoning:** Reviewing the graph helps determine whether the remote contains new commits and whether the histories have diverged.

### Step 4: Integrate the Remote Changes

If the team uses a merge-based workflow, and the local branch is `main`, run:

```bash
git switch main
git merge origin/main
```

This merges the fetched remote branch into the local `main` branch.

If Git reports conflicts, open the affected files, examine both versions, and resolve the conflicts carefully. Then stage the resolved files and create a merge commit if Git requires one.

Another possible workflow is rebasing local commits on top of the updated remote branch. The team should follow its agreed workflow, particularly if commits have already been shared.

**Reasoning:** Integrating remote work preserves the other developer's changes and creates a history that contains both sets of work.

### Step 5: Push Again

After successfully integrating the remote changes and checking the result, run:

```bash
git push origin main
```

This should succeed if the local branch now contains the required remote history and no new conflicting update has occurred.

### Why Should Remote History Not Be Overwritten Blindly?

Using a force push without understanding the situation can replace the remote branch reference and make other collaborators' commits difficult to access through the normal branch history.

This may disrupt teammates, remove expected commits from the branch, and create unnecessary recovery work.

The safer approach is to inspect the remote history, integrate changes, resolve conflicts, and push only after confirming the result.

If a force push is ever genuinely required, it should follow an agreed team procedure and a careful review of the history. It should not be the default response to a rejected push.

---

# Practical Implementation

The following practical example demonstrates the basic Node.js and Git workflow.

## 1. JavaScript Example

Create or use `app.js`:

```javascript
console.log("CS-408 Advanced Web Development");
console.log("Assignment 1 practical work");
console.log("Node.js is running successfully!");
```

Run the file:

```bash
node app.js
```

Expected output:

```text
CS-408 Advanced Web Development
Assignment 1 practical work
Node.js is running successfully!
```

This confirms that Node.js can execute the JavaScript file and display its output.

## 2. Verify Project Configuration

Check the installed tools:

```bash
node --version
npm --version
git --version
```

Inspect the repository:

```bash
git status
git remote -v
git log --oneline
```

These commands help verify the development environment and Git repository configuration.

## 3. Example Git Workflow

After saving the project files:

```bash
git status
git add .
git commit -m "Update CS-408 assignment"
git push
```

Review the status before staging and committing. Ensure that credentials and unnecessary generated files are excluded.

If there are no new changes to commit, Git may report that the working tree is clean. In that case, there is no need to create an empty commit.

---

# Project Structure

A simple repository for this assignment may contain the following files:

```text
CS408-ASSIGNMENT1/
├── README.md
├── app.js
├── package.json
├── package-lock.json
├── .gitignore
├── theory/
│   ├── question-1.md
│   └── question-2.md
├── practical/
│   └── practical-work.md
└── screenshots/
    ├── project-structure.png
    └── commit-history.png
```

**Note:** This is a suggested structure, not a claim that every listed file already exists. Keep files that are actually present in the repository and create missing files only when needed.

The README provides the complete assignment report. The additional theory and practical files can be retained as supporting documents, provided their contents are consistent with the README.

---

# Screenshots Required

The assignment instructions specifically require screenshots of the project structure and commit history.

## Screenshot 1: Project Structure

Capture a screenshot in VS Code showing the project folder and its important files, including:

* `README.md`
* `app.js`
* `package.json`
* `.gitignore`
* Any relevant theory and practical files

Save the actual screenshot as:

`screenshots/project-structure.png`

## Screenshot 2: Commit History

Capture a screenshot showing the Git commit history.

One way to display it is to run this command in the VS Code terminal:

```bash
git log --oneline --graph --decorate -10
```

Make sure the terminal output is readable in the screenshot.

Save the actual screenshot as:

`screenshots/commit-history.png`

**Important:** These are the required screenshot filenames. The screenshots must be captured from your actual project; example text or empty placeholder image files do not count as evidence.

After saving the screenshots, add and push them to GitHub:

```bash
git add screenshots/
git commit -m "Add assignment evidence screenshots"
git push
```

If the screenshots are saved in another location, adjust the path accordingly.

---

# GitHub Repository

**Repository URL:** https://github.com/naeem86810-cmd/CS408-ASSIGNMENT1

The repository should contain the assignment report, relevant project files, and the required screenshots.

Before sharing the repository with the instructor:

1. Open the repository on GitHub.
2. Verify that the README displays correctly.
3. Confirm that the practical code and configuration files are present.
4. Confirm that the two actual screenshots are uploaded.
5. Check that no passwords, access tokens, API keys, or other confidential information are exposed.

---

# Conclusion

This assignment explained how to select and configure a consistent JavaScript development environment, manage project dependencies, run a basic Node.js application, and investigate browser problems using Developer Tools.

It also demonstrated how Git and GitHub support version control and collaboration. Commands for checking status, staging changes, committing work, configuring a remote, pushing changes, and troubleshooting rejected pushes were explained with their purposes and reasoning.

Using consistent tooling, dependency configuration, a lockfile, and a safe Git workflow helps team members maintain a reproducible development environment. Reviewing changes and integrating remote commits carefully also reduces the risk of losing another developer's work.

The final submission should include the completed report, relevant practical files, the GitHub repository URL, and the two required screenshots.

---

**End of Assignment 1**
