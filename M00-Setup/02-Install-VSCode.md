# 02 — Install VS Code & Extensions
### Python Development | MCC BSIT 2526

[Back to Setup Overview](./Setup.md)

---

VS Code (Visual Studio Code) is the editor used to write Python code and run Jupyter notebooks in this course. It is free and used widely in the industry.

---

## Installing VS Code

### Windows

1. Go to [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Click **"Download for Windows"** and run the installer
3. On the **"Select Additional Tasks"** screen, check these two:
   - Add "Open with Code" action to Windows Explorer file context menu
   - Add to PATH
4. Click Next and finish the installation

### macOS

1. Go to [https://code.visualstudio.com/](https://code.visualstudio.com/)
2. Click **"Download for Mac"** and open the downloaded `.zip`
3. Drag **Visual Studio Code** into your **Applications** folder
4. Open it from Applications — right-click and choose Open the first time

### Linux (Ubuntu / Debian)

Download the `.deb` file from [https://code.visualstudio.com/](https://code.visualstudio.com/) and run:
```bash
sudo dpkg -i code_*.deb
```

Or install via terminal:
```bash
sudo apt install wget gpg -y
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -D -o root -g root -m 644 packages.microsoft.gpg /etc/apt/keyrings/packages.microsoft.gpg
echo "deb [arch=amd64 signed-by=/etc/apt/keyrings/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" | sudo tee /etc/apt/sources.list.d/vscode.list
sudo apt update
sudo apt install code -y
```

**Verify:** Open VS Code — you should see the Welcome tab.

---

## Installing Extensions

Extensions add Python and Jupyter Notebook support to VS Code. Do this once after installation.

1. Open VS Code
2. Open the Extensions panel: `Ctrl + Shift + X` (Windows/Linux) or `Cmd + Shift + X` (macOS)
3. Search for and install these three extensions — all published by **Microsoft**:

| Extension | Search term |
|-----------|-------------|
| Python | `Python` |
| Jupyter | `Jupyter` |
| Pylance | `Pylance` |

4. After installing all three, close and reopen VS Code

**Verify:** Create a new file, save it as `test.py`, type `print("Hello")` — you should see colored syntax highlighting.

---

## Common Issues

**No syntax highlighting after installing extensions**  
Close VS Code completely and reopen. If still grey, press `Ctrl + Shift + P` and run `Python: Select Interpreter`, then choose your Python version.

**"Install" button is greyed out**  
Check your internet connection.

**VS Code opens blank or black (Linux)**  
Launch with `code --disable-gpu` to work around a GPU rendering issue.

---

Next: [Install Git](./03-Install-Git.md)
