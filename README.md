# 🚀 Anjan Dev Workflow — Full Setup + Execution Log

A complete guide to setting up and using Git with GitHub over SSH, including real errors encountered and how they were fixed.

---

## 🔴 Initial Error (SSH Failed)

```bash
git clone git@github.com:ajvizganapathy-pixel/anjan-dev-workflow.git
# Error: Permission denied (publickey)
# Cause: SSH key not created or not added to GitHub
```

---

## 🔑 SSH Setup

```bash
# Generate SSH key
ssh-keygen -t ed25519 -C "ajvizganapathy@gmail.com"
# (Press ENTER for all prompts)

# Verify key exists
ls ~/.ssh
# Expected: id_ed25519  id_ed25519.pub

# Start SSH agent
eval "$(ssh-agent -s)"

# Add key to agent
ssh-add ~/.ssh/id_ed25519

# Copy public key — paste this into GitHub → Settings → SSH Keys
cat ~/.ssh/id_ed25519.pub
```

> 👉 Add the public key at: https://github.com/settings/keys

---

## 🧪 Test SSH Connection

```bash
ssh -T git@github.com
# Expected: Hi ajvizganapathy-pixel! You've successfully authenticated
```

---

## 📥 Clone Repository

```bash
git clone git@github.com:ajvizganapathy-pixel/anjan-dev-workflow.git
cd anjan-dev-workflow
ls
# Expected: README.md
```

---

## ❌ Commit Error — Identity Unknown

```bash
git commit -m "update workflow"
# Error: Author identity unknown

# Fix:
git config --global user.name "ANJAN GANAPATHY K"
git config --global user.email "ajvizganapathy@gmail.com"
```

---

## ⚠️ Extra Step (Not Needed After Clone)

```bash
git init
# Output: Reinitialized existing Git repository
# Note: Unnecessary — repo already has .git from clone

git remote add origin git@github.com:ajvizganapathy-pixel/anjan-dev-workflow.git
# Error: remote origin already exists
# Note: Clone already sets the remote
```

---

## 🚀 First Push

```bash
git add .
git commit -m "Initial workflow setup"
git push -u origin main
# Output: branch 'main' set up to track 'origin/main'
```

---

## 🧠 Daily Workflow (Correct Way)

After the repo is cloned and configured, all you need is:

```bash
git add .
git commit -m "your message"
git push
```

---

## ⚠️ Common Mistakes

| Mistake | Fix |
|---|---|
| SSH key not added to GitHub | Add via github.com/settings/keys |
| Using HTTPS instead of SSH | Re-clone with `git@github.com:...` URL |
| Forgetting `git add` | Always `add` before `commit` |
| File not saved before commit | Save first, then `add` |
| `user.name` / `user.email` not set | Run `git config --global` commands above |
| Running `git init` after clone | Not needed — clone includes `.git` |
| Running `git remote add` after clone | Not needed — clone sets remote automatically |

---

## ✅ Final State

- SSH key generated and added to GitHub
- Git identity configured globally
- Repository cloned via SSH
- Files edited, committed, and pushed successfully

**🚀 Full developer workflow is working.**
