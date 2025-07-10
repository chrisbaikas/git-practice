# Task 9 – Conflicts, Merging and Rebasing

## ✅ Merge Main into Greet Branch

```bash
git switch greet

# or 

git checkout greet
git merge main
```

Git will prompt for a merge commit message like:

```
Merge branch 'main' into greet
# Please enter a commit message to explain why this merge is necessary,
# Lines starting with '#' will be ignored, and an empty message aborts the commit.
```

## ✏️ Switch to `main` and modify `hello.sh`

```bash
git switch main

# or

git checkout main
```

Edit `hello.sh` to:

```bash
#!/bin/bash

echo "What's your name"
read my_name

echo "Hello, $my_name"
```

Then commit:

```bash
git add lib/hello.sh
git commit -m "Update hello.sh to prompt for user name (main branch)"
```

## ⚠️ Merge `main` into `greet` (Expect Conflict)

```bash
git switch greet
git merge main
```

Expected output:

```
Auto-merging lib/hello.sh
CONFLICT (content): Merge conflict in lib/hello.sh
Automatic merge failed; fix conflicts and then commit the result.
```

### 🔧 Resolve the conflict

Keep the version from `main`:

```bash
#!/bin/bash

echo "What's your name"
read my_name

echo "Hello, $my_name"
```

Then:

```bash
git add hello.sh
git commit -m "Resolve conflict: accept main's version of hello.sh"
```

## 🔁 Rebase `greet` onto `main`

To rebase:

```bash
git reset --hard HEAD~1  # If needed to undo merge
git switch greet
git rebase main
```

If a conflict occurs during rebase, fix the file, stage it, then:

```bash
git add <file>
git rebase --continue
```

## 🔀 Merge `greet` into `main`

```bash
git switch main
git merge greet
```

---

## 📘 Explanation: Fast-Forward vs Merge vs Rebase

### 🟢 Fast-Forward

Occurs when the current branch has no new commits. The pointer simply advances.

```
main:  A---B
             \
greet:        C---D

# After fast-forward merge:
main:  A---B---C---D
```

### 🟡 Merge

Preserves history by creating a merge commit:

```
main:  A---B
             \
greet:        C---D

# After merge:
main:  A---B---------M
             \     /
              C---D
```

### 🔵 Rebase

Rewrites commit base of a branch:

```
main:  A---B---C
             \
greet:        D---E

# After rebase greet onto main:
main:  A---B---C---D'---E'
```

This results in a linear history.

---

## ✅ Summary

| Concept         | Description                                                  |
|----------------|--------------------------------------------------------------|
| Merge           | Combines histories, keeps branching                          |
| Rebase          | Rewrites history onto a new base, linearizes history         |
| Fast-forward    | Pointer simply advances when no divergent history exists     |