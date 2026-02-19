# Git & VS Code Setup Guide
## My AI Voyage Blog - Complete Setup Instructions

---

## Prerequisites Checklist

Before starting, make sure you have:
- ✅ Git installed on your computer ([download here](https://git-scm.com/downloads))
- ✅ Visual Studio Code installed ([download here](https://code.visualstudio.com/))
- ✅ A GitHub account (username: MatthijsKoen)
- ✅ Your blog repository created on GitHub: `My-AI-Voyage`
- ✅ Local folder created at: `C:\MyFiles\MattieAI\my-ai-voyage-site`
- ✅ Your `index.html` file saved in that folder

---

## Part 1: Initial Git Configuration (One-Time Setup)

### Step 1.1: Configure Git with Your Identity

Open **Command Prompt** or **PowerShell** and run these commands:

```bash
git config --global user.name "MatthijsKoen"
git config --global user.email "your-email@example.com"
```

*Replace `your-email@example.com` with the email you used for GitHub.*

### Step 1.2: Verify Git Installation

```bash
git --version
```

You should see something like `git version 2.x.x`

---

## Part 2: Initialize Git Repository Locally

### Step 2.1: Navigate to Your Project Folder

```bash
cd C:\MyFiles\MattieAI\my-ai-voyage-site
```

### Step 2.2: Initialize Git

```bash
git init
```

You should see: `Initialized empty Git repository in C:/MyFiles/MattieAI/my-ai-voyage-site/.git/`

### Step 2.3: Add Your Remote Repository

```bash
git remote add origin https://github.com/MatthijsKoen/My-AI-Voyage.git
```

### Step 2.4: Set Default Branch to Main

```bash
git branch -M main
```

---

## Part 3: Your First Commit

### Step 3.1: Stage Your Files

```bash
git add .
```

This stages all files in your directory (currently just `index.html` and any others you've added).

### Step 3.2: Create Your First Commit

```bash
git commit -m "Initial commit: Blog homepage with editorial design"
```

### Step 3.3: Push to GitHub

```bash
git push -u origin main
```

*You may be prompted to authenticate with GitHub. Use your GitHub username and a [Personal Access Token](https://github.com/settings/tokens) as the password.*

---

## Part 4: Configure GitHub Pages

### Step 4.1: Go to Your Repository Settings

1. Navigate to: https://github.com/MatthijsKoen/My-AI-Voyage
2. Click **Settings** (top navigation)
3. Click **Pages** (left sidebar)

### Step 4.2: Configure GitHub Pages

- **Source**: Select `main` branch
- **Folder**: Select `/ (root)`
- Click **Save**

Your site will be live at: `https://matthijskoen.github.io/My-AI-Voyage/`

⏱️ *It may take 1-2 minutes for changes to appear online.*

---

## Part 5: Visual Studio Code Setup

### Step 5.1: Open Your Project in VS Code

**Method 1 (Quick):**
```bash
cd C:\MyFiles\MattieAI\my-ai-voyage-site
code .
```

**Method 2 (From VS Code):**
1. Open VS Code
2. File → Open Folder
3. Navigate to `C:\MyFiles\MattieAI\my-ai-voyage-site`
4. Click **Select Folder**

### Step 5.2: Install Recommended Extensions

Open the Extensions panel (Ctrl+Shift+X) and install:

1. **Live Server** (by Ritwick Dey)
   - Right-click `index.html` → "Open with Live Server"
   - Instantly preview changes at `http://localhost:5500`

2. **GitLens** (by GitKraken)
   - Enhanced Git integration
   - See who changed what and when

3. **Prettier - Code Formatter** (by Prettier)
   - Auto-format your HTML/CSS/JS
   - Keep code clean and consistent

4. **HTML CSS Support** (by ecmel)
   - IntelliSense for CSS classes in HTML

5. **Path Intellisense** (by Christian Kohler)
   - Autocomplete for file paths

### Step 5.3: Configure VS Code Settings for Your Project

In VS Code, press `Ctrl+Shift+P` and type "Preferences: Open Settings (JSON)"

Add these settings (or create a `.vscode/settings.json` file in your project):

```json
{
  "editor.formatOnSave": true,
  "editor.defaultFormatter": "esbenp.prettier-vscode",
  "files.autoSave": "afterDelay",
  "files.autoSaveDelay": 1000,
  "liveServer.settings.port": 5500,
  "git.autofetch": true,
  "git.confirmSync": false,
  "html.format.wrapLineLength": 120,
  "editor.wordWrap": "on"
}
```

---

## Part 6: Daily Workflow (How to Work With Git Going Forward)

### Making Changes and Publishing

**Every time you work on your blog:**

1. **Start VS Code and open your project**
   ```bash
   cd C:\MyFiles\MattieAI\my-ai-voyage-site
   code .
   ```

2. **Pull latest changes** (good habit, especially if working from multiple machines)
   ```bash
   git pull origin main
   ```

3. **Make your edits** in VS Code
   - Use Live Server to preview changes locally

4. **Stage your changes**
   ```bash
   git add .
   ```

5. **Commit your changes** with a descriptive message
   ```bash
   git commit -m "Added first blog post about earnings summarizer"
   ```

6. **Push to GitHub** (this publishes to your live site)
   ```bash
   git push origin main
   ```

### Quick Git Commands Reference

```bash
# Check status of your files
git status

# See what changed
git diff

# View commit history
git log --oneline

# Undo changes to a file (before staging)
git checkout -- filename.html

# Undo last commit (keeps changes)
git reset --soft HEAD~1

# Create a new branch for experiments
git checkout -b experiment-new-layout

# Switch back to main branch
git checkout main

# Merge experimental branch into main
git merge experiment-new-layout
```

---

## Part 7: VS Code Git Integration (Visual Workflow)

VS Code has built-in Git support. Here's how to use it:

### Using the Source Control Panel

1. **Open Source Control** (Ctrl+Shift+G or click the branch icon in left sidebar)

2. **See Changed Files** - Listed under "Changes"

3. **Stage Files**
   - Click the `+` icon next to a file
   - Or click `+` next to "Changes" to stage all

4. **Write Commit Message**
   - Type in the message box at the top

5. **Commit**
   - Click the checkmark ✓ button
   - Or press Ctrl+Enter

6. **Push to GitHub**
   - Click the `...` menu → Push
   - Or click the sync button in the bottom status bar

### Using the Command Palette

Press `Ctrl+Shift+P` and type "Git:" to see all Git commands available.

---

## Part 8: Project Structure (Recommended)

As your blog grows, organize it like this:

```
C:\MyFiles\MattieAI\my-ai-voyage-site\
│
├── index.html                  # Homepage (your current file)
├── about.html                  # About page
├── .gitignore                  # Files Git should ignore
├── README.md                   # Project documentation
│
├── css/
│   ├── main.css               # Main stylesheet
│   └── blog-post.css          # Blog post specific styles
│
├── js/
│   └── main.js                # Any JavaScript you add
│
├── posts/
│   ├── 2026-02-first-api-call.html
│   ├── 2026-02-ai-tools-review.html
│   └── ...                    # More blog posts
│
├── images/
│   ├── logo.png
│   ├── screenshots/
│   └── posts/                 # Images for blog posts
│
└── experiments/
    ├── earnings-summarizer/   # Code from your experiments
    └── portfolio-monitor/
```

---

## Part 9: Create Essential Files

### Create `.gitignore`

Create a file called `.gitignore` in your project root with:

```
# OS files
.DS_Store
Thumbs.db

# Editor files
.vscode/
.idea/

# Build files
node_modules/
dist/
*.log

# Personal notes (won't be published)
_drafts/
_notes/
```

### Create `README.md`

Create a `README.md` file:

```markdown
# My AI Voyage

**Subtitle:** My Journey as Citizen Developer to Explore Day to Day Applications of AI in the Space of Investment Management

## About This Project

This is my public AI experimentation lab where I document my journey learning to build with AI APIs and tools, with a specific focus on investment management applications.

## Live Site

Visit: [https://matthijskoen.github.io/My-AI-Voyage/](https://matthijskoen.github.io/My-AI-Voyage/)

## Tech Stack

- Pure HTML/CSS/JavaScript (keeping it simple as a citizen developer)
- GitHub Pages for hosting
- Claude API & OpenAI API for experiments

## Structure

- `/index.html` - Homepage
- `/posts/` - Blog posts
- `/experiments/` - Code from my AI experiments

## Follow Along

- Blog: [https://matthijskoen.github.io/My-AI-Voyage/](https://matthijskoen.github.io/My-AI-Voyage/)
- LinkedIn: [Your LinkedIn URL]

---

*Last updated: February 2026*
```

---

## Part 10: Troubleshooting Common Issues

### Issue: "Permission denied (publickey)" when pushing

**Solution:** Set up SSH key or use HTTPS with Personal Access Token
```bash
# Switch to HTTPS if SSH isn't working
git remote set-url origin https://github.com/MatthijsKoen/My-AI-Voyage.git
```

### Issue: Changes not appearing on GitHub Pages

**Solutions:**
1. Wait 1-2 minutes and hard-refresh (Ctrl+Shift+R)
2. Check GitHub Actions tab for build status
3. Verify your file is named `index.html` (case-sensitive)

### Issue: "fatal: not a git repository"

**Solution:** You're not in the right folder
```bash
cd C:\MyFiles\MattieAI\my-ai-voyage-site
```

### Issue: Merge conflicts

**Solution:**
1. Open the conflicted file in VS Code
2. VS Code will show conflict markers
3. Click "Accept Current" or "Accept Incoming" or manually edit
4. Save, stage, and commit

---

## Quick Reference Card

```bash
# Daily workflow shortcuts
git status                          # What changed?
git add .                          # Stage everything
git commit -m "Your message"       # Commit with message
git push                           # Publish to GitHub

# Undo commands
git checkout -- file.html          # Discard changes to file
git reset HEAD file.html           # Unstage file
git reset --soft HEAD~1            # Undo last commit (keep changes)

# Branch commands
git branch                         # List branches
git checkout -b new-feature        # Create and switch to new branch
git checkout main                  # Switch back to main
git merge new-feature              # Merge branch into current

# View commands
git log --oneline --graph          # Visual commit history
git diff                           # Show unstaged changes
git diff --staged                  # Show staged changes
```

---

## Next Steps After Setup

1. ✅ Commit and push your current `index.html`
2. ✅ Add `.gitignore` and `README.md`
3. ✅ Install VS Code extensions
4. ✅ Test Live Server preview
5. ✅ Practice: Make a small change, commit, push, verify on GitHub Pages
6. ✅ Start writing your first blog post!

---

## Need Help?

- [GitHub Docs](https://docs.github.com/)
- [Git Documentation](https://git-scm.com/doc)
- [VS Code Git Tutorial](https://code.visualstudio.com/docs/sourcecontrol/overview)

---

*Happy coding! 🚀*
