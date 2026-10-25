# Practical Work: CS-408 Assignment 1

## 1. Objective

The objective of this practical work is to set up a Node.js development environment, execute a JavaScript program, and manage project files using Git and GitHub.

## 2. Tools Used

* Visual Studio Code
* Node.js
* npm
* Git
* GitHub

## 3. Checking Node.js and npm Installation

The following commands were used to check the installed versions of Node.js and npm.

```bash
node -v
npm -v
```

These commands display the installed versions of Node.js and npm.

## 4. Initializing the Project

The following command initializes a Node.js project:

```bash
npm init -y
```

It creates a default `package.json` file containing the project's configuration.

## 5. Creating the JavaScript Application

A file named `app.js` is used to execute a simple JavaScript program.

Example code:

```javascript
const student = "CS-408 Student";

console.log("Welcome to Node.js!");
console.log("Course:", student);
console.log("Project is running successfully.");
```

## 6. Running the Application

The application can be executed using:

```bash
node app.js
```

### Expected Output

```text
Welcome to Node.js!
Course: CS-408 Student
Project is running successfully.
```

The output confirms that the program executes and displays the specified messages.

## 7. Git Workflow

The following commands are commonly used to manage project changes.

### Check Repository Status

```bash
git status
```

### Stage Changes

```bash
git add .
```

### Commit Changes

```bash
git commit -m "Update assignment practical work"
```

### Push Changes to GitHub

```bash
git push
```

These commands check the working tree, stage changes, record a commit, and push committed changes to the configured remote repository.

## 8. Git Ignore Configuration

The `.gitignore` file contains the following entries:

```gitignore
node_modules/
.env
```

These entries prevent Git from tracking untracked files in the specified directory and the specified environment file.

## 9. GitHub Repository

The project is maintained in the following GitHub repository:

[CS408-ASSIGNMENT1](https://github.com/naeem86810-cmd/CS408-ASSIGNMENT1)

The repository contains the assignment documentation, Node.js application, and supporting project files.

## 10. Conclusion

This practical work demonstrates the basic setup and execution of a Node.js application. It also documents the use of Git commands for version control and GitHub for online repository hosting.

The project files are organized so that theoretical answers and practical documentation can be accessed from one repository.
