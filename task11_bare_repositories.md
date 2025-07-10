# Task 11 – Bare Repositories

## What is a Bare Repository?

A **bare repository** in Git is a repository that **only contains the version control information**, without a working directory (no actual files are checked out). It's used as a **central hub** for collaboration—where other repositories can push to or pull from it.

It is needed when:
- You want a central shared repository on a server or local network.
- You don’t need to edit files in that repo (no working tree).
- It's commonly used for remote repositories like GitHub or self-hosted Git servers.

---

## ✅ Step 1: Create Bare Repository from `hello`

```bash
git clone --bare hello hello.git
```

Creates a `hello.git` folder containing the Git database only (no working copy).

---

## ✅ Step 2: Add the Bare Repository as a Remote

```bash
cd hello
git remote add shared ../hello.git
git remote -v
```

Output:
```
shared  ../hello.git (fetch)
shared  ../hello.git (push)
```

---

## ✅ Step 3: Modify `README.md` in Original Repository

```bash
echo "This is the Hello World example from the git project. (Changed in the original and pushed to shared)" > README.md
git add README.md
git commit -m "Update README.md and push to shared remote"
```

---

## ✅ Step 4: Push to `shared` Remote

```bash
git push shared master
```

---

## ✅ Step 5: Pull Changes in `cloned_hello`

```bash
git clone hello.git cloned_hello
cd cloned_hello
git remote add shared ../hello.git
git fetch shared
git pull shared main
```

Then confirm:

```bash
cat README.md
```

Output:
```
This is the Hello World example from the git project. (Changed in the original and pushed to shared)
```

---

## ✅ Summary

This task demonstrates:
- Creating a central bare repository (`hello.git`)
- Pushing changes from a working repo (`hello`) to the bare one
- Pulling the updates from another clone (`cloned_hello`)