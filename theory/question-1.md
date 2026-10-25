# Question 1: Environment Setup

## (a) Tools Required for Web Development

The following tools are required for web development:

1. **Visual Studio Code:** A code editor used to write and manage source code.
2. **Node.js:** A JavaScript runtime environment that allows JavaScript to run outside a web browser.
3. **npm:** Node Package Manager is used to install and manage project dependencies.
4. **Browser Developer Tools:** These tools help developers inspect HTML, CSS, JavaScript errors, and network requests.
5. **React Developer Tools:** A browser extension used to inspect React components and their properties.

## (b) Understanding package.json

The `package.json` file contains important information about a Node.js project, including its name, version, scripts, and dependencies.

### Dependencies

Dependencies are packages required for the application to run.

### DevDependencies

DevDependencies are packages used during development, such as testing and code-formatting tools.

### package-lock.json

This file records the exact versions of installed packages to help maintain consistent installations.

### Useful npm Commands

* `npm init -y` — Creates a package.json file.
* `npm install` — Installs project dependencies.
* `npm install package-name` — Installs a specific package.
* `npm ci` — Installs packages according to the lockfile.

## (c) Creating and Running a Node.js Project

### Step 1: Create a Project Folder

Create a folder named `CS408-ASSIGNMENT-1` and open it in Visual Studio Code.

### Step 2: Initialize the Project

Open the VS Code terminal and run:

```bash
npm init -y
```

### Step 3: Create app.js

Create a file named `app.js` and write the following code:

```javascript
const student = "CS-408 Student";

console.log("Welcome to Node.js!");
console.log("Course:", student);
console.log("Project is running successfully.");
```

### Step 4: Run the Program

Execute this command in the terminal:

```bash
node app.js
```

### Expected Output

```text
Welcome to Node.js!
Course: CS-408 Student
Project is running successfully.
```

The output confirms that the Node.js program runs successfully.

## (d) Debugging Webpage Errors

Browser Developer Tools help identify and fix webpage errors.

### Console Panel

The Console panel displays JavaScript errors and warnings. Developers can use error messages to identify problems in their code.

### Network Panel

The Network panel displays requests made by a webpage. If an image fails to load, the developer can check its request status and file path.

### Elements Panel

The Elements panel allows developers to inspect HTML elements and their CSS styles.

### Steps to Fix an Incorrect Webpage

1. Open the webpage in a browser.
2. Open Developer Tools by pressing `F12`.
3. Check the Console panel for JavaScript errors.
4. Check the Network panel for failed image requests.
5. Verify the image path and filename.
6. Correct the code and reload the webpage.

### Conclusion

The correct development tools and debugging techniques help developers create, test, and maintain reliable web applications.
