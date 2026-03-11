# 04 — GitHub, Cloning, and Workspace Setup
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./00-Environment-Setup.md)

---

You will be working with two separate repositories in this course. This guide covers both.

| Repository | Purpose | What you do |
|------------|---------|-------------|
| `Python-Development` (public) | Lecture notes and exercises | Clone once, pull every class |
| GitHub Classroom repos (private) | Graded submissions | Clone per assignment, push to submit |

---

## Part A — Create a GitHub Account

1. Go to [github.com](https://github.com) and click **Sign up**
2. Use an email you check regularly
3. Choose a professional username — this will be visible to your instructor and future employers
4. Verify your email address

---

## Part B — Clone the Course Repo

This is the public repository that contains all lecture notebooks and exercises. You clone it once and pull updates every class.

```powershell
# Navigate to where you want to save your work
cd Documents

# Clone the course repo
git clone https://github.com/mcc-bsit-2526/Python-Development.git

# Go into the folder
cd Python-Development
```

> ⚠️ You have read access only — you cannot push to this repo. That is expected.

---

## Part C — Set Up Your Virtual Environment

Do this once, right after cloning.

```powershell
# Make sure you are inside the Python-Development folder
cd Python-Development

# Create the virtual environment
py -3.12 -m venv venv

# Activate it
.\venv\Scripts\activate

# Install course dependencies
pip install -r requirements.txt

# Open in VS Code
code .
```

You should see `(venv)` at the start of your terminal prompt after activating. That confirms the virtual environment is active.

> ⚠️ Every time you open a new terminal, you need to activate the venv again with `.\venv\Scripts\activate` before running any notebooks.

---

## Part D — Pulling Updates Each Class

Your instructor will add new notebooks and exercises to the course repo regularly. Before each class, pull the latest changes:

```powershell
cd Python-Development
.\venv\Scripts\activate
git pull
code .
```

That is all you need to do. Any new files your instructor added will appear automatically.

---

## Part E — GitHub Classroom (Assignments)

GitHub Classroom is where you submit graded work. Your instructor will post two invite links on MS Teams for each module — one for exercises, one for the activity.

### Accepting an assignment

1. Click the invite link posted on MS Teams
2. Sign in to GitHub if prompted
3. Find your name in the roster and click it — this links your GitHub account to your student record
4. Click **Accept this assignment**
5. Wait a few seconds while GitHub creates your private repository
6. Click the link to your new repo — it will be named something like:
   `https://github.com/mcc-bsit-2526/m01-exercises-your-username`

Your repository is private — only you and your instructor can see it.

### Cloning your assignment repo

```powershell
# Clone your assignment repo — replace the URL with yours
git clone https://github.com/mcc-bsit-2526/m01-exercises-your-username.git

# Open it in VS Code
code m01-exercises-your-username
```

> Note: Assignment repos use the venv you already set up in Python-Development. You do not need to create a new one.

### Your assignment repo structure

```
m01-exercises-your-username/
├── README.md              <- read this first
├── M01_Exercises.ipynb    <- your work goes here
├── requirements.txt       <- do not modify
└── test_m01.py            <- do not modify
```

> ⚠️ Do not rename, delete, or modify `test_m01.py` or `requirements.txt`. The autograder depends on them.

---

## Part F — First-Time GitHub Sign-In in VS Code

The first time VS Code connects to GitHub, a browser window will open asking you to authorize VS Code. Click **Authorize Visual Studio Code** and follow the prompts.

If the terminal asks for a password, use your Personal Access Token — not your GitHub account password. See [03-Install-Git.md](./04-Install-Git.md) for how to create one.

---

## Common Issues

**"Repository not found" when cloning**
Make sure you accepted the assignment first and copied your personal repo URL, not the template.

**Cannot find your name in the classroom roster**
Contact your instructor to be added manually.

**`(venv)` does not appear after activating**
Run this first:
```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```
Then try activating again.

**VS Code asks to sign in but nothing happens**
Try cloning via the terminal instead of the VS Code interface.

---

Next: [Using Notebooks](./06-Using-Notebooks.md)
