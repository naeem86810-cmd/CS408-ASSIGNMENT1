# Question 1: Development Environment Setup

## (a) Development Tools and Their Justification

A suitable development environment helps developers write, run, test, and debug web applications. The following tools are commonly used in modern web development.

### 1. Visual Studio Code (VS Code)

**Definition:**
Visual Studio Code is a source code editor used to write and edit programming code.

**Main Features:**

* **Code Editing:** Allows developers to write and modify code.
* **Syntax Highlighting:** Displays different parts of code in different colors.
* **Extensions:** Adds additional features and programming language support.
* **Debugging:** Helps developers identify and fix errors.
* **Integrated Terminal:** Allows commands to run directly inside VS Code.

**Example:**
A developer can create a JavaScript file named `app.js` and write a Node.js program in it.

**Justification:**
VS Code provides a convenient environment for writing, managing, and debugging code.

### 2. VS Code Extensions

Extensions add extra features to Visual Studio Code.

| Extension | Purpose                                                           |
| --------- | ----------------------------------------------------------------- |
| Prettier  | Formats code consistently and improves readability.               |
| ESLint    | Identifies potential JavaScript errors and coding-style problems. |

**Justification:**
These extensions help developers write clean, readable, and consistent code.

### 3. Node.js

**Definition:**
Node.js is a JavaScript runtime environment that allows JavaScript code to execute outside a web browser.

**Main Purpose:**

* Runs JavaScript programs on a computer.
* Supports server-side application development.
* Provides an environment for running JavaScript tools.

**Example:**

```javascript
console.log("Welcome to Node.js!");
```

Save the code in a file named `app.js`.

Run it using this command:

```bash
node app.js
```

**Justification:**
Node.js allows developers to execute JavaScript programs without opening a browser.

### 4. npm (Node Package Manager)

**Definition:**
npm stands for Node Package Manager. It is used to install and manage JavaScript packages.

**Main Functions:**

* Installs packages required by a project.
* Manages project dependencies.
* Helps initialize Node.js projects.
* Runs commands defined in `package.json`.

**Example:**

```bash
npm init -y
```

This command creates a default `package.json` file.

**Justification:**
npm makes it easier to manage libraries and tools used in web development.

### 5. Browser Developer Tools

**Definition:**
Browser Developer Tools are built-in tools used to inspect, test, and debug websites.

They can usually be opened by pressing **F12** in a web browser.

**Important Panels:**

| Panel    | Purpose                                                               |
| -------- | --------------------------------------------------------------------- |
| Console  | Displays JavaScript errors, warnings, and messages.                   |
| Network  | Shows requests for images, scripts, stylesheets, and other resources. |
| Elements | Displays HTML elements and allows developers to inspect CSS styles.   |

**Justification:**
These tools help developers identify problems when a webpage does not display or behave as expected.

### 6. React Developer Tools

**Definition:**
React Developer Tools is a browser extension used to inspect applications developed with React.

**Main Features:**

* Displays the React component tree.
* Helps inspect component properties and state.
* Supports debugging React applications.

**Justification:**
It is useful when developing React applications, but it is not required to run a basic Node.js program.

---

## (b) package.json, Dependencies, DevDependencies, and Lockfiles

### 1. What Is package.json?

The `package.json` file contains important information about a Node.js project.

**It can contain:**

* Project name and version.
* Project description.
* Entry point of the application.
* Scripts for running commands.
* Dependencies and development dependencies.

**Example:**

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

**Explanation:**

* `name`: Specifies the project name.
* `version`: Specifies the project version.
* `description`: Describes the project.
* `main`: Specifies the main application file.
* `scripts`: Defines commands that can be executed using npm.

To run the application using the script above, enter:

```bash
npm start
```

### 2. Dependencies

**Definition:**
Dependencies are packages required by an application to perform its functions.

**Example:**

```bash
npm install express
```

This command installs Express and adds it to the project's dependencies.

**Purpose of Express:**

* Helps create web servers.
* Supports routing.
* Helps build web applications using Node.js.

**Justification:**
Dependencies provide reusable functionality without requiring developers to write everything from scratch.

### 3. DevDependencies

**Definition:**
DevDependencies are packages mainly used during development, testing, and code quality checks.

**Example:**

```bash
npm install --save-dev prettier
```

This command installs Prettier as a development dependency.

**Purpose of Prettier:**

* Formats source code.
* Maintains a consistent coding style.
* Improves code readability.

### 4. package-lock.json

**Definition:**
The `package-lock.json` file records the resolved dependency tree and specific package versions used by npm.

**Importance:**

* Helps maintain consistent dependency versions.
* Supports repeatable installations.
* Records information about installed packages.
* Helps team members install the same dependency tree.

For application projects, this file should generally be committed to Git.

### 5. Difference Between Dependencies and DevDependencies

| Dependencies                                     | DevDependencies                                |
| ------------------------------------------------ | ---------------------------------------------- |
| Required by the application at runtime.          | Mainly used during development and testing.    |
| Provide functionality needed by the application. | Support formatting, testing, and code quality. |
| Example: Express.                                | Example: Prettier.                             |
| Command: `npm install express`                   | Command: `npm install --save-dev prettier`     |

### 6. Difference Between npm install and npm ci

**npm install**

Installs project dependencies and can update the lockfile when necessary.

```bash
npm install
```

**npm ci**

Installs dependencies according to the existing lockfile. It is useful for clean and repeatable installations.

```bash
npm ci
```

**Important:**
`npm ci` requires a compatible lockfile and does not update it.

---

## (c) Steps to Create and Run a Node.js Project

The following steps demonstrate how to create and execute a simple Node.js application.

### Step 1: Create a Project Folder

Create a folder named:

```text
CS408-ASSIGNMENT-1
```

Open this folder in Visual Studio Code.

### Step 2: Open the Integrated Terminal

In VS Code, select:

**Terminal → New Terminal**

Check whether Node.js and npm are installed.

```bash
node -v
npm -v
```

**Explanation:**

* `node -v` displays the installed Node.js version.
* `npm -v` displays the installed npm version.

If both commands display version numbers, the tools are available in the terminal.

### Step 3: Initialize the Project

Run the following command:

```bash
npm init -y
```

This command creates a default `package.json` file.

The file contains basic project information and can be edited later.

### Step 4: Create app.js

Create a file named `app.js` in the project folder.

Write the following code:

```javascript
const student = "CS-408 Student";

console.log("Welcome to Node.js!");
console.log("Course:", student);
console.log("Project is running successfully.");
```

**Code Explanation:**

* `const student` declares a constant variable.
* `"CS-408 Student"` is the value stored in the variable.
* `console.log()` displays messages in the terminal.

### Step 5: Execute the Program

Run this command in the terminal:

```bash
node app.js
```

**Expected Output:**

```text
Welcome to Node.js!
Course: CS-408 Student
Project is running successfully.
```

**Explanation:**
Node.js reads and executes the JavaScript code in `app.js`. The `console.log()` statements display the output in the terminal.

### Step 6: Understand the Project Files

A basic project may contain the following files and folders:

```text
CS408-ASSIGNMENT-1/
├── app.js
├── package.json
├── package-lock.json
├── README.md
├── .gitignore
├── theory/
│   ├── question-1.md
│   └── question-2.md
└── practical/
    ├── practical-work.md
    └── screenshots/
```

**Purpose of Important Files:**

| File or Folder      | Purpose                                                           |
| ------------------- | ----------------------------------------------------------------- |
| `app.js`            | Contains the JavaScript application code.                         |
| `package.json`      | Stores project information, scripts, and dependency declarations. |
| `package-lock.json` | Records the resolved dependency tree.                             |
| `README.md`         | Introduces the project and explains how to use it.                |
| `.gitignore`        | Specifies files and folders Git should ignore.                    |
| `theory/`           | Contains written answers to theoretical questions.                |
| `practical/`        | Contains practical instructions and evidence.                     |

**Note:**
The `package-lock.json` file is normally generated or updated by npm operations that create or update the lockfile. Its presence depends on the operations performed in the project.

---

## (d) Debugging Incorrect Webpage Output and Failed Image Requests

Browser Developer Tools help developers investigate problems when a webpage displays incorrect output or an image fails to load.

The Console, Network, and Elements panels provide different types of evidence.

### 1. Console Panel

**Purpose:**
The Console panel displays JavaScript errors, warnings, and log messages.

**Procedure:**

1. Open the webpage in a browser.
2. Press `F12` to open Developer Tools.
3. Select the **Console** panel.
4. Look for error messages and warnings.
5. Click an error, if possible, to inspect its source location.

**Possible Findings:**

* Syntax errors.
* Undefined variables.
* Runtime errors.
* Incorrect JavaScript behavior.

**Example:**
If JavaScript attempts to use a variable that has not been defined, the Console may display a `ReferenceError`.

**Importance:**
The error message helps developers identify where the problem occurred and investigate its cause.

### 2. Network Panel

**Purpose:**
The Network panel displays requests made by a webpage, including requests for images, JavaScript files, and CSS files.

**Procedure:**

1. Open Developer Tools.
2. Select the **Network** panel.
3. Reload the webpage.
4. Filter requests by image type if needed.
5. Locate the failed request.
6. Inspect its URL, status code, and response details.

**Possible Findings:**

| Status or Result            | Possible Meaning                                              |
| --------------------------- | ------------------------------------------------------------- |
| `200 OK`                    | The request succeeded.                                        |
| `404 Not Found`             | The requested resource could not be found at that URL.        |
| `403 Forbidden`             | Access to the resource was denied.                            |
| `500 Internal Server Error` | The server encountered an error while processing the request. |

**Example:**
If an image request returns `404 Not Found`, the image URL or file location may be incorrect.

**Importance:**
The Network panel provides evidence about whether the browser successfully requested and received the image.

### 3. Elements Panel

**Purpose:**
The Elements panel displays the webpage's HTML structure and CSS styles.

**Procedure:**

1. Open Developer Tools.
2. Select the **Elements** panel.
3. Locate the relevant image element.
4. Inspect its `<img>` tag and `src` attribute.
5. Check whether the image URL is correct.
6. Inspect CSS properties that may affect the image's visibility or dimensions.

**Example:**

```html
<img src="images/logo.png" alt="Website Logo">
```

In this example, the browser attempts to load `logo.png` from the `images` directory relative to the webpage's URL.

If the file is stored elsewhere, the `src` path may need to be corrected.

**Importance:**
The Elements panel helps developers inspect the HTML and CSS associated with the problem.

### 4. Comparison of the Three Panels

| Panel    | Information Provided                                |
| -------- | --------------------------------------------------- |
| Console  | JavaScript errors, warnings, and messages.          |
| Network  | Requests, URLs, response details, and status codes. |
| Elements | HTML structure, image attributes, and CSS styles.   |

### 5. Example of Debugging a Failed Image

Suppose a website should display a logo, but the image is missing.

**Step 1:** Open the webpage and press `F12`.

**Step 2:** Check the Network panel to see whether the image request failed.

**Step 3:** Inspect the request URL and status code.

**Step 4:** Open the Elements panel and inspect the image's `src` attribute.

**Step 5:** Correct the image path if it is incorrect, then reload the webpage.

**Step 6:** Check the Network panel again to verify whether the request succeeds.

**Conclusion of the Example:**
Using these panels together helps developers investigate image-loading problems systematically. The actual error message and request details should be checked before deciding on a solution.

---

## Overall Conclusion

A suitable development environment is essential for modern web development. Visual Studio Code provides a convenient code editor, while Node.js allows JavaScript programs to run outside a browser. npm manages project packages, and `package.json` and `package-lock.json` help organize project configuration and dependencies.

Browser Developer Tools provide useful information for identifying JavaScript errors, failed network requests, and HTML or CSS problems.

By understanding these tools and following a structured workflow, developers can create, execute, organize, and debug web applications more effectively.
