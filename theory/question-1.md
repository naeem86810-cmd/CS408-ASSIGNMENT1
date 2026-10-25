# Question 1: Development Environment Setup

## (a) Development Tools and Their Justification

A suitable development environment is important for developing, testing, and debugging web applications. The following tools are useful for modern web development.

### 1. Visual Studio Code

Visual Studio Code (VS Code) is a lightweight source-code editor that supports many programming languages. It provides syntax highlighting, code completion, an integrated terminal, and debugging features.

**Justification:** VS Code allows developers to write code, run commands, manage project files, and use Git without frequently switching between applications.

### 2. VS Code Extensions

Extensions add useful features to VS Code.

* **Prettier:** Formats code consistently and improves readability.
* **ESLint:** Identifies potential JavaScript errors and coding-style problems.

These extensions help developers maintain clean and consistent code.

### 3. Node.js

Node.js is a JavaScript runtime that allows JavaScript code to execute outside a web browser.

**Justification:** It enables developers to run JavaScript programs and build server-side applications.

For example:

```javascript
console.log("Welcome to Node.js!");
```

Save this code in `app.js` and run it with:

```bash
node app.js
```

### 4. npm

npm stands for Node Package Manager. It is installed with Node.js and is used to install and manage JavaScript packages.

For example:

```bash
npm init -y
```

This command creates a default `package.json` file.

### 5. Browser Developer Tools

Browser Developer Tools help developers inspect and debug websites. They can usually be opened by pressing F12 or using the browser's developer-tools menu.

Important panels include:

* **Console:** Displays JavaScript errors, warnings, and log messages.
* **Network:** Shows network requests, including failed image or script requests.
* **Elements:** Displays the webpage's HTML structure and allows inspection of CSS styles.

These tools help developers investigate problems and understand why a webpage is not displaying correctly.

### 6. React Developer Tools

React Developer Tools is a browser extension used to inspect React applications. It helps developers examine the React component tree and view component properties and state where available.

**Justification:** It is useful when developing and debugging React applications. It is not required to run a basic Node.js program.

---

## (b) package.json, Dependencies, DevDependencies, and Lockfiles

### 1. What Is package.json?

The `package.json` file contains information about a Node.js project, such as its name, version, scripts, and dependencies.

It also allows developers to define commands that can be executed using npm.

Example:

```json
{
  "name": "cs408-assignment-1",
  "version": "1.0.0",
  "description": "CS-408 Advanced Web Development Assignment",
  "main": "app.js",
  "scripts": {
    "start": "node app.js"
  }
}
```

The `start` script can be executed using:

```bash
npm start
```

### 2. Dependencies

Dependencies are packages required by an application to perform its functions.

For example, Express can be installed as a dependency:

```bash
npm install express
```

Express is commonly used to build web servers and web applications with Node.js.

### 3. DevDependencies

DevDependencies are packages mainly used during development, testing, or code quality checks.

For example, Prettier can be installed as a development dependency:

```bash
npm install --save-dev prettier
```

Prettier formats code to maintain consistent style.

### 4. package-lock.json

The `package-lock.json` file records the resolved dependency tree and specific package versions used by npm. It helps developers install consistent dependency versions across different environments.

This file should generally be committed to Git for an application project.

### 5. Difference Between Dependencies and DevDependencies

| Dependencies                            | DevDependencies                                    |
| --------------------------------------- | -------------------------------------------------- |
| Required by the application at runtime. | Mainly required during development.                |
| Example: Express.                       | Example: Prettier.                                 |
| Installed using `npm install express`.  | Installed using `npm install --save-dev prettier`. |

### 6. npm install and npm ci

The `npm install` command installs project dependencies and can update the lockfile when needed.

```bash
npm install
```

The `npm ci` command installs dependencies according to the existing lockfile. It is useful for clean, repeatable installations, especially in automated environments.

```bash
npm ci
```

---

## (c) Steps to Create and Run a Node.js Project

The following steps demonstrate how to create and execute a simple Node.js project.

### Step 1: Create a Project Folder

Create a folder named:

```text
CS408-ASSIGNMENT-1
```

Open this folder in Visual Studio Code.

### Step 2: Open the Integrated Terminal

In VS Code, select **Terminal → New Terminal**.

Check whether Node.js and npm are installed:

```bash
node -v
npm -v
```

These commands display the installed versions if the tools are available.

### Step 3: Initialize the Project

Run:

```bash
npm init -y
```

This command generates a default `package.json` file.

### Step 4: Create app.js

Create a file named `app.js` in the project folder and add the following JavaScript code:

```javascript
const student = "CS-408 Student";

console.log("Welcome to Node.js!");
console.log("Course:", student);
console.log("Project is running successfully.");
```

### Step 5: Execute the Program

Run the following command in the terminal:

```bash
node app.js
```

### Expected Output

```text
Welcome to Node.js!
Course: CS-408 Student
Project is running successfully.
```

### Explanation

* `const student = "CS-408 Student";` declares a constant variable.
* `console.log()` prints messages to the terminal.
* `node app.js` executes the JavaScript file using Node.js.

### Step 6: Review the Project Structure

The project contains the following important files:

```text
CS408-ASSIGNMENT-1/
├── app.js
├── package.json
├── package-lock.json
├── README.md
├── .gitignore
└── theory/
    ├── question-1.md
    └── question-2.md
```

The `package-lock.json` file is created when npm generates or updates the dependency lockfile. Its presence depends on the npm operations performed in the project.

---

## (d) Debugging Incorrect Webpage Output and Failed Image Requests

Browser Developer Tools help developers identify problems when a webpage displays incorrect output or an image fails to load.

The Console, Network, and Elements panels provide different kinds of evidence.

### 1. Console Panel

The Console panel displays JavaScript errors, warnings, and messages.

**Procedure:**

1. Open the webpage in a browser.
2. Press F12.
3. Select the Console panel.
4. Look for error messages and warnings.
5. Click an error when possible to inspect its source location.

**Evidence:** A JavaScript error may indicate a syntax problem, an undefined variable, or another runtime issue. The exact cause should be determined from the actual error message.

### 2. Network Panel

The Network panel shows requests made by the webpage, including image, CSS, and JavaScript requests.

**Procedure:**

1. Open Developer Tools.
2. Select the Network panel.
3. Reload the webpage.
4. Filter the requests by image type if needed.
5. Find the failed image request.
6. Inspect its URL, status code, and response information.

**Evidence:** A failed request with a `404 Not Found` status usually means the requested resource could not be found at that URL. Other status codes may indicate different problems. The actual request details are needed to determine the cause.

### 3. Elements Panel

The Elements panel displays the webpage's HTML structure and CSS styles.

**Procedure:**

1. Open the Elements panel.
2. Find the relevant image element.
3. Inspect the `<img>` tag and its `src` attribute.
4. Check whether the image URL is correct.
5. Inspect the associated HTML and CSS for display-related problems.

**Evidence:** An incorrect `src` value may point to the wrong image location. CSS rules may also hide an image or affect its dimensions.

### 4. How the Evidence Helps

The three panels complement one another:

| Panel    | Evidence Provided                                 |
| -------- | ------------------------------------------------- |
| Console  | JavaScript errors and warnings.                   |
| Network  | Failed requests, URLs, and HTTP status codes.     |
| Elements | HTML structure, image attributes, and CSS styles. |

For example, if an image does not appear, the Network panel may reveal a failed request, while the Elements panel can help determine whether the image's `src` attribute contains the expected URL.

A developer should use the actual messages and request details to identify the cause rather than assuming every image-loading problem has the same explanation.

### Conclusion

Visual Studio Code, Node.js, npm, and browser Developer Tools provide a useful environment for developing and debugging JavaScript applications. Understanding project configuration and dependency management also helps developers organize their projects and work consistently across different environments.
