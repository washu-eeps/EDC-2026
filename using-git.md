---
layout: default
title: Git Workflow in JupyterLab
---

# Git Workflow in JupyterLab

This guide walks you through using Git to save and version your team's work. No terminal required - everything uses JupyterLab's visual Git interface.

---

## What is Git?

Git is a version control system that tracks changes to your files. Think of it as a detailed "undo history" that also backs up your work online.

**Key concepts:**

- **Repository (repo)**: A folder whose contents are tracked by Git
- **Stage**: Select which changes you want to save
- **Commit**: Save a snapshot of those changes with a short description
- **Push**: Upload your commits to GitHub so they're backed up online
- **Pull**: Download the latest changes from GitHub (e.g., your teammate's work)

Think of it like packing a box: you *stage* items to pack, *commit* seals the box with a label, and *push* ships it to storage.

For a deeper dive, see [GitHub's Git Handbook](https://docs.github.com/en/get-started/using-git/about-git).

---

## Getting Started (One-Time Setup)

Each team needs ONE shared GitHub account. Designate one team member to create it.

### Step 1: Create a Team GitHub Account

1. Go to [github.com](https://github.com)
2. Click **"Sign up"**
3. Create an account for your team:
   - **Username**: Something like `edc-yourteamname`
   - **Email**: Use a team member's real email (for receive notifications)
4. Verify the email address
5. **Share the login credentials with your teammates** (everyone will use this same account)

### Step 2: Tell Alex B.

Send Alex:
- Your team name
- Your team's GitHub username

He will create a repository for your team in the **washu-eeps** organization and add your team's GitHub account as a collaborator. The repo lives in `washu-eeps` (not in your team's account) - your team account is just used for login credentials.

### Step 3: Create a Personal Access Token (PAT)

GitHub requires a token (not your password) for connecting from JupyterLab.

1. Sign into your team's GitHub account
2. Go to [github.com/settings/tokens](https://github.com/settings/tokens)
3. Click **"Tokens (classic)"** in the left sidebar
4. Click **"Generate new token"** -> **"Generate new token (classic)"**
5. Fill in:
   - **Note**: `JupyterLab` (or any name to help you remember)
   - **Expiration**: 90 days (long enough to get to the end of April)
   - **Scopes**: Check the box for **`repo`**
6. Click **"Generate token"**
7. **COPY THE TOKEN NOW** - you won't see it again!
8. Save it somewhere your whole team can access it (shared note, etc.)

---

## Cloning the Repository

Once Alex confirms your repo is ready, you'll "clone" it into JupyterLab. This downloads a copy to your workspace.

### Step 1: Get the Repository URL

1. Go to the repository Alex created for your team (he'll send you the link - it will look like `https://github.com/washu-eeps/yourteamname`)
2. Click the green **"Code"** button
3. Make sure **HTTPS** is selected
4. Click the copy button to copy the URL

### Step 2: Clone in JupyterLab

1. Open JupyterLab
2. Click the **Git icon** in the left sidebar (diamond shape with branches)
3. Click **"Clone a Repository"**
4. Paste the URL you copied
5. Click **"Clone"**
6. When prompted for credentials:
   - **Username**: Your team's GitHub username
   - **Password**: Paste your Personal Access Token (NOT the GitHub password)
7. A new folder will appear in your file browser with your repository name


**Important**: Your team clones the repo once into JupyterLab. Since you're all sharing the same JupyterLab environment, you'll work from this single local copy. When you push, your changes go to the shared repo in `washu-eeps`.

**Avoid working simultaneously**: If two people edit the same notebook at the same time, you'll create merge conflicts. Git can handle these, but resolving them requires command-line tools you don't have access to here. Coordinate with your team - take turns or work together at the same screen.

---

## Daily Workflow

### Working on Your Notebook

1. In the file browser (folder icon), navigate into your repository folder
2. Double-click the notebook file to open it
3. Do your work!
4. Press **Ctrl+S** (or **Cmd+S** on Mac) to save frequently

### Saving to Git (Stage -> Commit -> Push)

When you've made progress you want to save:

**1. Stage your changes**
   - Click the **Git icon** in the left sidebar
   - You'll see changed files listed under **"Changed"**
   - Hover over each file and click the **"+"** button to stage it
   - The file moves to **"Staged"**

**2. Commit your changes**
   - Find the **"Summary"** text box at the bottom of the Git panel
   - Type a short message describing what you did (e.g., "Added temperature analysis" or "Fixed plotting bug")
   - Click **"Commit"**

**3. Push to GitHub**
   - Click the **cloud icon with an up arrow** in the Git panel toolbar
   - If prompted, enter your team's GitHub username and PAT
   - Your changes are now saved on GitHub!

### Getting Your Teammate's Changes (Pull)

Before starting work each session, pull the latest changes:

1. Click the **Git icon** in the left sidebar
2. Click the **cloud icon with a down arrow** (Pull button)
3. Your local copy updates with your teammates' work

**Tip**: Always pull before you start working, and push when you're done. This avoids conflicts.

---

## Quick Reference

| Action | How |
|--------|-----|
| Save notebook | Ctrl+S (Cmd+S on Mac) |
| Open Git panel | Click Git icon in left sidebar |
| Stage a file | Click "+" next to the file |
| Commit | Type message -> Click "Commit" |
| Push | Click cloud-with-up-arrow icon |
| Pull | Click cloud-with-down-arrow icon |

---

## Troubleshooting

### "Authentication failed"

- Make sure you're using your **Personal Access Token**, not the GitHub password
- Check that the token hasn't expired
- Verify the token has the `repo` scope checked

### "Changes not showing up" in the Git panel

- Did you save the notebook? (Ctrl+S)
- Click somewhere else and back to refresh the panel

### "Merge conflict"

This happens if you and a teammate edited the same part of a file at the same time. Ask your instructor for help resolving it.

**To avoid conflicts**: Coordinate with your team about who's working on what, and always pull before you start working.

### "Repository not found"

- Check that the URL is correct (should start with `https://github.com/washu-eeps/`)
- Make sure you accepted the collaborator invitation email from GitHub
- Verify Alex has added your team's GitHub account as a collaborator

### Accidentally deleted something?

If you pushed it to GitHub before deleting, you can recover it! Ask your instructor for help.

---

## Why Bother With Git?

- **Backup**: Your work is saved on GitHub, not just the shared server
- **Version history**: Go back to any previous version if something breaks
- **Collaboration**: See what your teammates changed and when
- **Safety net**: If someone accidentally deletes files on the server, you can restore from GitHub

**Rule of thumb**: Commit and push whenever you finish a working chunk of code. Don't wait until the end!

---

## Need Help?

Contact one of the EDC leads if you get stuck.
