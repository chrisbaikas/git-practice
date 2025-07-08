# Task 6 – Move it

## 🎯 Objective
Restructure the project and automate script execution:

1. Move `hello.sh` into a `lib/` directory using Git commands.
2. Create and commit a `Makefile` with a target that runs the script.

---

## ✅ Step 1: Move `hello.sh` into `lib/`

### 🔧 Commands Used:
```bash
mkdir lib
git mv hello.sh lib/
git commit -m "Move hello.sh to lib directory"
```

### 📁 New structure:
```
.
├── lib/
│   └── hello.sh
```

### ✔ Outcome:
- `hello.sh` is now under `lib/`
- The move was tracked by Git and committed properly

---

## ✅ Step 2: Create and Commit Makefile

### 📄 Makefile Contents:
```Makefile
TARGET="lib/hello.sh"

run:
	bash ${TARGET}
```

### 🔧 Commands Used:
```bash
git add Makefile
git commit -m "Add Makefile to run lib/hello.sh"
```

### ▶ Usage:
Run the script with:
```bash
make run
```

---

## 📝 Summary
This task introduced basic file reorganization using `git mv`, and automation of command execution via a `Makefile`, improving structure and usability of the project.