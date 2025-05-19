# Contributing to TaskVibe

Thank you for your interest in contributing to **TaskVibe**, a Haskell-based task management and scheduling web application! This document outlines how you can contribute, from reporting issues to submitting code changes. Your contributions help make TaskVibe better for everyone.

## Table of Contents

- [How to Contribute](#how-to-contribute)
  - [Reporting Issues](#reporting-issues)
  - [Suggesting Features](#suggesting-features)
  - [Submitting Pull Requests](#submitting-pull-requests)
- [Development Setup](#development-setup)
- [Code Standards](#code-standards)
  - [Haskell Backend](#haskell-backend)
  - [Frontend](#frontend)
  - [Documentation](#documentation)
- [Community Guidelines](#community-guidelines)

## How to Contribute

### Reporting Issues

If you encounter bugs or unexpected behavior:
1. Check the [Issues](https://github.com/<your-username>/TaskVibe/issues) page to avoid duplicates.
2. Create a new issue with:
   - A clear title and description.
   - Steps to reproduce the issue.
   - Expected and actual behavior.
   - Screenshots or logs, if applicable.
3. Use the "Bug" label when creating the issue.

### Suggesting Features

Have an idea to improve TaskVibe? We’d love to hear it!
1. Open an issue on the [Issues](https://github.com/<your-username>/TaskVibe/issues) page.
2. Provide a detailed description of the feature and its benefits.
3. Use the "Enhancement" label.
4. Be open to feedback and discussion.

### Submitting Pull Requests

To contribute code:
1. **Fork the Repository**:
   - Fork [TaskVibe](https://github.com/<your-username>/TaskVibe) to your GitHub account.
2. **Create a Branch**:
   - Use a descriptive branch name (e.g., `feature/add-task-priority` or `fix/api-error`).
   ```bash
   git checkout -b <branch-name>
   ```
3. **Make Changes**:
   - Follow the [Code Standards](#code-standards) below.
   - Test your changes locally (see [Development Setup](#development-setup)).
4. **Commit Changes**:
   - Write clear, concise commit messages (e.g., `Add task priority field to schema`).
   ```bash
   git commit -m "<commit-message>"
   ```
5. **Push and Create a Pull Request**:
   - Push your branch to your fork.
   ```bash
   git push origin <branch-name>
   ```
   - Open a pull request (PR) against the `main` branch of the original repository.
   - Include a detailed description of your changes, referencing related issues (e.g., `Fixes #123`).
6. **Code Review**:
   - Respond to feedback promptly.
   - Ensure all CI checks pass (if configured).
7. **Merge**:
   - Once approved, your PR will be merged by a maintainer.

## Development Setup

TaskVibe is developed in **GitHub Codespaces** for a seamless cloud-based environment. Follow these steps to set up the project:

1. **Create a Codespace**:
   - Go to [github.com/<your-username>/TaskVibe](https://github.com/<your-username>/TaskVibe).
   - Click "Code" > "Create codespace on main".
   - The environment includes Haskell, IHP, PostgreSQL, and Python (for Sphinx).

2. **Start the Backend**:
   ```bash
   cd DailyRoutine
   ./start
   ```
   - The IHP server runs on port 8000. Access the API via the forwarded port (e.g., `https://<codespace-id>-8000.app.github.dev/api/tasks`).

3. **Test the Frontend**:
   - Copy changes to the `docs` directory to test locally or check the live site at [https://<your-username>.github.io/TaskVibe](https://<your-username>.github.io/TaskVibe).
   ```bash
   cp -r frontend/* docs/
   ```

4. **Update Documentation**:
   - Edit files in `sphinx-docs/`.
   - Build and serve the docs:
   ```bash
   cd sphinx-docs
   make html
   cd _build/html
   python -m http.server 8001
   ```
   - Access at `http://localhost:8001` or the forwarded port.

5. **Install Additional Tools** (if needed):
   - Use Nix to install dependencies:
   ```bash
   nix-shell -p <package>
   ```

## Code Standards

To ensure consistency and quality, please adhere to the following guidelines.

### Haskell Backend

- **Framework**: Use IHP conventions for controllers, models, and views.
- **Style**: Follow the [Haskell Style Guide](https://kowainik.github.io/posts/2019-02-06-style-guide).
  - Use 2-space indentation.
  - Avoid excessive line length (aim for <80 characters).
- **Type Safety**: Leverage Haskell’s type system to prevent runtime errors.
- **Testing**: Add tests for new API endpoints in `Test/`.
- **Example**:
  ```haskell
  action CreateTaskAction = do
      let task = newRecord @Task
      task
          |> buildTask
          |> ifValid \case
              Left _ -> jsonErrorMessage "Invalid input" 400
              Right task -> do
                  task <- createRecord task
                  json task
  ```

### Frontend

- **Structure**: Keep HTML, CSS, and JS in the `frontend/` directory, copied to `docs/` for GitHub Pages.
- **Styling**: Use Tailwind CSS for consistency.
- **JavaScript**: Write modular, ES6-compliant code.
  - Use `async/await` for API calls.
  - Avoid inline scripts; place logic in `app.js`.
- **Example**:
  ```javascript
  async function createTask() {
      const task = {
          title: document.getElementById("title").value,
          startTime: document.getElementById("startTime").value
      };
      await fetch(API_URL, {
          method: "POST",
          headers: { "Content-Type": "application/json" },
          body: JSON.stringify(task)
      });
  }
  ```

### Documentation

- **Location**: Edit `.rst` files in `sphinx-docs/`.
- **Format**: Use reStructuredText (reST) with clear headings and code blocks.
- **Theme**: Maintain the “classic” Sphinx theme for an old-school look.
- **Example**:
  ```rst
  Setup
  =====
  To start the backend:
  .. code-block:: bash
      cd DailyRoutine
      ./start
  ```

## Community Guidelines

We strive to maintain a welcoming and inclusive community. Please:
- Be respectful and constructive in all interactions.
- Follow the [Code of Conduct](CODE_OF_CONDUCT.md) (if present).
- Avoid personal attacks or offensive language.
- Provide feedback thoughtfully, and be open to receiving it.

## Questions?

If you have any questions or need help, feel free to:
- Open an issue with the "Question" label.
- Contact the maintainer via [GitHub](https://github.com/<your-username>).

Thank you for contributing to **TaskVibe**! 🚀
