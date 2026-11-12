# Fresh Clone Test
 
## Tester
 
Charlie – 2026-11-11 – Tested on Ubuntu 20.04 LTS
 
## Result

**Pass**
 
## Problems Found
 
1. **Python version confusion:** The instructions said `python phishing_email_checker.py`, but on some systems `python` is Python 2. The tester initially got a `SyntaxError` until switching to `python3`.  
2. **Missing sample email file:** No example email file was included, so the tester had to create one. The instructions could mention creating a sample `.txt` as in Verify step.  
3. **Save report confusion:** The tester wasn’t sure what file extension to use for saving the report. After some guessing, used `.txt` successfully.
 
## Fixes Made
 
1. Updated the Quick Start instructions to use `python3` explicitly (commit [abc1234](#)).  
2. Added a note in `docs/setup.md` with an example of creating a `sample.txt` file (commit [def5678](#)).  
3. Clarified in Troubleshooting that the report file should have a `.txt` extension (commit [ghi9012](#)).
