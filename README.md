# \# 🚀 ANJAN DEV WORKFLOW (FULL SETUP + ERRORS)

# 

# \# -------------------------------

# \# 🔴 INITIAL ERROR (SSH FAILED)

# \# -------------------------------

# git clone git@github.com:ajvizganapathy-pixel/anjan-dev-workflow.git

# 

# \# Error:

# \# Permission denied (publickey)

# 

# \# Cause:

# \# SSH key not created or not added to GitHub

# 

# 

# \# -------------------------------

# \# 🔑 SSH SETUP

# \# -------------------------------

# 

# \# Generate SSH key

# ssh-keygen -t ed25519 -C "ajvizganapathy@gmail.com"

# 

# \# (Press ENTER for all prompts)

# 

# \# Verify key exists

# ls \~/.ssh

# \# Expected:

# \# id\_ed25519

# \# id\_ed25519.pub

# 

# \# Start SSH agent

# eval "$(ssh-agent -s)"

# 

# \# Add key

# ssh-add \~/.ssh/id\_ed25519

# 

# \# Copy public key

# cat \~/.ssh/id\_ed25519.pub

# 

# \# 👉 Add this key to:

# \# https://github.com/settings/keys

# 

# 

# \# -------------------------------

# \# 🧪 TEST SSH CONNECTION

# \# -------------------------------

# ssh -T git@github.com

# 

# \# Expected:

# \# Hi ajvizganapathy-pixel! You've successfully authenticated

# 

# 

# \# -------------------------------

# \# 📥 CLONE REPOSITORY

# \# -------------------------------

# git clone git@github.com:ajvizganapathy-pixel/anjan-dev-workflow.git

# 

# cd anjan-dev-workflow

# 

# ls

# \# Expected:

# \# README.md (or empty repo)

# 

# 

# \# -------------------------------

# \# ✏️ EDIT FILE

# \# -------------------------------

# notepad README.md

# 

# 

# \# -------------------------------

# \# 📦 STAGE CHANGES

# \# -------------------------------

# git add .

# 

# 

# \# -------------------------------

# \# ❌ COMMIT ERROR (IDENTITY)

# \# -------------------------------

# git commit -m "update workflow"

# 

# \# Error:

# \# Author identity unknown

# 

# \# Fix:

# git config --global user.name "ANJAN GANAPATHY K"

# git config --global user.email "ajvizganapathy@gmail.com"

# 

# 

# \# -------------------------------

# \# 🧾 COMMIT AGAIN

# \# -------------------------------

# git commit -m "update workflow"

# 

# \# Expected:

# \# \[main xxxx] update workflow

# 

# 

# \# -------------------------------

# \# 🚀 PUSH TO GITHUB

# \# -------------------------------

# git push

# 

# \# If error:

# \# Permission denied → SSH not set → repeat SSH setup

# 

# 

# \# -------------------------------

# \# 🧠 FULL WORKFLOW (DAILY USE)

# \# -------------------------------

# git add .

# git commit -m "update"

# git push

# 

# 

# \# -------------------------------

# \# ⚠️ COMMON MISTAKES

# \# -------------------------------

# \# - SSH key not added to GitHub

# \# - Using HTTPS instead of SSH

# \# - Forgetting git add

# \# - File not saved before commit

# \# - Git user.name / user.email not set

# 

# 

# \# -------------------------------

# \# ✅ FINAL STATE

# \# -------------------------------

# \# SSH working

# \# Git configured

# \# Repo cloned

# \# Commit working

# \# Push working

# 

# \# 🚀 You now have full developer workflow

