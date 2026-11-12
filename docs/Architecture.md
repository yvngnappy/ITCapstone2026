# Architecture
 
## Overview
 
This command-line application is written in Python and uses standard libraries to parse email data and extract links. It consists of a menu-driven interface that allows a user to enter or load an email, analyze it for links, display the content, and save a report. The program does not connect to any external services and runs entirely locally.
 
## Components
 
| Part             | Job                                                  | Technology                 |
|------------------|------------------------------------------------------|----------------------------|
| CLI Menu         | Presents options and reads user input (1-6)          | Python `input()`/`print()` |
| Email Reader     | Opens and parses `.eml` or `.txt` email files        | Python `email` module      |
| Text Analyzer    | Extracts plain-text parts and searches for URLs      | Python `re` (regex)        |
| Report Generator | Displays the report on screen or writes it to a file | Python file I/O and `print`|
 
## Data Flow
 
1. **User selects “Load an .eml or .txt file” (Option 2):** The program asks for a file path.
2. **Email Parsing:** The chosen file is read by `read_email_file()`. If it’s `.eml`, the email parser extracts the “From” and “Subject” headers and the body text. If it’s `.txt`, lines starting with `From:` or `Subject:` are detected, and the rest is body.
3. **Storing Content:** The parsed sender, subject, and body text are stored in variables (`current_sender`, `current_subject`, `current_message`).
4. **Display Report (Option 3):** The user selects “Display email content”. The program calls `analyze_email(current_message)` to find all URLs using a regular expression.
5. **Print Report:** `print_report()` then prints a formatted report showing sender, subject, number of links, the list of links, and the full email content to the console.
6. **Save Report (Option 4):** If the user chooses to save, `save_report()` prompts for a filename, then writes the same information (with a timestamp) to that text file.
 
## Security Notes
 
- **No execution of email content:** The program only reads email content as text. It does not execute any embedded scripts or attachments, so it should not run malicious code from an email.
- **Malicious links:** Although the tool finds and lists links in emails, it does not check if they are malicious. Users should not click links from suspicious emails just because they appear in the report.
- **File handling:** The program handles `.eml` and `.txt` files only. It skips non-text attachments. However, parsing `.eml` files could still involve large or obfuscated content; users should ensure files come from trusted sources or scan them separately.
- **Sensitive data:** The report includes the full email content. If an email contains private information (passwords, personal data), that will be visible. Users should store or share report files securely and delete them if no longer needed.
- **Input validation:** The tool assumes well-formed input. Supplying malformed email data (especially as a text file) might result in missing fields. Always check the report output for accuracy and be cautious if something looks off.
```
