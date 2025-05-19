# TaskVibe

[![GitHub stars](https://img.shields.io/github/stars/<your-username>/TaskVibe)](https://github.com/<your-username>/TaskVibe/stargazers)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)
[![Haskell](https://img.shields.io/badge/language-Haskell-brightgreen)](https://haskell.org)

**TaskVibe** is a modern task management and scheduling web application built with Haskell and the IHP framework. It features a robust backend API and a static frontend hosted on GitHub Pages, designed to help users organize their daily routines efficiently. Developed in GitHub Codespaces, this project showcases my expertise in functional programming, web development, and cloud-based workflows, making it a highlight of my freelance portfolio.

🌐 **Live Frontend**: [TaskVibe on GitHub Pages](https://<your-username>.github.io/TaskVibe)  
📖 **Documentation**: Available locally during development (see [Setup](#setup))

## Features

- **Task Management**: Create, read, update, and delete tasks with titles, descriptions, time slots, and completion status.
- **REST API**: Powered by IHP, providing secure and type-safe endpoints.
- **Static Frontend**: Built with HTML, Tailwind CSS, and JavaScript, hosted on GitHub Pages.
- **Local Documentation**: Sphinx-based docs with a classic theme, served locally for developers.
- **Cloud Development**: Fully configured for GitHub Codespaces, ensuring a seamless setup.

## Tech Stack

- **Backend**: Haskell, IHP Framework, PostgreSQL
- **Frontend**: HTML, Tailwind CSS, JavaScript
- **Documentation**: Sphinx (Python), Classic Theme
- **Development**: GitHub Codespaces, Nix
- **Hosting**: GitHub Pages (frontend), Codespaces (backend)

## Setup

### Prerequisites
- A GitHub account with Codespaces enabled.
- No local setup required—everything runs in the cloud!

### Running the App
1. **Create a Codespace**:
   - Navigate to [github.com/<your-username>/TaskVibe](https://github.com/<your-username>/TaskVibe).
   - Click "Code" > "Create codespace on main".
2. **Start the Backend**:
   ```bash
   cd DailyRoutine
   ./start
   ```
   - Access the API at the forwarded port (e.g., `https://<codespace-id>-8000.app.github.dev/api/tasks`).
3. **View the Frontend**:
   - Visit [https://<your-username>.github.io/TaskVibe](https://<your-username>.github.io/TaskVibe).
4. **Run Local Documentation**:
   ```bash
   cd sphinx-docs
   make html
   cd _build/html
   python -m http.server 8001
   ```
   - Access at `http://localhost:8001` or the forwarded port.

## Contributing

We welcome contributions to **TaskVibe**! Please read our [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on how to get involved, including code standards, issue reporting, and pull request processes.

## License

This project is licensed under the [MIT License](LICENSE).

## About the Developer

This project is part of my freelance portfolio, demonstrating my skills in Haskell, web development, and modern DevOps practices. Connect with me on [LinkedIn](https://linkedin.com/in/<your-linkedin>) or check out my other projects on [GitHub](https://github.com/<your-username>).

---

*Built with 💻 and ☕ in GitHub Codespaces.*