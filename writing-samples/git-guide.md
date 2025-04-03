# Git for Beginners

Version control is essential for developers, and Git is the most widely used system. This guide covers the basics to get you started.

## Installation

- **Windows**: Download from [git-scm.com](https://git-scm.com)
- **macOS**: Use Homebrew - `brew install git`
- **Linux**: Use your package manager - `sudo apt install git`

## Initial Setup

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

## Common Commands
| Command | Description |
|--------|-------------|
| `git init` | Initialize a repo |
| `git clone <url>` | Clone a remote repo |
| `git status` | Check current changes |
| `git add <file>` | Stage changes |
| `git commit -m "message"` | Commit staged changes |
| `git push` | Push to remote |
| `git pull` | Pull latest from remote |

## Create a New Repo
```bash
mkdir my-project
cd my-project
git init
echo "# My Project" > README.md
git add .
git commit -m "Initial commit"
git remote add origin https://github.com/yourusername/my-project.git
git push -u origin main
```

## Summary 
Git can seem tricky at first, but with a few commands, you'll be managing code like a pro. 

[back](./)
