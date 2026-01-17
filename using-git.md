---
layout: default
title: Git Workflow in JupyterLab
---

# Git Workflow in JupyterLab

This guide walks you through using Git in JupyterLab to save and version your work. No terminal required—everything uses the visual Git interface.

---

## One-Time Setup

### 1. Git Identity (Ask Your Instructor First)

The first time you try to commit, you may see an error:

```
Author identity unknown
*** Please tell me who you are.
```

**This is normal.** Send your instructor your name and email address. They will configure your Git identity on the server. Once done, you won't see this error again.

### 2. Create a GitHub Account

If you don't already have one:

1. Go to [github.com](https://github.com)
2. Click **"Sign up"**
3. Follow the prompts to create your account
4. Verify your email address

### 3. Create a Personal Access Token (PAT)

GitHub requires a token (not your password) for pushing from JupyterLab.

1. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
2. Click **"Tokens (classic)"** in the left sidebar
3. Click **"Generate new token"** → **"Generate new token (classic)"**
4. Fill in:
   - **Note:** `JupyterLab` (or any name to help you remember)
   - **Expiration:** 90 days (or your preference)
   - **Scopes:** Check the box for **`repo`**
5. Click **"Generate token"**
6. **COPY THE TOKEN NOW**—you won't see it again!
7. Save it somewhere safe (password manager, secure note, etc.)

---

## Cloning a Repository

"Cloning" downloads a copy of a repository to your JupyterLab workspace.

### Step 1: Get the Repository URL

1. Go to your repository on GitHub
2. Click the green **"Code"** button
3. Make sure **HTTPS** is selected
4. Copy the URL (looks like `https://github.com/washu-eeps/your-repo-name.git`)

### Step 2: Clone in JupyterLab

1. Open JupyterLab
2. Click the **Git icon** in the left sidebar (diamond shape with branches)
3. Click **"Clone a Repository"**
4. Paste the URL you copied
5. Click **"Clone"**
6. When prompted:
   - **Username:** Your GitHub username
   - **Password:** Paste your Personal Access Token (NOT your GitHub password)
7. A new folder will appear in your file browser with the repository name

---

## Daily Workflow

Once you've cloned a repository, here's how you save your work.

### Step 1: Open Your Notebook

1. In the file browser (folder icon), navigate into your repository folder
2. Double-click the notebook file to open it
3. Do your work!

### Step 2: Save Your Notebook

Press **Ctrl+S** (or **Cmd+S** on Mac) to save.

### Step 3: Stage Your Changes

1. Click the **Git icon** in the left sidebar
2. You'll see your changed files listed under **"Changed"**
3. Hover over the file and click the **"+"** button to stage it
4. The file moves to **"Staged"**

### Step 4: Commit Your Changes

1. In the Git panel, find the **"Summary"** text box at the bottom
2. Type a short message describing what you did (e.g., "Completed Part 1" or "Fixed analysis bug")
3. Click **"Commit"**

### Step 5: Push to GitHub

1. Look for the **cloud icon with an up arrow** in the Git panel toolbar
2. Click it
3. If prompted for credentials, enter your GitHub username and PAT again
4. Your changes are now on GitHub!

---

## Quick Reference

| Action | How |
|--------|-----|
| Save notebook | Ctrl+S (Cmd+S on Mac) |
| Open Git panel | Click Git icon in left sidebar |
| Stage a file | Click "+" next to the file |
| Commit | Type message → Click "Commit" |
| Push | Click cloud-with-up-arrow icon |
| Pull | Click cloud-with-down-arrow icon |

---

## Pulling Changes (Getting Updates)

If your instructor updates the repository, or if teammates push changes:

1. Click the **Git icon** in JupyterLab
2. Click the **cloud icon with a down arrow** (or "Pull" button)
3. Your local copy will update with the latest changes

---

## Troubleshooting

### "Author identity unknown"

Your instructor needs to configure your Git identity. Send them your name and email.

### "Authentication failed"

- Make sure you're using your **Personal Access Token**, not your GitHub password
- Check that the token hasn't expired
- Verify the token has the `repo` scope

### "Changes not showing up"

- Did you save the notebook? (Ctrl+S)
- Refresh the Git panel by clicking elsewhere and back

### "Merge conflict"

This happens if you and a teammate edited the same part of a file. Ask your instructor for help resolving it.

### "Repository not found"

- Check that the URL is correct
- Make sure you have access to the repository

---

## Why Use Git?

Git provides a safety net for your work:

- **Version history**: Go back to any previous version if something breaks
- **Backup**: Your work is saved on GitHub, not just the shared server
- **Collaboration**: Multiple team members can work on the same project
- **Push often**: If someone accidentally deletes your files on the server, you can restore from GitHub

**Rule of thumb:** Commit and push whenever you finish a working chunk of code. Don't wait until the end!

---

## Need Help?

Contact your instructor or TA if you get stuck.
