# Task 1: Git Commits - `hello.sh`

## 📋 Goal

The purpose of this task is to track incremental changes made to the `hello.sh` script using Git. Each commit must isolate a meaningful change, resulting in a clean and readable Git history with descriptive messages. Partial staging was used to split changes into multiple commits.

---

## ✅ Steps and Commits

### 1️⃣ Commit: `Task 1: Add Hello World script`

**Content added:**
```bash
echo "Hello, World"
```

**Explanation:**
- Created the initial version of the `hello.sh` script with a hardcoded greeting.
- This was the simplest possible implementation to get started.

---

### 2️⃣ Commit: `Task 1: Add parameterized Hello script`

**Content changed:**
```bash
echo "Hello, $1"
```

**Explanation:**
- Replaced the hardcoded "World" with a parameter, using `$1` to take the name from the command-line argument.
- This introduces basic dynamic behavior to the script.

---

### 3️⃣ Commit: `Add comment for default parameter`

**Content added:**
```bash
# Default is "World"
```

**Method used:**
- Used `git add -p` and chose `e` (manual edit) to selectively stage **only** the comment line.
- Committed this change separately as requested.

**Why:**
- To demonstrate an understanding of partial staging and maintain clean, atomic commits.

---

### 4️⃣ Commit: `Add name parameter expansion and greeting`

**Content added:**
```bash
name=${1:-"World"}
echo "Hello, $name"
```

**Explanation:**
- Added logic to support a default greeting ("World") when no argument is passed.
- Replaced `$1` with a named variable using Bash parameter expansion.

---

## 🧠 Lessons Learned

- Used `git init`, `git status`, `git add`, and `git commit` commands in the correct order.
- Learned how to stage only specific parts of a file using `git add -p` with **manual hunk editing**.
- Gained experience in creating **atomic commits** to improve readability and auditability of Git history.
- Validated everything with `git log`.

---

## 🔍 Final Commit History

```bash
git log --oneline
```

Output:
```
e8f6293 Add name parameter expansion and greeting
928ee2f Add comment for default parameter
bfd561d Task 1: Add parameterized Hello script
53bdfbc Task 1: Add Hello World script
```
