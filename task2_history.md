# Task 2: Git History

## 1️⃣ Show full commit history

```bash
git log
```

<details>
<summary>Example output</summary>

```
commit fc958dd9e873e1494f642e73974187108c239e69 (HEAD -> main, origin/main)
Author: Chris Baikas <chrisbaikas@yahoo.gr>
Date:   Tue Jul 8 15:07:11 2025 +0300

    Add task1_commits.md documentation

commit 5ad88dd894ccba7e04917a3c699a2f15f934cac3
Author: Chris Baikas <chrisbaikas@yahoo.gr>
Date:   Tue Jul 8 14:30:10 2025 +0300

    Add default logic using parameter expansion
...
```
</details>

---

## 2️⃣ Show one-line summary of history

```bash
git log --oneline
```

```
fc958dd (HEAD -> main, origin/main) Add task1_commits.md documentation  
5ad88dd Add default logic using parameter expansion  
d80f9e1 Add comment for default parameter  
65b8053 Task 1: Add parameterized Hello script  
64291fe Task 1: Add Hello World script  
```

---

## 3️⃣ Show controlled entries

### 🔹 Show the last 2 commits

```bash
git log -n 2 --oneline
```

```
fc958dd (HEAD -> main, origin/main) Add task1_commits.md documentation  
5ad88dd Add default logic using parameter expansion  
```

### 🔹 Show commits from the last 5 minutes

```bash
git log --since="5 minutes ago" --oneline
```

(⚠️ Output may vary depending on when you run the command.)

---

## 4️⃣ Show logs in a personalized format

```bash
git log --pretty=format:"* %h %ad | %s (%d) [%an]" --date=short
```

```
* fc958dd 2025-07-08 | Add task1_commits.md documentation (HEAD -> main, origin/main) [Chris Baikas]  
* 5ad88dd 2025-07-08 | Add default logic using parameter expansion () [Chris Baikas]  
* d80f9e1 2025-07-08 | Add comment for default parameter () [Chris Baikas]  
* 65b8053 2025-07-08 | Task 1: Add parameterized Hello script () [Chris Baikas]  
* 64291fe 2025-07-08 | Task 1: Add Hello World script () [Chris Baikas]  
```

---

## ✅ Checklist for the evaluator

- ✔️ Used `git log` to display full commit history.  
- ✔️ Used `git log --oneline` for condensed view.  
- ✔️ Used `-n 2` to show last 2 commits.  
- ✔️ Used `--since="5 minutes ago"` for recent commits.  
- ✔️ Used custom `--pretty=format` output including hash, date, message, branch info, and author.