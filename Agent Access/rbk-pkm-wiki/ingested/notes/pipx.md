---
links: "[[Python]]"
---
# pipx

`pipx` is a command-line tool that installs and runs Python applications in isolated virtual environments.

When to Use pipx
Use pipx for command-line tools and utilities that you want to use globally on your system. Examples of such tools include: 
black: A popular Python code formatter.
mypy: A static type checker for Python.
httpie: A user-friendly command-line HTTP client.
cookiecutter: A utility that creates projects from project templates. 
Do not use pipx for installing libraries that you intend to import into your own Python code or for managing the dependencies of a specific development project. For project-specific dependencies, you should use project management tools like **Poetry** or standard virtual environments with **pip**

## Installation

- **Install pipx itself:** It is recommended to install `pipx` using your operating system's package manager (`sudo apt install pipx` on Debian-based Linux) or using `pip install --user pipx` on Windows.
- **Ensure pipx is on your PATH:** After installation, run `pipx ensurepath` and restart your terminal to make sure the installed apps are accessible from anywhere.

## Common Commands

- **Install an application:** `pipx install <package_name>`
- **List installed applications:** `pipx list`
- **Upgrade an application:** `pipx upgrade <package_name>`
- **Upgrade all applications:** `pipx upgrade-all`
- **Uninstall an application:** `pipx uninstall <package_name>`
- **Run an application temporarily:** `pipx run <package_name>`



