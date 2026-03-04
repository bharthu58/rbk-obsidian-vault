---
tags:
  - linux
links: "[[Domain]]"
---
Managing Obsidian vaults in WSL2 from Windows requires opening the vault located in the WSL filesystem (`\\wsl$\...`) through the standard Windows Obsidian app. For best performance, keep the vault files within the WSL filesystem (e.g., `/home/username/vault`) and open them using the `\\wsl$\` network path to avoid performance issues with file watching. 
Methods to Access & Manage WSL2 Vaults in Obsidian

- **Direct Access via `\\wsl$` (Recommended):**
    1. Open Obsidian on Windows.
    2. Click **Open folder as vault**.
    3. In the file dialog, enter `\\wsl$` into the address bar to navigate to your WSL distribution files.
    4. Navigate to your vault folder (e.g., `\\wsl$\Ubuntu\home\youruser\vault`).
    5. Select the folder to open it.
- **Symlinking Method:**
    1. Create a folder in your Windows file system (`C:\Users\...`).
    2. Create a symbolic link (symlink) in WSL pointing to your WSL-based vault folder.