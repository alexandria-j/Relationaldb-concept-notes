# Relationaldb-concept-notes
My master study guide and reference notes for Relational Databases.

## 1. Code Editors vs. IDEs

* **Code Editor:** A lightweight application focused primarily on writing and editing the text of code files (e.g., VS Code, Sublime Text, Notepad++).
* **IDE (Integrated Development Environment):** A heavier, full-suite application that includes built-in tools to compile, run and debug code while you edit (e.g., Visual Studio, Xcode, Android Studio).
* **Cloud-Based Editors:** Allow you to write and execute code directly in a web browser without local installation (e.g., Replit, GitHub Codespaces).

---

## 2. Workspaces & CLI Basics

VS Code considers the directory (folder) you currently have open to be your **Workspace**.

### Essential CLI Commands
* `cd ~` : Navigate to your home directory.
* `mkdir my-project` : Create a new directory (folder) named "my-project".
* `code .` : (In terminal typying) Open the current directory in VS Code.

### Best Practice: Running a Local Web Server
Never open HTML files directly in your browser by double-clicking them (this causes bugs, such as CSS failing to load). 
* **The Fix:** Install the **Live Server** extension in VS Code. Open your HTML file and click **Go Live** in the bottom status bar. Project will launch safely on a local web server (usually `http://localhost:5500/`).

---

## 3. Essential VS Code Shortcuts

| Action | Windows / Linux | Mac |
| :--- | :--- | :--- |
| **Command Palette** | `Ctrl + Shift + P` | `Cmd + Shift + P` |
| **Search All Files** | `Ctrl + Shift + F` | `Cmd + Shift + F` |
| **Find & Replace** | `Ctrl + Shift + H` | `Cmd + Shift + H` |
| **Format Document** | `Shift + Alt + F` | `Shift + Option + F` |
| **Delete Current Line** | `Ctrl + Shift + K` | `Cmd + Shift + K` |
| **Toggle Sidebar** | `Ctrl + B` | `Cmd + B` |

### Multi-Line Editing
* **Keyboard:** Use `Ctrl + Alt + Down/Up` (Windows) or `Option + Cmd + Down/Up` (Mac) to drag your cursor across consecutive lines.
* **Mouse:** Hold `Alt` (Windows) or `Option` (Mac) and click anywhere to place multiple cursors.

---

## 4. Recommended VS Code Extensions

* **Error Lens:** Highlights the entire line of an error and displays the message directly in your code (no hovering required).
* **Code Spell Checker:** Catches typos in variables and accounts for camelCase formatting.
* **Better Comments:** Color-codes comments to highlight `TODOs`, warnings or questions.
* **Indent Rainbow:** Colorizes indentation levels, making scope incredibly easy to read.
* **Prettier & ESLint:** Essential tools for formatting and linting JavaScript.

---

## 5. Terminal vs. Command Line vs. Shell

While often used interchangeably, these three terms refer to different layers of the same system:
* **Command Line:** The actual text input interface where you type and execute commands.
* **Terminal (or Terminal Emulator):** The visual application/window that houses the command line (e.g., Windows Terminal, macOS Terminal, iTerm). 
* **Shell:** The invisible underlying software that actually reads your commands, interprets them and spits out the result (e.g., Bash, Zsh, PowerShell).

---

## 6. Essential Terminal Shortcuts

These shortcuts work in almost all Unix-based terminals (Linux/macOS) and heavily speed up workflow. 

| Action | Shortcut / Command | Note |
| :--- | :--- | :--- |
| **Cycle History** | `Up Arrow` / `Down Arrow` | Scrolls through your previously typed commands. |
| **Auto-Complete** | `Tab` | Finishes typing a file/folder name or command automatically. |
| **Clear Screen** | `Ctrl + L` | Clears terminal clutter (Use `cls` in Windows PowerShell). |
| **Kill Process** | `Ctrl + C` | Safely forces the current running command/program to stop. |
| **Send to Background** | `Ctrl + Z` | Pauses current task and returns you to the prompt. |
| **Bring to Foreground** | `fg` | Restores the task you paused with `Ctrl + Z`. |
| **Run Last Command** | `!!` | Instantly re-runs the exact last command executed. |

---

## 7. Basic Bash Commands (File Navigation & Creation)

*Bash (Bourne Again SHell) is the most common shell language in Unix environments.*

**Navigation & Viewing**
* `pwd` : **P**rint **W**orking **D**irectory. Shows the exact folder your terminal is currently inside.
* `cd [path]` : **C**hange **D**irectory. Moves you into a different folder.
  * `cd /` moves to the absolute root.
  * `cd ..` moves up one level to the parent directory.
* `ls` : **L**i**s**t. Shows all files and folders in your current directory.
* `cat [filename]` or `less [filename]` : Prints the contents of a text file directly into the terminal.
* `man [command]` : Opens the **man**ual/documentation for a specific command (e.g., `man ls`).

**Creating, Moving, & Deleting**
* `mkdir [name]` : **M**a**k**e **Dir**ectory. Creates a new folder.
* `touch [filename]` : Creates a new, empty file (e.g., `touch index.html`).
* `mv [old-name] [new-name]` : **M**o**v**e. Renames a file or moves it to a new location.
* `cp [source] [destination]` : **C**o**p**y. Duplicates a file. To copy a whole folder, you must use `cp -r`.
* `rm [filename]` : **R**e**m**ove. Deletes a file. 
  * `rm -r` deletes a folder and everything inside it.
  * `rm -f` forces deletion of protected files.

**Output to Files**
* `echo "text"` : Prints text to the terminal like a `console.log`.
* `echo "text" > file.txt` : Creates (or completely overwrites) a file with the string.
* `echo "text" >> file.txt` : Appends the string to the end of the file without overwriting.

---

## 8. Command Options & Flags

Options (or flags) modify how a command behaves. You can usually find a command's available flags by typing `[command] --help`.

**Short-Form Options (`-`)**
Typically a single hyphen followed by a single letter. Values are separated by a space.
* Example: `ls -a` (Lists all files, including hidden ones).
* Example with a value: `ls -w 50` (Sets width to 50).
* **Chaining:** You can combine multiple short flags into one block. `ls -a -h -s` can be written quickly as `ls -ahs`.

**Long-Form Options (`--`)**
Typically two hyphens followed by a full word. Values are attached using an equals sign (`=`).
* Example: `ls --all`
* Example with a value: `ls --width=50`
