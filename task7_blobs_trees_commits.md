# Task 7 – Blobs, Trees, and Commits

---

## 1. Exploring the `.git/` Directory

### 📁 Objective:
Understand the structure of the `.git` folder and its core components.

### ✅ Commands Used:
```bash
ls -la .git
```

### 🧠 Explanation of Components:

- **HEAD**: Points to the current branch reference (e.g., refs/heads/main).
- **config**: Stores configuration settings specific to the current repository.
- **refs/**: Holds references to commits, including branches and tags.
- **objects/**: Contains all Git objects — blobs, trees, and commits.
- **index**: A staging area between the working directory and the repository.
- **logs/**: Records movements of HEAD and branches, used in `git reflog`.

---

## 2. Latest Object Hash: Identify & Inspect

### ✅ Step 1: Get the Latest Commit Hash
```bash
git log --oneline
```

(Example output):
```
fce99dd (HEAD -> main) Add documentation for Task 6: Move hello.sh and add Makefile
...
```

### ✅ Step 2: Inspect the Commit
```bash
git cat-file -p fce99dd
```

This reveals the commit metadata, including the tree hash.

### ✅ Step 3: Print Type of Git Object
```bash
git cat-file -t fce99dd
```

Output:
```
commit
```

---

## 3. Dumping Directory Tree, lib/ Folder and hello.sh File

### ✅ Step 1: Dump the Tree for the Commit
```bash
git ls-tree fce99dd
```

Output:
```
040000 tree <tree_hash>	lib
100644 blob <blob_hash>	README.md
...
```

### ✅ Step 2: Dump Contents of `lib/`
```bash
git ls-tree <tree_hash>
```

This will show:
```
100755 blob <blob_hash>	hello.sh
```

### ✅ Step 3: Dump the `hello.sh` Blob
```bash
git cat-file -p <blob_hash>
```

This will show the script's contents at that commit state.

---

### Summary

This task demonstrates how Git internally stores and links data using commit objects, tree structures, and file blobs.