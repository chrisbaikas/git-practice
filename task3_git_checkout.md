# Task 3: Check it out (Restoring Snapshots)

## 🎯 Objective
Practice reverting the working directory to previous states using Git, **without relying on hardcoded commit hashes**. Each step demonstrates Git commands to navigate commit history and inspect file states.

---

## ✅ 1. Restore First Snapshot

Restore the working tree to the **first commit** and print `hello.sh`:

```bash
git checkout $(git rev-list --max-parents=0 HEAD) -- hello/hello.sh
cat hello/hello.sh
```

📄 Output:
```bash
echo "Hello, World"
```

📝 Explanation:
- `git rev-list --max-parents=0 HEAD` finds the first commit.
- The `checkout ... -- <file>` syntax restores only that file from that commit (without changing HEAD).

---

## ✅ 2. Restore Second Most Recent Snapshot

Restore the file to the **second most recent commit**:

```bash
git checkout HEAD~1 -- hello/hello.sh
cat hello/hello.sh
```

📄 Output:
```bash
#!/bin/bash

# Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```

📝 Explanation:
- `HEAD~1` refers to the commit before the current one.
- This restores the version of `hello.sh` as it existed then.

---

## ✅ 3. Return to Latest Version

Restore the latest committed version of `hello.sh` from the current branch:

```bash
git checkout main -- hello/hello.sh
cat hello/hello.sh
```

📄 Output:
```bash
#!/bin/bash

# Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```

📝 Explanation:
- This ensures the file reflects the **latest version** from the main branch.
- No commit hash is used (as required by the task).
- `git checkout main -- hello/hello.sh` works even if you're in a detached HEAD state.

---

## 💡 Notes

- `cat hello/hello.sh` is used to confirm the contents of the restored file.
- These commands affect only the **working directory**, not the Git history.
- Avoid `git reset` here; it's not required and affects HEAD instead of files.

---

## ✅ Evaluation Checklist Coverage

| Requirement                                                                 | ✅ Completed |
|-----------------------------------------------------------------------------|-------------|
| Restore first snapshot and print content                                   | ✅ Yes       |
| Restore second most recent snapshot and print content                      | ✅ Yes       |
| Return to latest version without using commit hashes                       | ✅ Yes       |

---
