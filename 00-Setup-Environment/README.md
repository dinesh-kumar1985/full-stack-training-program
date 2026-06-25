# Environment Setup & Prerequisites

## 🖥️ System Requirements

### Minimum Requirements
- **RAM:** 8GB (16GB Recommended)
- **Storage:** 50GB Free Space
- **Processor:** Intel i5/AMD Ryzen 5 or better
- **OS:** Windows 10+, macOS 10.14+, or Ubuntu 18.04+

---

## 📦 Software Installation (Complete Setup Guide)

### 1. Git & GitHub

```bash
# Windows (using Chocolatey)
choco install git

# macOS (using Homebrew)
brew install git

# Linux
sudo apt-get install git
```

**Setup GitHub:**
```bash
git config --global user.name "Your Name"
git config --global user.email "your.email@example.com"
git config --global core.editor "code"
```

### 2. Code Editor - VS Code

Download from: https://code.visualstudio.com/

**Essential Extensions:**
- ES7+ React/Redux/React-Native snippets
- Python
- Pylint
- Django
- Thunder Client (API Testing)
- Postman
- Docker
- GitLens
- GitHub Copilot
- Cursor AI
- REST Client
- Live Server
- Prettier
- ESLint

### 3. Node.js & npm

```bash
# Install from https://nodejs.org/ (LTS version)
node --version  # Verify (v18+)
npm --version   # Verify

# Update npm
npm install -g npm@latest
```

### 4. Python Installation

```bash
# Download from https://www.python.org/
python --version  # Verify (3.10+)
pip --version     # Verify

# Update pip
python -m pip install --upgrade pip
```

### 5. PostgreSQL Database

```bash
# Windows/macOS: Download from https://www.postgresql.org/download/
# Linux:
sudo apt-get install postgresql postgresql-contrib

# Verify
psql --version
```

### 6. MongoDB

```bash
# Download from https://www.mongodb.com/try/download/community
# Or use MongoDB Atlas (Cloud): https://www.mongodb.com/cloud/atlas
```

### 7. Docker

```bash
# Download from https://www.docker.com/products/docker-desktop
docker --version  # Verify
```

### 8. Git Bash / Terminal

```bash
# Windows: Use Git Bash (comes with Git) or PowerShell
# macOS: Use Terminal
# Linux: Use any terminal emulator
```

---

## 🔧 Terminal/Command Line Basics

### Essential Commands

```bash
# Navigation
cd folder-name          # Change directory
ls or dir               # List files
cd ..                   # Go to parent directory
pwd                     # Print working directory
clear                   # Clear terminal

# File Operations
touch file.txt          # Create file
mkdir folder-name       # Create directory
rm file.txt             # Delete file
rm -r folder-name       # Delete folder recursively
cp file.txt file2.txt   # Copy file
mv file.txt new-name.txt # Move/Rename file
cat file.txt            # Display file contents

# Git Commands
git clone <url>         # Clone repository
git add .               # Stage changes
git commit -m "message" # Commit changes
git push origin main    # Push to GitHub
git pull origin main    # Pull from GitHub
git status              # Check status
git branch              # List branches
git checkout -b branch-name  # Create new branch
```

---

## 📁 Project Folder Structure

```
~/dev/projects/
├── 01-frontend-projects/
│   ├── 01-html-basics/
│   ├── 02-css-styling/
│   ├── 03-responsive-design/
│   ├── 04-flexbox-grid/
│   ├── 05-bootstrap-projects/
│   ├── 06-tailwind-projects/
│   ├── 07-javascript-projects/
│   └── 08-api-integration/
├── 02-backend-projects/
├── 03-fullstack-projects/
├── 04-capstone-projects/
└── learning-notes/
```

---

## 🤖 AI Tools Setup

### 1. GitHub Copilot
- Install VS Code Extension
- Sign in with GitHub account
- Activate license (GitHub Copilot subscription or free for students)
- Start typing code and AI will suggest completions

### 2. Cursor AI
- Download from https://cursor.sh/
- VSCode alternative with built-in AI capabilities
- Free trial available

### 3. ChatGPT
- Sign up at https://openai.com/
- Use for learning, debugging, and code optimization
- Free tier available

---

## ✅ Verification Checklist

Run these commands in your terminal to verify setup:

```bash
# Check Git
git --version

# Check Node.js and npm
node --version
npm --version

# Check Python
python --version
pip --version

# Check PostgreSQL (if installed locally)
psql --version

# Check Docker
docker --version
```

**Checklist:**
- [ ] Git installed and configured
- [ ] VS Code installed with extensions
- [ ] Node.js (v18+) and npm working
- [ ] Python 3.10+ installed
- [ ] PostgreSQL installed
- [ ] MongoDB account (Atlas or local)
- [ ] Docker installed
- [ ] GitHub account created and configured
- [ ] AI tools (Copilot/Cursor) configured
- [ ] Terminal/Command line working
- [ ] Test project folder created

---

## 🚀 First Project Setup

### Step 1: Create Local Project Folder

```bash
# Navigate to projects directory
cd ~/dev/projects

# Create new directory
mkdir my-first-project
cd my-first-project
```

### Step 2: Initialize Git Repository

```bash
# Initialize git
git init

# Create initial files
touch README.md
touch .gitignore

# Create initial folder structure
mkdir src
mkdir public
```

### Step 3: Connect to GitHub

```bash
# Stage files
git add .

# Create initial commit
git commit -m "Initial commit: Project setup"

# Rename branch to main (if needed)
git branch -M main

# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/my-first-project.git

# Push to GitHub
git push -u origin main
```

### Step 4: Verify

- Visit your GitHub repository
- Confirm files are pushed
- You're ready to start coding!

---

## 📚 Recommended Learning Resources

### Free Online Platforms
- **MDN Web Docs:** https://developer.mozilla.org/
- **freeCodeCamp.org:** https://www.freecodecamp.org/
- **Codecademy:** https://www.codecademy.com/
- **Khan Academy:** https://www.khanacademy.org/
- **Python.org:** https://docs.python.org/
- **Django Official Docs:** https://docs.djangoproject.com/
- **React Official Docs:** https://react.dev/
- **Next.js Docs:** https://nextjs.org/docs

### Paid Platforms (Optional)
- **Udemy:** https://www.udemy.com/
- **Coursera:** https://www.coursera.org/
- **Pluralsight:** https://www.pluralsight.com/
- **Frontend Masters:** https://frontendmasters.com/

---

## 🎯 Next Steps

1. ✅ Complete environment setup
2. ✅ Verify all installations
3. ✅ Create first GitHub repository
4. 👉 **Start Month 1:** [Frontend Fundamentals](../01-Month-1-Frontend-Fundamentals/README.md)

---

**Environment ready? Let's start learning! 🎉**
