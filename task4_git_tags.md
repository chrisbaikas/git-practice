# Task 4: TAG me

## 🎯 Objective
Learn how to tag versions of your repository and navigate between them.

---

## 🛠️ Commands Used

### ✅ 1. Tag the current version as `v1`
```bash
git tag v1
```

Check:
```bash
git tag
```
Output:
```
v1
```

---

### ✅ 2. Tag the previous version as `v1-beta`
```bash
git tag v1-beta HEAD~1
```

Check again:
```bash
git tag
```
Output:
```
v1
v1-beta
```

---

### ✅ 3. Navigate between tagged versions

#### 🔁 Switch to `v1`
```bash
git checkout v1
```

Check file:
```bash
cat hello/hello.sh
```
Output:
```bash
#!/bin/bash

# Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```

---

#### 🔁 Switch to `v1-beta`
```bash
git checkout v1-beta
```

Check file:
```bash
cat hello/hello.sh
```
Output:
```bash
#!/bin/bash

# Default is "World"
name=${1:-"World"}
echo "Hello, $name"
```

---

#### 🔁 Return to main branch
```bash
git switch main
```

---

### ✅ 4. List all tags
```bash
git tag
```
Output:
```
v1
v1-beta
```

---

## 🧠 Notes

- Tags are **snapshots** used to mark specific points in history (e.g. releases).
- `HEAD~1` refers to **the commit just before the current one**.
- `git checkout <tag>` enters a **detached HEAD** state to inspect code at a tagged point.
- `git switch main` brings you back to your main development branch.
- Use `git tag` to **verify** your tags at any time.

---