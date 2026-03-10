# 08 — Python Virtual Environments
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./README.md)

---

## What is a Virtual Environment?

When you install Python, packages you install with `pip` go into a single global location on your machine. This becomes a problem when:

- Different projects need different versions of the same package
- A package you install for one project breaks another project
- You work on a shared or lab computer and cannot install packages globally

A **virtual environment** is an isolated copy of Python for a specific project. Packages installed inside it stay there and do not affect anything else on your machine.

Think of it this way:

```
Without virtual environments          With virtual environments

Global Python                         Global Python
  └── requests 2.28                     (unchanged)
  └── numpy 1.23                      
  └── flask 1.0   <-- breaks          Project A/
       when you                         └── venv/
       upgrade for                           └── flask 1.0
       another project                       └── numpy 1.23

                                      Project B/
                                        └── venv/
                                             └── flask 3.0
                                             └── numpy 2.0
```

In this course, each assignment repo has a `requirements.txt` file listing the packages it needs. You create a virtual environment, install from that file, and everything works consistently — on your machine, your classmate's machine, and the autograder.

---

## Creating a Virtual Environment

Navigate to your project folder first, then run:

### Windows
```
python -m venv venv
```

### macOS / Linux
```bash
python3 -m venv venv
```

This creates a folder called `venv` inside your project. It contains its own Python interpreter and a place for packages.

> ⚠️ Never commit the `venv` folder to GitHub. It is large and machine-specific. The `.gitignore` in your assignment repos already excludes it.

---

## Activating the Virtual Environment

You must activate the environment each time you open a new terminal session.

### Windows (Command Prompt)
```
venv\Scripts\activate
```

### Windows (PowerShell)
```
venv\Scripts\Activate.ps1
```

> ⚠️ If PowerShell blocks the script with an error about execution policy, run this first:
> ```
> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
> ```
> Then try activating again.

### macOS / Linux
```bash
source venv/bin/activate
```

When activated, your terminal prompt will show the environment name:
```
(venv) C:\Users\YourName\Documents\PythonDev\M01-exercises>
```

---

## Installing Packages from requirements.txt

Once the environment is active, install the required packages:

```bash
pip install -r requirements.txt
```

This installs exactly the packages the project needs — nothing more, nothing less.

---

## Deactivating the Virtual Environment

When you are done working, deactivate it:

```bash
deactivate
```

Your terminal prompt returns to normal. The packages you installed are still inside the `venv` folder for next time.

---

## Using the Virtual Environment in VS Code

VS Code needs to know about your virtual environment so it uses the right Python interpreter for the notebook.

1. Open your project folder in VS Code
2. Press `Ctrl + Shift + P` (Windows/Linux) or `Cmd + Shift + P` (macOS)
3. Type `Python: Select Interpreter` and press Enter
4. Look for the entry that shows `venv` in the path, for example:
   ```
   Python 3.12.x ('venv': venv)
   ```
5. Select it

VS Code will now use this environment for all Python files and notebooks in the project. You do not need to manually activate the environment in the terminal every time — VS Code handles it.

---

## Typical Workflow per Assignment

```
1. Accept assignment on GitHub Classroom
2. Clone the repo to your machine
3. Open the folder in VS Code
4. Open the terminal in VS Code (Ctrl + `)
5. Create a virtual environment:
       python -m venv venv         (Windows)
       python3 -m venv venv        (macOS/Linux)
6. Activate it:
       venv\Scripts\activate       (Windows)
       source venv/bin/activate    (macOS/Linux)
7. Install dependencies:
       pip install -r requirements.txt
8. Select the venv interpreter in VS Code
9. Open the notebook and start working
10. When done, commit and push
```

---

## Common Issues

**"python is not recognized" when creating the environment (Windows)**  
Python is not in your PATH. See [01-Install-Python.md](./01-Install-Python.md).

**PowerShell blocks activation with a script error**  
Run this in PowerShell as your normal user (not administrator):
```
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Then try `venv\Scripts\Activate.ps1` again.

**VS Code does not show the venv interpreter**  
Make sure you created the virtual environment inside the project folder that is open in VS Code. If it still does not appear, press `Ctrl + Shift + P` → `Python: Refresh Interpreters`.

**Packages install but the notebook still cannot import them**  
The notebook kernel is not using the venv interpreter. Go back to the "Using the Virtual Environment in VS Code" section above and select the correct interpreter.

**venv folder accidentally pushed to GitHub**  
Add `venv/` to your `.gitignore` file, then run:
```bash
git rm -r --cached venv
git commit -m "Remove venv from tracking"
git push
```

---

[Install Git](./04-Install-Git.md)
