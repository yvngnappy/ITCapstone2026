# 1. Use CLI Interface Instead of GUI or Web
 
**Status:** Approved  
**Date:** 2026-11-11
 
## Context
 
We needed a user interface for the Phishing Email Checker. The options considered were: 
- A graphical user interface (GUI) using a toolkit like Tkinter.
- A web-based interface (e.g., a Flask or Django app).
- A text-based command-line interface (CLI) with menu options.
 
A GUI or web app would allow more user-friendly interaction but would significantly increase development time and add dependencies (like a web framework or GUI library). Since this is a simple tool primarily for demonstration and quick use, we opted for a CLI to keep the project lightweight and easy to run on any machine with Python.
 
## Decision
 
We will use a command-line interface with a numbered menu. The program runs in a terminal and prompts the user to choose actions (enter or load an email, display or save reports, etc.).
 
## Consequences
  
- Easier: 
  - Quicker and simpler to implement with standard Python (`input()` and `print()`).  
  - No extra libraries or frameworks required (no GUI toolkit or web server).  
  - Runs in any terminal on Windows, macOS, or Linux without special setup.
- Harder:
  - Less intuitive for non-technical users who prefer graphical interfaces.  
  - Limited formatting and no graphics (everything is text-based).  
  - Can't show email content with rich formatting or clickable links (user sees raw URLs).
```
