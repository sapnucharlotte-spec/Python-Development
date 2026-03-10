# 03 — Install Git & Configure GitHub
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./README.md)

---

Git tracks your code changes and connects your local work to GitHub for submission.

- **Git** — the tool that tracks changes on your machine
- **GitHub** — the website that stores your code online
- **git push** — uploads your local commits to GitHub

---

## Installing Git

### Windows

1. Go to [https://git-scm.com/download/win](https://git-scm.com/download/win)
2. Run the installer and use these settings:

| Step | Choose |
|------|--------|
| Default editor | Use Visual Studio Code as Git's default editor |
| Initial branch name | Override — `main` |
| PATH environment | Git from the command line and also from 3rd-party software |
| Everything else | Leave as default |

3. Click Install and finish

**Verify — open Command Prompt:**
```
git --version
```

### macOS

Check if Git is already installed:
```bash
git --version
```

If not installed, macOS will prompt you to install Xcode Command Line Tools — click Install.

Or install via Homebrew:
```bash
brew install git
```

### Linux

```bash
sudo apt update
sudo apt install git -y
git --version
```

---

## Configure Git with Your GitHub Account

This attaches your identity to every commit you make. Use the same email as your GitHub account.

Open a terminal and run:
```bash
git config --global user.name "Your Full Name"
git config --global user.email "your-github-email@example.com"
```

**Verify:**
```bash
git config --global --list
```

You should see your name and email listed.

---

## Creating a Personal Access Token

GitHub no longer accepts your account password for Git operations. You need a **Personal Access Token (PAT)** — use it as your password whenever Git asks.

1. Go to [github.com](https://github.com) and sign in
2. Click your profile picture (top right) → Settings
3. Scroll to the bottom of the left sidebar → Developer settings
4. Click Personal access tokens → Tokens (classic)
5. Click "Generate new token (classic)"
6. Set:
   - Note: `VS Code Git`
   - Expiration: 90 days
   - Scopes: check **repo**
7. Click Generate token

> ⚠️ Copy the token immediately. You cannot view it again after leaving the page. Save it somewhere safe.

When Git asks for your password — paste the token instead.

---

## Common Issues

**"Please tell me who you are"**  
Run the `git config` commands from the Configure section above.

**"git is not recognized" (Windows)**  
Restart your terminal after installation. If still not working, reinstall Git and select "Git from the command line" during setup.

**Push fails with "authentication failed"**  
Use your Personal Access Token as the password, not your GitHub account password.

---

Next: [GitHub Classroom](./04-GitHub-Classroom.md)
