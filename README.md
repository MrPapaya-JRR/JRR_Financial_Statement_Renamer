# JRR financial statement renamer

A friendly tool to automatically rename your bank statements, credit card statements, and brokerage documents with consistent, organized filenames.

---

## What does this program do?

Ever download bank statements with confusing names like “document.pdf” or “20251021-Bank statement.pdf”? This program automatically renames them to organized formats like “CapitalOne 2025-10 Bank.pdf” or “ETrade 2025-10 Statement.pdf”.

You create simple rules that tell the program how to recognize and rename your files. Once set up, renaming is just a few clicks away!

---

## Getting started

### First run
- **Config file:** On first start, a default configuration file named “JRR_Financial_Statement_Renamer.ini” is created with example rules.

### The main window
- **Tabs:**
  - **Single file:** Process one file at a time
  - **Folder:** Process all files in a folder at once
  - **Rules:** View and edit your renaming rules
  - **Watch folder:** Automatically process new files as they arrive
  - **Settings:** Choose your preferred color theme
  - **Help:** Built-in instructions
  - **About:** Program information

### Activity log
- **Location:** Bottom of the window
- **Color-coding:**
  - **Green:** Success
  - **Red:** Error
  - **Orange:** Warning
  - **Cyan/Blue:** Information

---

## How to rename files

### Method 1: Single file tab
1. **Open:** Click the “Single File” tab  
2. **Select file:** Click “Browse…” or drag-and-drop your file into the window  
3. **Process:** Click “Process File”  
4. **Preview:** The program shows the new name  
5. **Confirm:** Click “Yes” to rename

- **If multiple rules match:** You’ll be asked which rule to use and to specify the date (often “LAST MONTH” for monthly statements).

### Method 2: Folder tab
1. **Open:** Click the “Folder” tab  
2. **Select folder:** Click “Browse…” or drag-and-drop a folder into the window  
3. **Process:** Click “Process Folder”  
4. **Confirm:** The program will ask you to confirm each rename

- **Convenience:** Remembers your last used folder.

### Method 3: Watch folder tab
1. **Open:** Click the “Watch Folder” tab  
2. **Choose location:** Enter or browse to the folder to monitor  
3. **Auto mode:** Check “Auto-process files” to rename automatically  
4. **Start:** Click “Start Watching”  
5. **Stop:** Click “Stop Watching” when you’re done

- **Frequency:** Checks for new files every 2 seconds and either auto-renames or logs activity.

---

## Creating and managing rules

### Rule parts
- **Pattern:** What to look for in the filename
- **Template:** What the new filename should be
- **Description:** A friendly name for the rule

### Viewing rules
- **Access:** Click the “Rules” tab to see description, pattern, and template for each rule.

### Adding a new rule
1. **Open:** Click the “Rules” tab  
2. **Add:** Click “Add Rule”  
3. **Fill fields:**  
   - **Pattern example:** YYYYMMDD-Bank statement.pdf  
   - **Template example:** CapitalOne YYYY-MM Bank.pdf  
   - **Description example:** Capital One Bank Statement  
4. **Save:** Click “OK”

- **Storage:** Rules are saved automatically to the configuration file.

### Editing a rule
1. **Select:** Click the “Rules” tab and choose a rule  
2. **Edit:** Click “Edit Rule,” make changes, then click “OK”

### Deleting a rule
1. **Select:** Click the “Rules” tab and choose a rule  
2. **Delete:** Click “Delete Rule” and confirm

### Reloading rules
- **Manual changes:** If you edit the .ini file directly, click “Reload Config” to refresh.

---

## Understanding patterns and templates

### Special placeholders
- **YYYY:** 4-digit year (like 2025)
- **MM:** 2-digit month (01–12)
- **DD:** 2-digit day (01–31)
- **\*:** Wildcard (matches any text)

### Pattern examples
- **YYYYMMDD-Bank statement.pdf**
  - **Matches:** 20251021-Bank statement.pdf
  - **Matches:** 20250315-Bank statement.pdf
- **document.pdf**
  - **Matches:** Any file named exactly “document.pdf”
- **\*-Visa statement.pdf**
  - **Matches:** 20251021-Visa statement.pdf
  - **Matches:** October-Visa statement.pdf
  - **Matches:** anything-Visa statement.pdf

### Template examples
- **CapitalOne YYYY-MM Bank.pdf**
  - **Creates:** CapitalOne 2025-10 Bank.pdf
- **ETrade YYYY-MM Statement.pdf**
  - **Creates:** ETrade 2025-10 Statement.pdf
- **BOA YYYY-MM Visa-\*.pdf**
  - **Creates:** BOA 2025-10 Visa-20251021.pdf  
  - **Note:** The wildcard is replaced by whatever matched in the pattern.

### Complete rule examples
- **Pattern:** YYYYMMDD-Bank statement.pdf  
  **Template:** CapitalOne YYYY-MM Bank.pdf  
  **Result:** 20251021-Bank statement.pdf → CapitalOne 2025-10 Bank.pdf

- **Pattern:** document.pdf  
  **Template:** Schwab YYYY-MM Brokerage.pdf  
  **Result:** document.pdf → Schwab 2025-10 Brokerage.pdf  
  **Note:** You’ll be asked to enter a date since “document.pdf” has none.

- **Pattern:** statement\*.pdf  
  **Template:** Fidelity YYYY-MM Statement.pdf  
  **Result:** statement_oct.pdf → Fidelity 2025-10 Statement.pdf

---

## Handling files with no date

Some institutions use generic filenames like “document.pdf” or “statement.pdf.” If no date is found in the filename, you’ll be prompted to provide one.

### Date options
- **Quick select (recommended):**
  - **LAST MONTH:** Common for statements
  - **THIS MONTH:** Current month
- **Manual select:**
  - **Year:** Choose from a dropdown
  - **Month:** Choose from a dropdown with full month names

- **Default:** LAST MONTH (since statements often arrive the month after the period).

---

## Handling multiple matching rules

When more than one rule matches a filename, a dialog lets you:
1. **See:** All matching rules
2. **Preview:** The new filename for each rule
3. **Select:** Which rule to use
4. **Specify:** The date

---

## Configuration file

### Location and name
- **File:** “JRR_Financial_Statement_Renamer.ini”
- **Location:** Same folder as the program

### Editing
- **Direct editing:** Possible via Notepad
- **Recommendation:** Use the built-in “Rules” tab for ease

### Format
- **Line structure:** Pattern|Template|Description

- **Example:**
  - YYYYMMDD-Bank statement.pdf|CapitalOne YYYY-MM Bank.pdf|Capital One Bank

### Additional settings
- **WATCHFOLDER:** Your watch folder location
- **LASTFOLDER:** The last folder you processed

---

## Color themes

### Available themes
1. **Light (default):** Classic Windows look with white background
2. **Dark:** Modern dark mode with dark gray background
3. **Solarized:** Warm, easy-on-the-eyes beige tones
4. **High contrast:** Black background with white text
5. **Blue:** Blue-tinted interface

### Changing themes
1. **Open:** Click the “Settings” tab
2. **Select:** Choose your theme from the dropdown
3. **Apply:** Click “Apply Theme”

- **Persistence:** Your theme choice is saved for next time.

---

## Window size and position

- **Persistence:** The program remembers your window size when you drag to resize.
- **Storage:** Window size settings are saved in “WindowSize.ini.”

---

## Log files

### Activity log (in-app)
- **Purpose:** Real-time view of actions
- **Features:** Color-coded, can be cleared
- **Persistence:** Not saved between sessions

### Permanent log file
- **File:** “JRR_Financial_Statement_Renamer_LOG.txt”
- **Contents:** Timestamps, old filename, new filename, status
- **Note:** The file grows over time; you can delete it if it gets too big.

---

## Tips and best practices

1. **Test first:** Try rules on one or two files using Single File tab  
2. **Use descriptive names:** Clear labels like “Chase Credit Card,” “Vanguard 401k Statement”  
3. **Start simple:** Begin with basic patterns; add wildcards only if needed  
4. **Organize by institution:** One rule per institution or account type  
5. **Backup important files:** Make a copy before batch processing  
6. **Use the watch folder:** Auto-rename as soon as files download  
7. **Consistent naming:** Use formats like “[Institution] YYYY-MM [Type].pdf” for clarity

---

## Common patterns for popular institutions

### Bank of America
- **Pattern:** eStmt_\*.pdf  
- **Template:** BOA YYYY-MM Statement.pdf

### Chase
- **Pattern:** \*_Statement.pdf  
- **Template:** Chase YYYY-MM Statement.pdf

### Discover
- **Pattern:** Discover-Statement-\*.pdf  
- **Template:** Discover YYYY-MM Statement.pdf

### Capital One
- **Pattern:** YYYYMMDD-\*.pdf  
- **Template:** CapitalOne YYYY-MM Statement.pdf

### Schwab / ETrade / Fidelity (generic downloads)
- **Pattern:** document.pdf  
- **Template:** [InstitutionName] YYYY-MM Statement.pdf

- **Note:** Customize based on the actual filenames your institution uses.

---

## Troubleshooting

- **Program won’t start or says already running:** Only one copy can run at a time; close the other window.  
- **No rules match my files:** Ensure your pattern exactly matches the filename. Patterns are case-insensitive, but spelling and punctuation must match (except placeholders).  
- **Program renamed my file incorrectly:** Check your template placeholders (use uppercase YYYY, MM, DD). Review the permanent log file to see what happened.  
- **Watch folder isn’t detecting new files:** Click “Start Watching,” verify the folder path, and note the 2-second check interval.  
- **Don’t like the colors:** Try a different theme in the Settings tab.  
- **Window too small/too big:** Drag edges to resize; preference is saved.  
- **Accidentally deleted a rule:** If the program is still open, manually edit the .ini file to restore. Otherwise, recreate the rule.

---

## Keyboard shortcuts

- **Tab:** Move between fields in dialogs  
- **Enter:** Click OK/default button  
- **Escape:** Cancel/close dialogs  
- **Alt+F4:** Close the program

---

## Uninstalling

To remove the program:
1. **Delete:** JRR_Financial_Statement_Renamer.exe  
2. **Optional:** Delete configuration files if you don’t want to keep your rules:
   - JRR_Financial_Statement_Renamer.ini
   - WindowSize.ini
   - ThemePreference.ini
   - JRR_Financial_Statement_Renamer_LOG.txt

- **Note:** No registry entries or hidden files are used.

---

## Support and feedback

- **GitHub:** https://github.com/MrPapaya-JRR  
- **Releases page:** Leave a message on the release page  
- **Forum:** Contact the author on RadioDJ.ro forums (username: JackRabbit)  
- **Tips:** https://ko-fi.com/mrpapaya

---

## License

This program is released as FREEWARE. You may:
- **Use:** For personal or commercial purposes  
- **Share:** Distribute as-is  
- **Modify:** For your own use (if you have the source code)

You may NOT:
- **Sell:** The program  
- **Distribute:** Modified versions publicly

© 2025 JackRabbit Radio Software

---

## Version history

- **v1.23:** Added color theme selection tab  
- **v1.22:** Integrated color theme system  
- **v1.21:** Improved handling when program is already running  
- **v1.20:** Enhanced color-coded logging  
- **v1.19:** Added color-coded activity log messages  
- **v1.18:** Window size persistence between sessions  
- **v1.17:** Enhanced month selection dialog, auto-scroll activity log  
- **v1.16:** Improved date entry with dropdown menus, remembers last folder  
- **v1.15:** Fixed pattern matching bug  
- **v1.14:** Added drag-and-drop support for Single File tab  
- **v1.13:** Added date input fields for files without dates  
- **v1.12:** Added support for generic filenames like “document.pdf”  
- **v1.11:** Added dynamic window resizing and improved help text  
- **v1.10:** All functions made functional  
- **v1.00:** Initial release with basic GUI

---

Thank you for using JRR Financial Statement Renamer!  
May all your files be perfectly organized. :)
