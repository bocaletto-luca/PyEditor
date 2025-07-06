# PyEditor v1.0.0
#### Author: Bocaletto Luca

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue?style=for-the-badge&logo=gnu)](LICENSE) [![Language: Python](https://img.shields.io/badge/Language-Python-blue?style=for-the-badge&logo=python)](https://www.python.org/) [![Linux-Compatible](https://img.shields.io/badge/Linux-Compatible-blue?style=for-the-badge&logo=linux)](https://www.kernel.org/) [![Status: Complete](https://img.shields.io/badge/Status-Complete-brightgreen?style=for-the-badge)](https://github.com/bocaletto-luca/Directory-Monitor)

PyEditor is a modern, terminal-based text editor in Python that blends Nano’s simplicity with IDE-style features. It uses `curses` for fast screen updates, Pygments for real-time syntax highlighting, and a JSON config file for full customization of keybindings (save, quit, undo, redo, search, replace) and color themes. Core editing features include undo/redo stacks, incremental search (Ctrl+F), regex find & replace (Ctrl+R), dynamic line numbering, mouse-driven cursor placement, and a colorized status bar showing file name, modified flag, cursor position, and shortcut hints. It runs entirely in the console—ideal for SSH sessions, containers, or headless environments.

---

## Table of Contents

- [Overview](#overview)  
- [Features](#features)  
- [Prerequisites](#prerequisites)  
- [Installation](#installation)  
- [Usage](#usage)  
- [Keybindings](#keybindings)  
- [Configuration](#configuration)  
- [Contributing](#contributing)  
- [License](#license)  
- [Author](#author)  

---

## Overview

PyEditor operates entirely within a Unix-style terminal (Linux, macOS, WSL) and requires no GUI. Its lightweight codebase and minimal startup time make it perfect for quick edits in any shell environment.

---

## Features

- Undo/Redo (Ctrl+Z / Ctrl+Y)  
- Incremental search (Ctrl+F) and regex-powered find & replace (Ctrl+R)  
- Real-time syntax highlighting via Pygments  
- Dynamic line numbers and smooth scrolling  
- Mouse-click cursor positioning  
- Colorized status bar with modified-file indicator (*)  
- Fully customizable keybindings and theme via JSON  

---

## Prerequisites

- **Python** 3.6 or newer  
- Unix-style terminal with `curses` support  
- **Pygments** library  
  - Debian/Ubuntu:  
    ```bash
    sudo apt update
    sudo apt install python3-pygments
    ```  
  - Or in a virtual environment:  
    ```bash
    python3 -m venv .venv
    source .venv/bin/activate
    pip install pygments
    ```  

---

## Installation

Clone the repository and prepare dependencies:

```bash
git clone https://github.com/bocaletto-luca/PyEditor.git
cd PyEditor
```

Choose one of:

1. **System install of Pygments** (Debian/Ubuntu):  
   ```bash
   sudo apt install python3-pygments
   ```

2. **Virtual environment** (any Linux/macOS):  
   ```bash
   python3 -m venv .venv
   source .venv/bin/activate
   pip install pygments
   ```

Finally make the script executable:

```bash
chmod +x pyeditor.py
```

---

## Usage

```bash
./pyeditor.py [optional_filename]
```

- Launch with a filename to edit that file, or omit to start with an empty buffer.  
- Press Ctrl+S to save, Ctrl+Q to quit.

---

## Keybindings

| Keys         | Action                                    |
|--------------|-------------------------------------------|
| Arrow Keys   | Move cursor                              |
| Backspace    | Delete character                         |
| Enter        | Insert new line                          |
| Ctrl + S     | Save (Save As if unnamed)                |
| Ctrl + Q     | Quit editor                              |
| Ctrl + Z / Y | Undo / Redo                              |
| Ctrl + F     | Search                                   |
| Ctrl + R     | Find & Replace (regex)                   |
| Mouse Click  | Move cursor to clicked position          |

---

## Configuration

Create or edit `~/.pyeditor.json` to override defaults:

```json
{
  "keybindings": {
    "save": 19,
    "quit": 17,
    "undo": 26,
    "redo": 25,
    "search": 6,
    "replace": 18
  },
  "syntax": {
    "lexer": "python"
  },
  "theme": {
    "status_bg": "cyan",
    "status_fg": "black",
    "keyword": "yellow",
    "string": "green",
    "comment": "blue"
  }
}
```

- **keybindings**: ASCII codes for each command  
- **syntax.lexer**: name of a Pygments lexer (e.g., `python`, `javascript`)  
- **theme**: curses-compatible color names for status bar and token types  

---

## Contributing

Bug reports, feature requests, and pull requests are welcome!  

1. Fork the repository  
2. Create a feature branch (`git checkout -b feat/awesome`)  
3. Commit your changes with clear messages  
4. Open a pull request  

Please follow [PEP 8](https://peps.python.org/pep-0008/) style and include tests or examples for new features.

---

## License

Distributed under the **GNU GPL v3**. See [LICENSE](LICENSE) for details.

---

## Author

**Luca Bocaletto**  
- GitHub: [bocaletto-luca](https://github.com/bocaletto-luca)  
- Website: https://bocaletto-luca.github.io  

---
