# 06 — Committing & Pushing Your Work
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./README.md)

---

When you finish an exercise or want to save progress, you commit and push to GitHub. This is also how you submit assignments — no email or file uploads needed.

---

## How It Works

```
Your Computer                          GitHub
───────────────────────────────────────────────────
[Your Files]
     | git add .          (stage changes)
[Staged Changes]
     | git commit -m ""   (save a snapshot)
[Local Commit]
     | git push           (upload to GitHub)
                                  [Your Repo on GitHub]
                                          |
                                   Autograder runs
```

Every push triggers the autograder. Results appear on your repo page within seconds.

---

## Method A — VS Code Source Control Panel (Recommended)

1. Save your notebook — `Ctrl + S`
2. Click the **Source Control icon** in the left sidebar, or press `Ctrl + Shift + G`
3. Under **Changes**, click the **+** next to `M01_Exercises.ipynb` to stage it
4. Type a short message in the text box at the top, for example:  
   `Completed M01 exercises`
5. Click the **Commit** button (checkmark)
6. Click **Sync Changes** to push to GitHub

---

## Method B — Terminal

Open the VS Code terminal with `` Ctrl + ` `` and run:

```bash
git add .
git commit -m "Completed M01 exercises"
git push
```

---

## Checking Your Autograder Results

1. Go to your repo on GitHub
2. Look at the latest commit — you will see:
   - A green checkmark — all tests passed
   - A red X — some tests failed
   - A yellow circle — tests are still running, wait a few seconds
3. Click the checkmark or X to see detailed results — it shows exactly which tests passed and which failed, with a message explaining what went wrong

---

## If Tests Fail

1. Read the failing test message — it tells you what was expected vs what your code returned
2. Fix the code in VS Code
3. Save, then push again:
   ```bash
   git add .
   git commit -m "Fix Exercise 3"
   git push
   ```
4. Check GitHub again

You can push as many times as you want before the deadline. Every push re-runs the tests.

---

## Commit Message Guidelines

Your commit messages are visible to your instructor.

| Good | Bad |
|------|-----|
| `Completed all M01 exercises` | `aaa` |
| `Fix Exercise 3 formatting` | `done` |
| `Fix GPA decimal in challenge` | `final final FINAL` |

---

## Common Issues

**"Nothing to commit, working tree clean"**  
Your file was not saved. Press `Ctrl + S` and try again.

**"src refspec main does not match any"**  
You have not made a commit yet. Run `git add .` and `git commit` before pushing.

**Push fails with "authentication failed"**  
Use your Personal Access Token as the password. See [03-Install-Git.md](./03-Install-Git.md).

**Autograder shows a red X but your code seems correct**  
The tests check output exactly. Look for extra spaces, wrong capitalization, or missing decimal places in your output strings.

---

Setup complete. Go to your first module on GitHub and check MS Teams for the Module 01 announcement.

See [07-Troubleshooting.md](./07-Troubleshooting.md) if anything is still not working.
