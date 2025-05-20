```markdown
# TaskVibe Directory File Tree

This file describes the complete directory structure for the TaskVibe project, a Haskell-based daily routine and scheduling web app developed in GitHub Codespaces, with a frontend hosted on GitHub Pages and documentation generated using Sphinx.

```
TaskVibe/
├── .devcontainer/
│   ├── devcontainer.json
│   └── Dockerfile
├── .github/
│   └── workflows/
│       ├── ci.yml
│       └── docs.yml
├── src/
│   ├── Main.hs
│   ├── Models/
│   │   ├── Task.hs
│   │   └── Schedule.hs
│   ├── Routes/
│   │   ├── TaskRoutes.hs
│   │   └── ScheduleRoutes.hs
│   └── Utils/
│       └── Database.hs
├── frontend/
│   ├── index.html
│   ├── css/
│   │   └── styles.css
│   ├── js/
│   │   ├── script.js
│   │   └── api.js
│   └── assets/
│       ├── logo.png
│       └── favicon.ico
├── docs/
│   ├── conf.py
│   ├── index.rst
│   ├── readme_link.md
│   ├── introduction.md
│   ├── installation.rst
│   ├── api.rst
│   ├── guides/
│   │   ├── getting_started.md
│   │   ├── configuration.md
│   │   └── deployment.md
│   ├── reference/
│   │   ├── backend.rst
│   │   ├── frontend.rst
│   │   └── database.rst
│   ├── _build/
│   │   ├── html/
│   │   ├── latex/
│   │   └── doctrees/
│   ├── _static/
│   │   ├── custom.css
│   │   ├── logo.png
│   │   └── favicon.ico
│   ├── _templates/
│   │   ├── layout.html
│   │   ├── sidebar.html
│   │   └── footer.html
│   ├── make.bat
│   └── Makefile
├── tests/
│   ├── TestMain.hs
│   ├── TaskTests.hs
│   └── ScheduleTests.hs
├── .gitignore
├── README.md
├── LICENSE
├── TECHSTACK.md
├── CONTRIBUTING.md
├── TaskVibe.cabal
├── stack.yaml
├── package.json
└── tailwind.config.js
```

## File and Directory Descriptions

### Root Directory
- **.gitignore**: Specifies files and directories to ignore in Git (e.g., `docs/_build/`, `.stack-work/`, `node_modules/`).
- **README.md**: Project overview, including purpose, setup instructions, and links to documentation and GitHub Pages. Included in Sphinx via `readme_link.md`.
- **LICENSE**: MIT License for TaskVibe, defining usage and distribution terms.
- **TECHSTACK.md**: Lists technologies used (Haskell, Stack, Scotty, Tailwind CSS, Sphinx, MyST-Parser, GitHub Pages, Codespaces).
- **CONTRIBUTING.md**: Guidelines for contributing to TaskVibe, including setup, coding standards, and pull request processes.
- **TaskVibe.cabal**: Cabal file for Haskell dependencies and project configuration (e.g., `build-depends: base, scotty, aeson`).
- **stack.yaml**: Stack configuration for Haskell builds, specifying the resolver (e.g., `lts-22.0`).
- **package.json**: Node.js configuration for frontend dependencies (e.g., Tailwind CSS).
- **tailwind.config.js**: Tailwind CSS configuration for custom styles in the frontend.

### .devcontainer/
- **devcontainer.json**: Configures the Codespaces environment with Haskell, Python, and Node.js.
- **Dockerfile**: Custom Dockerfile for additional setup (e.g., installing `stack` or Sphinx dependencies).

### .github/workflows/
- **ci.yml**: GitHub Actions workflow for continuous integration, running Haskell tests and building the backend.
- **docs.yml**: GitHub Actions workflow for building and deploying Sphinx documentation to GitHub Pages.

### src/
- **Main.hs**: Main Haskell file, implementing the Scotty web server for TaskVibe’s backend API.
- **Models/Task.hs**: Defines the `Task` data type and related functions for task management.
- **Models/Schedule.hs**: Defines the `Schedule` data type for managing daily routines.
- **Routes/TaskRoutes.hs**: Defines API routes for task-related operations (e.g., create, update, delete tasks).
- **Routes/ScheduleRoutes.hs**: Defines API routes for schedule-related operations.
- **Utils/Database.hs**: Handles database interactions (e.g., SQLite for storing tasks and schedules).

### frontend/
- **index.html**: Main HTML file for the GitHub Pages frontend, providing the TaskVibe UI.
- **css/styles.css**: Tailwind CSS output for styling the frontend.
- **js/script.js**: JavaScript for frontend interactivity (e.g., DOM manipulation, form handling).
- **js/api.js**: JavaScript for API calls to the Haskell backend (e.g., fetching tasks via `fetch`).
- **assets/logo.png**: TaskVibe logo for branding in the frontend.
- **assets/favicon.ico**: Favicon for the GitHub Pages site.

### docs/
- **conf.py**: Sphinx configuration, enabling `myst_parser` and `sphinx_rtd_theme`.
- **index.rst**: Main documentation entry point with a table of contents (toctree).
- **readme_link.md**: Includes `README.md` in Sphinx documentation.
- **introduction.md**: Overview of TaskVibe’s purpose and features.
- **installation.rst**: Setup instructions for TaskVibe in Codespaces.
- **api.rst**: Documentation for backend API endpoints.
- **guides/**: Contains user guides in Markdown.
  - **getting_started.md**: Beginner’s guide to using TaskVibe.
  - **configuration.md**: Configuration instructions (e.g., environment variables).
  - **deployment.md**: Deployment steps for backend and frontend.
- **reference/**: Technical reference documentation in reStructuredText.
  - **backend.rst**: Documents Haskell backend modules and functions.
  - **frontend.rst**: Documents frontend components and scripts.
  - **database.rst**: Documents database schema (if applicable).
- **_build/**: Generated documentation output (HTML, LaTeX, doctrees).
- **_static/**: Custom static files (e.g., `custom.css`, `logo.png`, `favicon.ico`).
- **_templates/**: Custom Jinja2 templates (e.g., `layout.html`, `sidebar.html`, `footer.html`).
- **make.bat**: Windows batch file for Sphinx builds.
- **Makefile**: Unix Makefile for Sphinx builds.

### tests/
- **TestMain.hs**: Main test file for running Haskell tests with HUnit or Tasty.
- **TaskTests.hs**: Unit tests for task-related functions.
- **ScheduleTests.hs**: Unit tests for schedule-related functions.

## Usage Notes
- Build the Haskell backend with `stack build` in the root directory.
- Generate Sphinx documentation with `cd docs && make html`.
- Preview documentation locally with `python3 -m http.server 8000 --directory docs/_build/html`.
- Build the frontend CSS with `npx tailwindcss -i frontend/input.css -o frontend/css/styles.css`.
- Deploy the frontend and documentation to GitHub Pages by pushing `frontend/` and `docs/_build/html/` to the `gh-pages` branch.
- Run tests with `stack test`.
```