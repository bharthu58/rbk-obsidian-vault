Mise-en-place (mise) is a fast, cross-platform tool version manager (formerly asdf-plugin-manager). Key commands include mise use for configuring tools, mise install for installing them, and mise ls for listing installed versions.

**Core Mise Commands**

*   **[mise use @<VERSION](https://www.google.com/search?q=mise+use+%40%3CVERSION&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAB)**: The most used command. Installs a tool and adds it to the local `mise.toml` file (e.g., `mise use node@20`).
*   **[mise use -g @<VERSION](https://www.google.com/search?q=mise+use+-g+%40%3CVERSION&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAD)**: Installs a tool globally (`~/.config/mise/config.toml`).
*   **[mise i|install \[TOOL@VERSION\]](https://www.google.com/search?q=mise+i%7Cinstall+%5BTOOL%40VERSION%5D&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAF)**: Installs tools defined in `mise.toml` or a specific tool version.
*   **[mise ls](https://www.google.com/search?q=mise+ls&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAH)**: Lists all currently installed/active tools.
*   **[mise ls-remote <TOOL](https://www.google.com/search?q=mise+ls-remote+%3CTOOL&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAJ)**: Lists available versions of a tool.
*   **[mise x|exec @ -- <COMMAND](https://www.google.com/search?q=mise+x%7Cexec+%40+--+%3CCOMMAND&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAL)**: Executes a command using a specific tool version without creating a config file.
*   **[mise r|run <TASK](https://www.google.com/search?q=mise+r%7Crun+%3CTASK&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAN)**: Runs a defined task from `mise.toml`.
*   **[mise outdated](https://www.google.com/search?q=mise+outdated&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAP)**: Checks for newer versions of installed tools.
*   **[mise link <PATH](https://www.google.com/search?q=mise+link+%3CPATH&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAR)**: Symlinks a tool installed elsewhere into mise.
*   **[mise --version](https://www.google.com/search?q=mise+--version&rlz=1C1VDKB_enUS1138US1138&oq=basic+mise+commands&gs_lcrp=EgZjaHJvbWUyBggAEEUYOdIBCDI1NzdqMGo3qAIAsAIA&sourceid=chrome&ie=UTF-8&ved=2ahUKEwjs3JjKnIWTAxURjIkEHVfrNHYQgK4QegQIAxAT)**: Checks the installed version of mise.
    
**Common Options**

*   `-f, --force`: Force reinstall.
*   `-y, --yes`: Answer yes to prompts.
*   `-p, --path`: Specify a config file path.

---