# Relationaldb-concept-notes
My master study guide and reference notes for Relational Databases.
(learning Markdown to do this as well lol) 

---

## Table of Contents
* [1. Code Editors vs. IDEs](#1-code-editors-vs-ides)
* [2. Workspaces & CLI Basics](#2-workspaces--cli-basics)
* [3. Essential VS Code Shortcuts](#3-essential-vs-code-shortcuts)
* [4. Recommended VS Code Extensions](#4-recommended-vs-code-extensions)
* [5. Terminal vs. Command Line vs. Shell](#5-terminal-vs-command-line-vs-shell)
* [6. Essential Terminal Shortcuts](#6-essential-terminal-shortcuts)
* [7. Basic Bash Commands (File Navigation & Creation)](#7-basic-bash-commands-file-navigation--creation)
* [8. Command Options & Flags](#8-command-options--flags)
* [9. Relational vs. Non-Relational Databases](#9-relational-vs-non-relational-databases)
* [10. Common Relational Databases](#10-common-relational-databases)
* [11. Core SQL & Database Setup](#11-core-sql--database-setup)
* [12. Essential SQL Data Types](#12-essential-sql-data-types)
* [13. Inserting & Querying Data](#13-inserting--querying-data)
* [14. Primary & Foreign Keys](#14-primary--foreign-keys)
* [15. Database Relationships](#15-database-relationships)
* [16. SQL JOIN Operations](#16-sql-join-operations)
* [17. Bash Scripting Fundamentals](#17-bash-scripting-fundamentals)
* [18. Database Normalisation](#18-database-normalisation)
* [19. Security: SQL Injection](#19-security-sql-injection)
* [20. Performance: The N+1 Problem](#20-performance-the-n+1-problem)
* [21. CLI Text Editing: Working with Nano](#21-cli-text-editing-working-with-nano)

---

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

---

## 17. Bash Scripting Fundamentals

Bash scripting involves writing a sequence of terminal commands in a file that can be executed automatically as a single script.

**Advantages of Bash Scripting**
* **No Setup Required:** Bash is pre-installed on nearly every Unix environment (no need to configure Node.js or Python runtimes).
* **System Access:** You have immediate, built-in access to all binary applications installed on the system.
* **Terminal Testable:** Any syntax written in a Bash script can be copied and pasted directly into the command line to test it instantly.

### Anatomy of a Bash Script
A script typically starts with a "shebang" and executes commands sequentially, often using loops, arrays and variables.

    #!/bin/bash
    servers=("prod" "dev")
    
    for server in "${servers[@]}"
    do
      echo "Pulling $server"
      rsync --archive --verbose $server:/etc/nginx/conf.d/server.conf configs/$server.conf
    done

**Syntax Breakdown:**
* `#!/bin/bash` : The **Shebang**. This must be the absolute first line of the file. It tells the system which interpreter to use to run the script.
* `servers=("prod" "dev")` : Creates an array (list) of strings.
* `for server in "${servers[@]}"` : Initiates a loop. The `[@]` syntax expands the array so the loop iterates through every single item.
* `do ... done` : The logical block of the loop. Everything inside here runs once per item.
* `$server` : **Variable Interpolation**. Adding the `$` sign injects the current value of the variable into the command.

---

## 18. Database Normalisation

Normalisation is the process of organizing a relational database to reduce data redundancy and improve data integrity by dividing data into smaller linked tables.

**Key Terminology:**
* **Superkey:** Any set of columns that uniquely identifies a row.
* **Candidate Key:** A superkey with the *minimum* number of columns necessary to uniquely identify a row.

**The Normal Forms (With Examples):**

* **First Normal Form (1NF):** * Values must be atomic (one value per cell).
  * *Example:* If a student has two phone numbers, do not store them as `555-0100, 555-0101` in a single cell. Create a separate `phone_numbers` table.

* **Second Normal Form (2NF):**
  * Must be in 1NF.
  * **Rule:** No Partial Dependencies. Non-key attributes must depend on the *entire* primary key.
  * *Visual Example:* An `orders` table with a composite primary key (`order_id` + `item_id`).
    * **Bad:** Storing `order_shipping_city` in this table. The city only depends on the `order_id`, not the specific `item_id`.
    * **Fixed (2NF):** Split into two tables: `order_header` (holding the ID, date, and city) and `order_items` (holding the ID, item, and quantity).

* **Third Normal Form (3NF):**
  * Must be in 2NF.
  * **Rule:** No Transitive Dependencies. A non-key attribute cannot depend on another non-key attribute.
  * *Visual Example:* * **Bad:** `order_id` -> `customer_id` -> `customer_city` -> `city_postal_code`. 
    * The zip code relies on the city, not the order. If the city's zip code changes, you'd have to update hundreds of order rows.
    * **Fixed (3NF):** Split into three separate tables: `Orders`, `Customers`, and `Cities`.

---

## 19. Security: SQL Injection

**SQL Injection** is a critical vulnerability where attackers input malicious SQL code into web forms or URLs to manipulate your database.

**Visual Example:**
Imagine an app that authenticates users by directly concatenating their input into the query:
`SELECT * FROM users WHERE username = ' + input + '`

If an attacker types this into the username box: `" " OR "1"="1" --`
The database reads it as: `WHERE username = " " OR TRUE`
*(Because 1 always equals 1, the database returns TRUE and logs the attacker in without a password. The `--` comments out the rest of your security checks!)*

**Prevention Best Practices:**
1. **Parameterized Queries:** Never use string concatenation for user input. This separates the SQL structure from the data so it cannot be executed.
2. **Principle of Least Privilege:** Never connect your web app using a database Admin account.

---

## 20. Performance: The N+1 Problem

The **N+1 Problem** is a severe performance bottleneck caused by making multiple database queries inside a loop instead of grabbing all necessary data at once. 

**Visual Example: The Food Delivery App**
You need to load the 50 most recent orders plus the names of the customers who placed them.

**The Bad Way (N+1):**
1. You make **1** query to get the list of 50 orders.
2. You loop through those orders, making **N** (50) separate queries to look up each customer.

    for (const order of orders) {
      // This hits the database 50 individual times!
      const customerData = await getCustomerData(order.customer_id); 
    }

**The Solution:**
Avoid loops entirely. Use an SQL **`JOIN`** operation to combine the tables and fetch all 50 orders AND their related customer data in one single, highly efficient trip to the database.

---

## 21. CLI Text Editing: Working with Nano

When working on a remote server or in the terminal, graphical text editors aren't always available. **Nano** is a streamlined user-friendly CLI text editor (compared to the steep learning curve of Vim or the heavy shortcut reliance of Emacs). While it lacks the extensibility of Vim, it is perfect for quick and immediate edits.

**Opening a file:**
`nano <filename>`

**The Nano Interface:**
* **Top:** Displays the Nano version and current file name.
* **Middle:** The file content (navigate using arrow keys).
* **Bottom:** The shortcut menu. 
  * A caret (`^`) means hold the **Ctrl** key.
  * An `M-` means hold the **Meta** key (usually the **Alt** key).

**Essential Nano Shortcuts:**
* `Ctrl + O` (`^O`): **Write Out** (Save). It will prompt for a file name—press `Enter` to confirm or `Ctrl + C` to cancel.
* `Ctrl + X` (`^X`): **Exit**. If you have unsaved changes, it will prompt you: press `Y` to save or `N` to discard.
* `Ctrl + K` (`^K`): **Cut** the current line (often used to quickly delete a whole line).
* `Ctrl + U` (`^U`): **Uncut** (Paste) the text you just cut.
* `Ctrl + W` (`^W`): **Where is** (Search the document for a specific word).

**The Standard Git Commit Flow in Nano:**
Git often defaults to Nano if you run `git commit` without an inline message. 
1. Type your commit message at the top of the file.
2. Press `Ctrl + O`, then `Enter` to save the message.
3. Press `Ctrl + X` to exit Nano. Git will automatically complete the commit.

---
