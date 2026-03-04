---
links: "[[Python]]"
---
## Here is a compact cheat sheet of the most essential uv commands, broken down by their primary use cases.

### Project Management 
*Managing `pyproject.toml` based projects.*

| Command | Description |
| :--- | :--- |
| `uv init` | Initialize a new Python project |
| `uv add <package>` | Add a dependency to the project |
| `uv remove <package>`| Remove a dependency from the project |
| `uv sync` | Sync the virtual environment with project dependencies |
| `uv run <command>` | Run a script or command in the project's environment |

### Virtual Environments & Python
*Managing Python installations and isolated environments.*

| Command | Description |
| :--- | :--- |
| `uv venv` | Create a new virtual environment (default: `.venv`) |
| `uv python install <version>` | Install a specific Python version (e.g., `3.12`) |
| `uv python list` | List available and installed Python versions |

### Tool Management (`pipx` alternative)
*Running and installing standalone CLI tools.*

| Command | Description |
| :--- | :--- |
| `uv tool install <tool>` | Install a CLI tool globally in an isolated environment |
| `uv tool upgrade-all` | Upgrade all installed tools |
| `uvx <tool>` | Run a tool on-the-fly without installing it |

### Pip Interface (`pip`/`pip-tools` alternative)
*Fast, drop-in replacements for standard pip workflows.*

| Command | Description |
| :--- | :--- |
| `uv pip install <package>` | Install a package into the active environment |
| `uv pip compile reqs.in` | Lock dependencies into a `requirements.txt` file |
| `uv pip sync reqs.txt` | Sync the environment exactly to a `requirements.txt` |
| `uv pip freeze` | List currently installed packages and versions |