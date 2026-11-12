# Setup Guide
 
This guide explains how to install and run the Phishing Email Checker from a fresh clone.
 
## Requirements
 
- Python 3.7 or higher (to use `email.policy.default` from the standard library)  
- Git (to clone the repository)

## Steps
 
1. Clone the repository and change into its directory:  
   ```bash
   git clone https://github.com/yvngnappy/ITCapstone2026/repo.git
   cd repo.git
   ```

2. (Optional but recommended) Create and activate a Python virtual environment:  
   ```bash
   python3 -m venv venv
   source venv/bin/activate   # On Windows: venv\Scripts\activate
   ```  

3. Install dependencies (none beyond the standard library, so this step is a placeholder if future packages are added):  
   ```bash
   pip install -r requirements.txt
   ```  

4. Run the program:  
   ```bash
   python phishing_email_checker.py
   ```
If your system requires `python3` instead of `python`, use that command.
 
5. Follow the on-screen menu to paste an email or load a file.
 
## Verify It Works
 
After running `python phishing_email_checker.py`, you should see a menu like this:

```
Phishing Email Checker
1. Enter an email message
2. Load an .eml or .txt file
3. Display email content
4. Save report
5. Clear current message
6. Exit
```

If you see the menu, the setup is correct. You can then test with option 1 by pasting a simple email (ending with `END`) or with option 2 by loading a `.txt` or `.eml` file. For example, create a file `sample.txt` with:

```
From: test@example.com
Subject: Greetings
Hello, visit http://example.com for more info.
```
 
Then choose option 2 and enter `sample.txt`. Choosing option 3 should display the parsed email and the link.
 
## Troubleshooting
 
1. **Python version issues:**  
   - *Problem:* Running `python phishing_email_checker.py` gives a syntax error or the program exits immediately.  
   - *Solution:* Ensure you are using Python 3. If your system’s `python` points to Python 2.x, try `python3 phishing_email_checker.py` instead.
 
2. **File not found or cannot open file:**  
   - *Problem:* When choosing “Load an .eml or .txt file”, you get `Could not open that file.` or a FileNotFoundError.  
   - *Solution:* Make sure the file path is correct and that the file is in the current directory or provide the full path. For example, if your file is in the same folder, just type `sample.txt`. If it’s elsewhere, give the full path like `/path/to/sample.txt`.
 
3. **No output or empty report:**  
   - *Problem:* After loading an email, choosing “Display email content” shows no links found or blank content.  
   - *Solution:* Check that the email file contains a clear `From:` and `Subject:` line and at least one `http://` or `https://` link. The program only finds plain text parts and HTTP(S) links via regex.
 
4. **Report file not saved:**  
   - *Problem:* When saving a report, no file is created or an error appears.  
   - *Solution:* Enter a valid filename with a `.txt` extension when prompted (e.g., `report.txt`). Ensure you have write permission in the directory. If you see `Could not save the report.`, try a different filename or directory where you have permission.

