# 07 — Troubleshooting
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./README.md)

---

Find your error below and follow the fix. If your issue is not listed, post a screenshot in the MS Teams class channel.

---

## Python

**"python is not recognized" (Windows)**
```
'python' is not recognized as an internal or external command
```
You missed the "Add Python to PATH" checkbox during installation.  
Fix: Uninstall Python from Control Panel → Apps, then reinstall from [python.org](https://www.python.org/downloads/) and check the box.

---

**Wrong Python version (e.g. Python 2.7)**  
Fix: Install the latest version from python.org. On macOS and Linux, use `python3` instead of `python`.

---

**"pip: command not found"**  
Fix on Linux:
```bash
sudo apt install python3-pip -y
```
Fix on macOS:
```bash
python3 -m ensurepip
```
Fix on Windows: Reinstall Python — pip is included by default.

---

## VS Code

**No syntax highlighting — all text is the same color**  
The Python extension is not active.  
Fix: Go to Extensions (`Ctrl + Shift + X`), confirm Python by Microsoft is installed, click Reload if prompted, then restart VS Code.

---

**"No kernel found" when opening a notebook**  
Fix:
1. Click **"Select Kernel"** in the top right of the notebook
2. Choose Python Environments
3. Select your Python version

If no version appears: `Ctrl + Shift + P` → `Python: Select Interpreter` → pick your installed version.

---

**Kernel keeps crashing or restarting**  
Fix: Install the required packages:
```bash
pip install -r requirements.txt
```
If still crashing, click Restart in the notebook toolbar.

---

**VS Code opens blank or black (Linux)**  
Fix:
```bash
code --disable-gpu
```

---

## Git

**"Please tell me who you are"**
```
Author identity unknown
```
Fix:
```bash
git config --global user.name "Your Name"
git config --global user.email "your-github-email@example.com"
```

---

**"git is not recognized" (Windows)**  
Fix: Restart your terminal after installing Git. If still not working, reinstall and select "Git from the command line and 3rd-party software" during setup.

---

**Push fails with "authentication failed"**
```
remote: Support for password authentication was removed
```
Fix: Use a Personal Access Token as your password. See [03-Install-Git.md](./03-Install-Git.md) for how to create one.

---

**"Repository not found" when cloning**  
Fix:
- Confirm you accepted the assignment via the Classroom link first
- Check that you copied your personal repo URL, not the template URL
- Confirm you are signed into the correct GitHub account

---

**"src refspec main does not match any"**
```
error: src refspec main does not match any
```
Fix: You have not committed yet. Run:
```bash
git add .
git commit -m "first commit"
git push
```

---

**"Nothing to commit, working tree clean" after making changes**  
Fix: Your file was not saved. Press `Ctrl + S` in VS Code, then try again.

---

## Autograder

**Red X but code looks correct**  
The tests check output exactly. Common causes:
- Extra or missing spaces
- Wrong capitalization
- GPA showing `1.5` instead of `1.50`
- Missing punctuation in output strings

Click the red X on GitHub to read the exact error — it shows what was expected vs what was returned.

---

**Yellow circle that never finishes**  
Your function likely contains an `input()` call inside it. The autograder hangs waiting for input.  
Fix: Remove `input()` from inside your functions. Use hardcoded parameters for functions — `input()` should only appear in standalone cells outside function definitions.

---

**Tests pass locally but fail on GitHub**  
Fix: You likely forgot to push your latest changes. Run:
```bash
git status
```
If files are modified, stage, commit, and push again.

---

## Google Colab

**"Runtime disconnected"**  
Click Reconnect in the top right, then re-run all cells from the top.

**Output is wrong after editing a cell**  
Run all cells from the top: Runtime → Run all. Colab cells depend on each other in order.

---

[Back to Setup Overview](./README.md)
