# Task 10: Local and Remote Repositories

## 📁 Step 1: Clone the Repository

Clone the existing repository into a new directory named `cloned_hello`:
```bash
git clone /home/chbaikas/Downloads/cohort/4.\ git/git-practice cloned_hello
```

✅ *Output:*
```
Cloning into 'cloned_hello'...
done.
```

---

## 📄 Step 2: View Commit Logs

Navigate into the cloned repository and show the commit history:
```bash
cd cloned_hello
git log --oneline
```

✅ *Sample output:*
```
c0eaabd (HEAD -> main, origin/main, origin/HEAD) Add Task 9 documentation
aa5de36 (origin/greet) Update Makefile
6a4a9b6 Update hello.sh
...
```

---

## 🌐 Step 3: View Remote Repository Information

Check remote URLs and detailed tracking info:
```bash
git remote -v
git remote show origin
```

✅ *Sample output:*
```
origin  /home/chbaikas/Downloads/cohort/4. git/git-practice (fetch)
origin  /home/chbaikas/Downloads/cohort/4. git/git-practice (push)
...
Remote branches:
  greet tracked
  main  tracked
```

---

## 🌿 Step 4: List All Branches

### Local Branches:
```bash
git branch
```

### Remote Branches:
```bash
git branch -r
```

### All Branches:
```bash
git branch -a
```

✅ *Sample output:*
```
* main
  remotes/origin/greet
  remotes/origin/main
```

---

## ✏️ Step 5: Modify the Original Repository

Return to the original repository and update `README.md`:
```bash
cd ../git-practice
echo "This is the Hello World example from the git project." > README.md
git add README.md
git commit -m "Update README.md in original repo"
```

---

## 🔄 Step 6: Fetch Remote Changes in Clone

Switch back to the clone and fetch the updates:
```bash
cd ../cloned_hello
git fetch origin
git log --oneline --all
```

---

## 🔀 Step 7: Merge Remote `main` into Local `main`

```bash
git merge origin/main
```

---

## 🌱 Step 8: Track Remote Branch `greet` Locally

If `greet` branch exists remotely:
```bash
git checkout -b greet origin/greet
```

If it already exists locally but isn’t tracking:
```bash
git branch --set-upstream-to=origin/greet greet
```

---

## 🚀 Step 9: Push to Remote

Push both branches to origin (or other remote):
```bash
git push origin main
git push origin greet
```

---

## ❓ Audit Question

> **Q:** What is the single Git command equivalent to bringing changes from remote to local `main` branch?

✅ **A:**
```bash
git pull origin main
```

This fetches changes from the `origin` remote and merges them into your local `main` branch in one step.