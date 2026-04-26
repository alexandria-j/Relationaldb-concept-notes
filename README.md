# Relationaldb-concept-notes
My master study guide and reference notes for Relational Databases.
(learning markdown to do this as well lol) 

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

---

## 9. Relational vs. Non-Relational Databases

* **Relational Databases:** Store data in structured tables (rows and columns). They require a strict **schema** (a defined structure of tables, columns and data types) and enforce data integrity through relationships.
* **Non-Relational Databases (NoSQL):** Store data in flexible, unconnected files or documents. They do not require a rigid schema, allowing fields to be added or removed on the fly.

---

## 10. Common Relational Databases

* **PostgreSQL:** Advanced, open-source, object-relational database known for high reliability, data integrity and custom data types.
* **MySQL:** Extremely popular, open-source database heavily used in web development.
* **SQLite:** Lightweight, serverless, file-based database that requires zero initial configuration.

---

## 11. Core SQL & Database Setup

SQL (Structured Query Language) commands typically end with a semicolon (`;`). Standard naming convention for tables and columns is `snake_case`.

**Connecting via Terminal**
* `psql -U <username> -d <database_name>` : Connect to a specific database.
* `\c <database_name>` : Switch to a different database while already inside the psql shell (No semicolon needed for `\` commands).

**Creating Databases & Tables**
Eg.
    CREATE DATABASE my_database;

    CREATE TABLE products (
      id SERIAL,
      name VARCHAR(255)
    );

---

## 12. Essential SQL Data Types

**Numeric**
* `INTEGER` : Standard whole number.
* `SERIAL` : Automatically increments by 1 for each new row (essential for creating unique IDs in PostgreSQL).

**Text / String**
* `VARCHAR(n)` : Variable-length string with a maximum character limit of `n`.
* `TEXT` : Strings of any length.

**Date & Time**
* `DATE` : Stores the calendar date.
* `TIME` : Stores the time of day.
* `TIMESTAMP` : Stores both date and time (Use `TIMESTAMP WITH TIME ZONE` for global data).

**Boolean**
* `BOOLEAN` : Stores `TRUE` or `FALSE`.

---

## 13. Inserting & Querying Data

**Example Setup:** A `dogs` table with `id`, `name`, and `age`.

**Inserting Data**
It is safest to explicitly state the column names so values are assigned correctly.

    INSERT INTO dogs (name, age) 
    VALUES 
      ('Gino', 3),
      ('Nora', 2);

**Querying Data (SELECT & WHERE)**
* `SELECT * FROM dogs;` : Retrieves all columns and all rows.
* `SELECT name, age FROM dogs;` : Retrieves only specific columns.
* `SELECT * FROM dogs WHERE age < 3;` : Filters for dogs younger than 3.
* `SELECT age FROM dogs WHERE name = 'Gino';` : Retrieves only Gino's age.

---

## 14. Primary & Foreign Keys

Keys enforce data integrity and create relationships between tables.

* **Primary Key:** Uniquely identifies a row. Cannot be `NULL` or duplicated. (e.g., `customer_id`).
* **Composite Primary Key:** A combination of two or more columns to create a unique identifier (e.g., `student_id` + `course_id` ensures a student isn't enrolled in the exact same class twice).
* **Foreign Key:** A column in one table that references the Primary Key of another table.

**Visual Example:**
Linking a customer to their specific order.

    CREATE TABLE orders (
      order_id SERIAL PRIMARY KEY,
      customer_id INTEGER,
      FOREIGN KEY (customer_id) REFERENCES customers(customer_id)
    );

---

## 15. Database Relationships

* **One-to-One:** Record A links to exactly one Record B.
  * *Example:* One `employee` is assigned exactly one `company_vehicle`.
* **One-to-Many / Many-to-One:** Record A links to multiple Record Bs.
  * *Example:* One `customer` can have many `orders`.
* **Many-to-Many:** Multiple records in Table A link to multiple records in Table B.
  * *Example:* An `author` writes multiple `books`, and a `book` can have multiple `authors`.
  * *How to solve:* You must create a **Junction Table** (e.g., `books_authors`) holding the IDs (Foreign Keys) from both tables to bridge the gap.
* **Self-Referencing (Recursive):** A record relates to another record in the exact same table.
  * *Example:* An `employees` table where an employee has a `manager_id` that links back to a different employee in the same table.

---

## 16. SQL JOIN Operations

JOINs allow you to combine data from multiple tables. 

**The Setup:**
Table A: `products` (1: Ice Cream, 2: Pizza, 4: T-Shirt)
Table B: `sales` (Product 1 was sold, Product 2 was sold)

* **INNER JOIN:** Returns only rows with a match in *both* tables.
  * *Visual Result:* Shows Ice Cream and Pizza. (T-Shirt is excluded because it wasn't sold).
* **FULL OUTER JOIN:** Returns all rows from *both* tables.
  * *Visual Result:* Shows Ice Cream, Pizza, and T-Shirt. (T-Shirt's "sale date" column will just be `NULL`).
* **LEFT JOIN:** Returns all rows from the *left* table (`products`), plus matched rows from the right (`sales`).
* **RIGHT JOIN:** Returns all rows from the *right* table (`sales`), plus matched rows from the left (`products`).

**Basic JOIN Syntax:**

    SELECT * FROM products 
    INNER JOIN sales 
      ON products.product_id = sales.product_id;
