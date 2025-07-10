# Task 8: Branching

## 🎯 Objective
Isolate major changes in a new branch and practice collaboration workflows using `git switch`, file edits, commits, diffs, and tree visualization.

---

## ✅ Step 1: Create and Switch to `greet` Branch
```bash
git switch -c greet
# or
git checkout -b greet
```

📤 Output:
```
Switched to a new branch 'greet'
```

---

## ✅ Step 2: Create `lib/greeter.sh`
```bash
mkdir -p lib
nano lib/greeter.sh
```

✍️ File content:
```bash
#!/bin/bash

Greeter() {
    who="$1"
    echo "Hello, $who"
}
```

✅ Make executable (optional):
```bash
chmod +x lib/greeter.sh
```

```bash
git add lib/greeter.sh
git commit -m "Add greeter function in greeter.sh"
```

Push the branch:
```bash
git push --set-upstream origin greet
```

---

## ✅ Step 3: Update `lib/hello.sh` to Use Greeter
```bash
nano lib/hello.sh
```

✍️ Updated content:
```bash
#!/bin/bash

source lib/greeter.sh

name="$1"
if [ -z "$name" ]; then
    name="World"
fi

Greeter "$name"
```

```bash
git add lib/hello.sh
git commit -m "Update hello.sh to use greeter function"
git push
```

---

## ✅ Step 4: Update `Makefile`
```bash
nano Makefile
```

✍️ Updated content:
```makefile
# Ensure it runs the updated lib/hello.sh file
TARGET="lib/hello.sh"

run:
	bash ${TARGET}
```

```bash
git add Makefile
git commit -m "Update Makefile to run updated hello.sh"
git push
```

---

## ✅ Step 5: Compare Differences with Main Branch
```bash
git switch main
```

Compare differences:
```bash
git diff greet -- Makefile
git diff greet -- lib/hello.sh
git diff greet -- lib/greeter.sh
```

📤 Example Output:
- `Makefile`: The comment line was removed or added.
- `lib/hello.sh`: Switch between inline echo and external function call.
- `lib/greeter.sh`: File missing in `main` branch.

---

## ✅ Step 6: Add README.md on Main
```bash
nano README.md
```

📄 Content:
```markdown
# Hello World Git Project

This is the Hello World example from the git project.
```

```bash
git add README.md
git commit -m "Add README.md file to main branch"
```

---

## ✅ Step 7: Commit Tree Diagram
Illustrates diverging branches.

```
* 8ec12d3 (HEAD -> main) Add README.md with project description
| * 4c2d605 (origin/greet, greet) Update Makefile to run updated hello.sh
| * 8f3ba1c Update hello.sh to use greeter function
| * 646fe2d Add greeter.sh with Greeter function
|/  
* c6510f4 (origin/main) Add documentation for Task 7: Explore Git internals (blobs, trees, commits)
* ...
```

---

✅ **Summary**: This task demonstrates branching, independent development, diffing changes, documenting progress, and understanding tree structure in Git.