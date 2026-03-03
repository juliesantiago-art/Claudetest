# Using GitHub + Claude.ai for Work: A Complete Onboarding Guide

**You don't need to be a programmer to use these tools together.**

This guide is for everyone — whether you've never written a line of code or you're a developer who just wants a quick reference. By the end, you'll know how to use Claude.ai to fix or understand code and save your work safely on GitHub.

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Before You Start (One-Time Setup)](#2-before-you-start-one-time-setup)
3. [Key Concepts in Plain English](#3-key-concepts-in-plain-english)
4. [Core Workflow — Non-Technical Path](#4-core-workflow--non-technical-path)
5. [Core Workflow — Technical Path](#5-core-workflow--technical-path)
6. [Example 1: Fixing a Python Bug (Non-Tech Path)](#6-example-1-fixing-a-python-bug-non-tech-path)
7. [Example 2: Fixing a JavaScript Bug (Technical Path)](#7-example-2-fixing-a-javascript-bug-technical-path)
8. [Example 3: Understanding Unfamiliar Code](#8-example-3-understanding-unfamiliar-code)
9. [Tips & Best Practices](#9-tips--best-practices)
10. [Common Mistakes & How to Avoid Them](#10-common-mistakes--how-to-avoid-them)

---

## 1. Introduction

### What is GitHub?

Think of GitHub as a **filing cabinet for code** — but a magical one that:
- Stores every version of every file, forever
- Tracks who changed what, and when
- Lets multiple people work on the same project without overwriting each other
- Lets you undo mistakes by going back to any earlier version

You access it through your web browser at [github.com](https://github.com), just like email. No installation required for basic use.

### What is Claude.ai?

Claude.ai is an **AI assistant you talk to in plain English**. You can paste code into the chat window, describe what's wrong, and Claude will explain the problem and suggest a fix — in plain language you can actually understand, not just technical jargon.

You don't need to know how to code to use Claude.ai. You just need to be able to copy and paste.

### Why Use Them Together?

| Without these tools | With these tools |
|---|---|
| Email code snippets back and forth | Claude fixes it; GitHub saves it |
| No record of what changed | Every change is tracked automatically |
| Fear of breaking something | Every version is saved; nothing is truly lost |
| Need a developer for every small fix | Claude explains and fixes; you commit the change |

### The Mental Model

```
You → Claude.ai → get the fix → GitHub → saved safely ✓
       (ask in plain English)    (paste & commit)
```

---

## 2. Before You Start (One-Time Setup)

You only need to do this once.

### Everyone

**Step 1: Create a free GitHub account**
1. Go to [github.com](https://github.com)
2. Click the green **"Sign up"** button in the top right
3. Enter your work email address and create a password
4. Follow the prompts — choose the free plan when asked

**Step 2: Sign in to Claude.ai**
1. Go to [claude.ai](https://claude.ai)
2. Sign in with your work email (or create a free account)
3. You'll land on a chat screen — this is where you'll paste code and ask questions

---

### Non-Technical Users: Install GitHub Desktop

GitHub Desktop is a **visual app** that lets you work with GitHub without ever opening a terminal or typing commands. It shows you exactly what changed, with checkboxes and buttons instead of typed commands.

1. Go to [desktop.github.com](https://desktop.github.com)
2. Click **"Download for Mac"** (or Windows)
3. Open the downloaded file and drag it to your Applications folder
4. Open GitHub Desktop and sign in with your GitHub account

> **What you'll see:** A window with your repositories listed on the left and file changes shown on the right. There's a big blue "Commit" button at the bottom left — that's how you save your work.

---

### Technical Users: Git CLI

If you already have Git installed (`git --version` returns something), you're good. Make sure you're authenticated:

```bash
git config --global user.name "Your Name"
git config --global user.email "you@company.com"
```

---

## 3. Key Concepts in Plain English

You'll see these words throughout this guide. Here's what they actually mean:

| Term | Plain-English Definition |
|---|---|
| **Repository (repo)** | A project folder stored on GitHub. Like a shared Google Drive folder, but for code, with full version history. |
| **Commit** | Saving a snapshot of your changes with a short note about what you did. Like "Save As" but it keeps every previous save too. |
| **Branch** | A copy of the project where you can try changes safely without affecting the real version. Like a scratch pad. |
| **Pull Request (PR)** | A way to propose your changes to the team before they go live. Others can review and approve before anything changes. |
| **Bug** | Something in the code that makes it behave incorrectly — like a formula in a spreadsheet that returns the wrong number. |
| **Push** | Sending your saved commits up to GitHub so others can see them (and so they're safely backed up). |
| **Clone** | Downloading a copy of a GitHub repository to your own computer. |

---

## 4. Core Workflow — Non-Technical Path

**Use this if:** You are not a developer, or you prefer working in a browser without installing anything beyond GitHub Desktop.

### Step-by-Step: Fix a File on GitHub

1. **Find the file on GitHub**
   - Open your repository page on github.com
   - Click through folders until you see the file you need to change
   - Click the file name to open it

2. **Open the web editor**
   - Look for the **pencil icon** (✏️) near the top right of the file view
   - Click it — the file will open in an editable text box right in your browser
   > **What you'll see:** The file contents become editable, like a basic text editor. A green "Commit changes" button appears at the top right.

3. **Copy the broken code**
   - Select and copy the section of code that has the problem (Ctrl+C / Cmd+C)

4. **Open Claude.ai in a new tab**
   - Press Ctrl+T (or Cmd+T on Mac) to open a new browser tab
   - Go to [claude.ai](https://claude.ai)

5. **Describe the problem and paste the code**
   - Type a message to Claude explaining what the code should do, what it actually does, and paste the code
   - See [Section 6](#6-example-1-fixing-a-python-bug-non-tech-path) for a copy-paste ready prompt example

6. **Copy Claude's fixed version**
   - Claude will respond with corrected code in a gray code block
   - Click the **copy icon** that appears in the top right of the code block

7. **Paste the fix back into GitHub**
   - Switch back to the GitHub tab
   - Select the old (broken) code in the editor and replace it with Claude's version (Ctrl+V / Cmd+V)

8. **Write a short commit message**
   - Scroll down on the GitHub page (or click "Commit changes")
   - In the text field labeled **"Commit message"**, write a short description like:
     `Fix overtime calculation always returning zero`

9. **Click "Commit changes"**
   - Press the green **"Commit changes"** button
   - Done! Your fix is saved and recorded in the project history.

> **What you'll see after committing:** The file view refreshes and shows the updated code. Your commit message appears in the file history.

---

## 5. Core Workflow — Technical Path

**Use this if:** You're a developer comfortable with the terminal.

```bash
# 1. Get the latest version of the code
git pull

# 2. Open Claude.ai, paste the code + error message, get the fix

# 3. Apply the fix to the file in your editor

# 4. Test locally to confirm the fix works

# 5. Stage, commit, and push
git add path/to/changed-file.py
git commit -m "Fix: correct overtime calculation logic"
git push
```

**Tip:** Always include the error message in your Claude prompt — not just the code. Claude diagnoses faster with the full picture.

---

## 6. Example 1: Fixing a Python Bug (Non-Tech Path)

### The Scenario

Your team has a Python script that calculates employee overtime pay. HR reported that it always returns $0.00 no matter how many hours someone worked. You need to find the bug and fix it.

### The Broken Code

```python
def calculate_overtime(hours_worked, hourly_rate):
    # Bug: always returns 0
    overtime_hours = 0
    if hours_worked > 40:
        overtime_hours = hours_worked - 40
    overtime_pay = overtime_hours * 1.5 * hourly_rate
    return overtime_pay

# Expected: calculate_overtime(45, 20) should return 150.0
# Actual:   calculate_overtime(45, 20) returns 0
```

### The Claude Prompt (Copy-Paste Ready)

> I have a Python function that should calculate overtime pay (hours over 40 × 1.5 × hourly rate) but it always returns 0. Here's the code:
>
> ```python
> def calculate_overtime(hours_worked, hourly_rate):
>     overtime_hours = 0
>     if hours_worked > 40:
>         overtime_hours = hours_worked - 40
>     overtime_pay = overtime_hours * 1.5 * hourly_rate
>     return overtime_pay
> ```
>
> Please fix it and explain what was wrong.

### Claude's Response

Claude will explain: *The logic is actually correct — the bug is likely that the function is being called with the wrong variable, or the result isn't being used. But in this exact snippet, if `hours_worked` is passed as a string like `"45"` instead of a number, the `> 40` comparison may fail silently. Let me give you a fixed version that handles this:*

```python
def calculate_overtime(hours_worked, hourly_rate):
    hours_worked = float(hours_worked)   # ensure it's a number
    hourly_rate = float(hourly_rate)     # ensure it's a number
    if hours_worked > 40:
        overtime_hours = hours_worked - 40
        return overtime_hours * 1.5 * hourly_rate
    return 0.0

# Test: calculate_overtime(45, 20) now correctly returns 150.0
```

### GitHub Web Editor Steps

1. Open the file (e.g., `payroll.py`) on github.com and click the **pencil icon** (✏️)
2. Find the old `calculate_overtime` function
3. Select it entirely and replace it with Claude's fixed version
4. Scroll down to **"Commit changes"**
5. In the commit message box, type:
   ```
   Fix overtime calculation to handle string input types
   ```
6. Click the green **"Commit changes"** button

Your fix is now saved. The previous (broken) version is preserved in history — you can always go back.

---

## 7. Example 2: Fixing a JavaScript Bug (Technical Path)

### The Scenario

A button on the company's internal web tool doesn't do anything when clicked. The developer who built it is on vacation. You need to find and fix the bug.

### The Broken Code

```javascript
// In app.js
document.querySelector('.submit-btn').addEventListener('click', function() {
    var formData = document.querySelector('#expense-form').value;
    submitExpense(formData);
});

function submitExpense(data) {
    console.log('Submitting:', data);
    fetch('/api/expenses', {
        method: 'POST',
        body: data
    });
}
```

### Browser Console Error

```
Uncaught TypeError: Cannot read properties of null (reading 'addEventListener')
    at app.js:2
```

### The Claude Prompt (Copy-Paste Ready)

> This JavaScript click handler isn't firing. Here's the code and the error from the browser console:
>
> **Code (app.js):**
> ```javascript
> document.querySelector('.submit-btn').addEventListener('click', function() {
>     var formData = document.querySelector('#expense-form').value;
>     submitExpense(formData);
> });
> ```
>
> **Error:**
> ```
> Uncaught TypeError: Cannot read properties of null (reading 'addEventListener')
>     at app.js:2
> ```
>
> What's wrong and how do I fix it?

### Claude's Fix and Explanation

Claude will explain: *The script runs before the HTML is fully loaded, so `document.querySelector('.submit-btn')` returns `null` — the button doesn't exist yet when the JavaScript tries to attach the listener. Wrap the code in a `DOMContentLoaded` event:*

```javascript
// Fixed app.js
document.addEventListener('DOMContentLoaded', function() {
    document.querySelector('.submit-btn').addEventListener('click', function() {
        var formData = document.querySelector('#expense-form').value;
        submitExpense(formData);
    });
});

function submitExpense(data) {
    console.log('Submitting:', data);
    fetch('/api/expenses', {
        method: 'POST',
        body: data
    });
}
```

### Git Commands to Commit and Push

```bash
# Make sure you have the latest code
git pull

# Apply Claude's fix to app.js, then:
git add app.js
git commit -m "Fix: wrap click handler in DOMContentLoaded to prevent null error"
git push
```

---

## 8. Example 3: Understanding Unfamiliar Code

### The Scenario

You inherited a repository and found a function that no one documented. You need to understand what it does before deciding whether to change it.

### The Confusing Code

```python
def proc(records, cutoff=90):
    out = []
    seen = set()
    for r in sorted(records, key=lambda x: x['ts'], reverse=True):
        uid = r.get('user_id')
        if uid not in seen and (time.time() - r['ts']) < cutoff * 86400:
            out.append(r)
            seen.add(uid)
    return out
```

### The Claude Prompt (Copy-Paste Ready)

> Can you explain what this code does in simple terms, like I'm not a programmer? Also tell me if there's anything I should watch out for before changing it.
>
> ```python
> def proc(records, cutoff=90):
>     out = []
>     seen = set()
>     for r in sorted(records, key=lambda x: x['ts'], reverse=True):
>         uid = r.get('user_id')
>         if uid not in seen and (time.time() - r['ts']) < cutoff * 86400:
>             out.append(r)
>             seen.add(uid)
>     return out
> ```

### Claude's Plain-English Explanation

Claude will respond with something like:

> This function filters a list of records (like activity logs) and returns only the **most recent record per user**, as long as that record is from the **last 90 days** (by default).
>
> Here's what it does step by step:
> 1. It sorts all records from newest to oldest
> 2. It goes through each record and checks two things:
>    - Has it already seen a record for this user? (If yes, skip it)
>    - Is this record less than 90 days old? (If no, skip it)
> 3. It keeps only the first (most recent) qualifying record per user
>
> **Watch out for:** The function name `proc` is vague — consider renaming it to `get_latest_active_users` so the next person knows what it does. Also, if `records` contains entries without a `user_id` field, those entries are silently dropped.

### How This Helps You

Now you know:
- What the function is supposed to do
- What edge cases to watch for
- Whether it's safe to change (and where to be careful)

This is exactly the kind of context that helps you make a safe, informed commit — rather than guessing and potentially breaking something.

---

## 9. Tips & Best Practices

**For everyone:**

- **Always paste the error message, not just the code.** Claude needs the full picture — the error tells it exactly where things went wrong. Code alone often isn't enough.

- **Ask Claude to explain the fix.** After getting corrected code, ask: *"Can you explain why this fix works?"* This is how you learn as you go, even without a programming background.

- **Write descriptive commit messages.** Compare:
  - Bad: `fix`
  - Good: `Fix overtime calculation rounding error for part-time employees`

  Commit messages are how your team (and future you) will understand what changed and why.

- **Never commit directly to `main` if your team has branch policies.** When in doubt, ask your team lead whether you should create a branch first. GitHub will usually warn you if there's a branch protection rule.

- **Review Claude's suggestion before committing.** Claude is accurate the vast majority of the time, but you're the final check. Read the fix and make sure it makes sense for your situation before saving it.

---

## 10. Common Mistakes & How to Avoid Them

### "I pasted the code but Claude gave a generic answer"

**Why it happens:** Claude doesn't have enough context to give a specific fix.

**How to fix it:** Add more detail to your prompt:
- What programming language is this? (Python, JavaScript, etc.)
- What should the code do?
- What does it actually do instead?
- Copy the exact error message from the terminal or browser console

The more specific you are, the more specific Claude's answer will be.

---

### "I committed but my changes aren't showing up"

**Why it happens:** You committed locally but didn't push to GitHub (technical path), or you thought you clicked "Commit changes" but the page didn't refresh.

**How to fix it:**
- **Technical:** Run `git push` — the commit is saved locally but not yet sent to GitHub
- **Non-technical:** Check that the page refreshed after clicking "Commit changes" and that your commit message appears in the file history. If not, try again.

---

### "I broke something"

**Don't panic.** This is exactly what GitHub is for.

GitHub saves every version of every file forever. Nothing is truly lost. Here's what to do:

1. Open the file on GitHub
2. Click **"History"** (usually near the top right of the file view) to see every past version
3. Find the last version that worked
4. Ask Claude:
   > "How do I revert a file in GitHub to a previous commit? I don't have much technical experience."

Claude will walk you through it step by step.

---

*Questions or feedback about this guide? Open an issue on this repository or reach out to your team's onboarding contact.*
