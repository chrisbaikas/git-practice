# Task 5 – Changed Your Mind

## 🎯 Objective
Practice reverting, resetting, amending, and cleaning Git commits.

---

## 1️⃣ Reverting Changes (Before Staging)

Modified `hello.sh` with unwanted comment:

```bash
#!/bin/bash

# This is a bad comment. We want to revert it.
name=${1:-"World"}
echo "Hello, $name"
```

Reverted before staging:
```bash
git restore hello.sh
```

✅ Restored state:
```bash
#!/bin/bash

# Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```

---

## 2️⃣ Staging and Cleaning

Introduced and **staged** unwanted change:

```bash
# This is an unwanted but staged comment
```

Commands:
```bash
git add hello.sh
git restore --staged hello.sh
git restore hello.sh
```

✅ Cleaned both the **index** and the **working directory**.

---

## 3️⃣ Committing and Reverting

Committed an unwanted change:
```bash
git add hello.sh
git commit -m "Oops: committed unwanted comment"
```

Reverted it:
```bash
git revert HEAD
```

✅ Clean state restored after revert.

---

## 4️⃣ Tagging and Removing Commits

Tagged the unwanted commit:
```bash
git tag oops
```

Then reset to previous stable version:
```bash
git reset --hard v1
```

✅ HEAD now points to `v1`.

---

## 5️⃣ Viewing Deleted Commits

Showed logs (deleted commits still appear as dangling):
```bash
git log --oneline --all
```

To verify:
```bash
git log --oneline
```

---

## 6️⃣ Cleaning Unreferenced Commits

Used garbage collection to clean dangling commits:
```bash
git gc --prune=now
```

✅ Deleted unreferenced commits from reflog and history.

---

## 7️⃣ Author Information

Added author line:
```bash
# Author: Jim Weirich
```

Then committed:
```bash
git commit -m "Add author name to hello.sh"
```

Amended the commit to include email:
```bash
# Author: Jim Weirich <jim@example.com>
```

Without creating a new commit:
```bash
git add hello.sh
git commit --amend --no-edit
```

✅ Final version includes name and email in the same commit.

---

## ✅ Summary of Commands Used

```bash
git restore hello.sh
git add hello.sh
git restore --staged hello.sh
git commit -m "Oops: committed unwanted comment"
git revert HEAD
git tag oops
git reset --hard v1
git log --oneline --all
git gc --prune=now
git commit --amend --no-edit
```

---

📝 This document serves as the report for **Task 5** and is suitable for submission.