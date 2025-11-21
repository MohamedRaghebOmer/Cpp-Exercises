# Cpp Exercises

Welcome to my **Cpp Exercises** repository! This repository is a collection of my progress and practice in **C++** programming. It includes 6 independent submodules, each representing a full course I followed with **Engineer Mohamed Abou Haddoud**. Each course contains around **50 folders**, with each folder holding a unique solved **programming problem**. No problem or idea is repeated across folders or courses.

This repository is continuously **updated** to reflect my growth and improvements in C++. All submodules have their own `README` explaining their contents in detail.

---

## Table of Contents

1. [About this repository](#about-this-repository)
2. [Included course submodules](#included-course-submodules)
3. [Why this structure](#why-this-structure)
4. [How to clone (with submodules)](#how-to-clone-with-submodules)
5. [Repository layout and conventions](#repository-layout-and-conventions)
6. [How to open & run exercises (Visual Studio Community 2022)](#how-to-open--run-exercises-visual-studio-community-2022)
7. [Coding style & best practices](#coding-style--best-practices)
8. [How to contribute / add solutions](#how-to-contribute--add-solutions)
9. [Issues, PRs, and tracking your progress](#issues-prs-and-tracking-your-progress)
10. [Suggested badges and metadata](#suggested-badges-and-metadata)
11. [License & credits](#license--credits)

---

## About this repository

**Cpp Exercises** is a curated container for six standalone C++ exercise repositories (added as Git submodules). Each submodule represents a full course walked with the instructor **Mohamed Abu Hadhoud** and contains roughly **~50 folders**, each folder holding a single solved programming problem. The problems are intentionally unique — no repeated ideas across folders — and together they reflect a progressive record of your C++ skills.

This meta-repo's purpose:

* Keep all your course repositories unified in one place while preserving their independent history.
* Make it easy to clone, browse, and run any exercise locally.
* Show continuous progress: keep the repo up-to-date as you finish more exercises.

---

## Included course submodules

These are the six course repositories (submodule names reflect your naming):

* `Cpp-Exercises-level-1-Course-3`
* `Cpp-Exercises-level2-Course5`
* `Improve-my-Cpp-knowledge-Course-6`
* `Cpp-Exercises-Course-7`
* `Cpp-Exercises-Course-8`
* `Cpp-Exercises-Course-10`

> Each submodule contains its own `README.md` that documents that course (what it covers, tips, and how folders are organized). Open each submodule to read course-specific notes.

---

## Why this structure

* **Submodules** keep each course self-contained (history, issues, and README per course).
* Large number of exercises per course can be browsed independently or together.
* Easier to reuse or extract a single course to another repo without copying files.

---

## How to clone (with submodules)

Clone this meta-repo together with all submodules in one command:

```bash
git clone --recurse-submodules https://github.com/<MohamedRaghebOmer>/Cpp-Exercises.git
```

If you already cloned without submodules, initialize and fetch them:

```bash
git submodule update --init --recursive
```

To update submodules later (pull latest commits from each submodule):

```bash
git submodule foreach git pull origin main
# or replace 'main' with the correct branch name used by each submodule
```

To add a new course submodule (maintainers only):

```bash
git submodule add https://github.com/<your-username>/<submodule-repo> path/to/submodule-directory
git commit -m "Add <submodule>"
```

---

## Repository layout and conventions

Recommended layout (top-level of this meta-repo):

```
Cpp-Exercises/                # this repo (meta)
├─ README.md                   # this file
├─ .gitmodules                 # auto-generated submodule config
├─ Cpp-Exercises-level-1-Course-3/    # submodule
├─ Cpp-Exercises-level2-Course5/      # submodule
├─ Improve-my-Cpp-knowledge-Course-6/ # submodule
├─ Cpp-Exercises-Course-7/            # submodule
├─ Cpp-Exercises-Course-8/            # submodule
└─ Cpp-Exercises-Course-10/           # submodule
```

Inside each course submodule the typical structure you follow is:

```
Course-Repo/
├─ README.md                # course description & instructions
├─ 01_SomeProblem/
│  ├─ README.md             # problem description + approach notes
│  ├─ solution.cpp          # solved code (should compile with MSVC)
│  └─ input.txt             # (optional) sample inputs
├─ 02_OtherProblem/
│  └─ ...
└─ samples/                 # optional runnable examples or solutions
```

**Naming convention for folders**: use a 2-digit prefix `01_`, `02_`, etc., followed by a short descriptive title. Each folder must contain a `README.md` explaining the problem, constraints, complexity, and the solution idea.

---

## How to open & run exercises (Visual Studio Community 2022)

You use Visual Studio Community 2022 as your primary environment. Here are two recommended workflows depending on how you prefer to organize exercises:

### Option A — Single-solution per exercise (recommended for focused editing)

1. Create a new Solution in Visual Studio: `File -> New -> Project -> Empty Project (C++)`.
2. For the exercise you want to run, add its `.cpp` file: `Add -> Existing Item`.
3. Make sure project uses C++17 or C++14 depending on your code (Project Properties -> C/C++ -> Language -> C++ Language Standard).
4. Build (Ctrl+Shift+B) and Run (F5 or Ctrl+F5).

### Option B — One Solution containing many exercise projects

1. Create a solution and add multiple small projects (one per exercise folder). This is useful for batch testing many solutions.
2. Use `Add -> New Project` and `Add -> Existing Item` to copy solution files into each project.
3. Keep projects small to avoid long build times.

### If you prefer CMake (optional)

* Add a small `CMakeLists.txt` per exercise and use Visual Studio's CMake support. This makes cross-platform usage easier.

**Tips**:

* Keep `using namespace std;` where you prefer (consistency matters).
* Avoid global variables across exercises.
* If an exercise needs input files, set the file as working directory contents in Debugging settings.

---

## Coding style & best practices

Because this repo documents your learning path, maintain readable and beginner-friendly code:

* Prefer clarity over cleverness.
* Avoid advanced/modern C++ features if the goal is to follow the course material. Keep solutions simple and educational.
* Use descriptive variable/function names.
* Add a short comment block at the top of each `solution.cpp` describing the problem, complexity, and approach (English only).
* Keep line length reasonable and format consistently.

Suggested header for each solution file (3–6 lines):

```cpp
// Problem: Short problem title
// Course: Course # - Exercise #
// Approach: short explanation
```

---

## How to contribute / add solutions

If you want to add new solved exercises or improve existing ones, follow these steps:

1. **Work on a branch**: `git checkout -b feature/add-exercise-XX`.
2. **Add a new folder** under the appropriate course submodule (if you have submodule write access). If you don't have direct write access, fork the course repo and add the folder there, then open a PR.
3. Include at minimum:

   * `solution.cpp` (the code)
   * `README.md` (problem statement, sample I/O, approach, complexity)
   * `input.txt` / `output.txt` (optional sample files)
4. Run locally in Visual Studio and ensure it builds.
5. Commit and open a Pull Request describing your changes.

> Note about submodules: If you change a submodule's contents locally, remember to commit inside the submodule and then commit the meta-repo to update the submodule pointer.

---

## Issues, PRs, and tracking your progress

* Track problems you want to revisit using GitHub Issues or a dedicated `progress.md` file in this meta-repo.
* Consider adding a simple `progress.json` or `progress.md` that logs completed exercises per course with dates. This helps show continuous improvement.

Example entry for `progress.md`:

```
- 2025-11-20: Cpp-Exercises-level-1-Course-3/01_BasicSyntax - solved
- 2025-11-21: Cpp-Exercises-level2-Course5/05_Arrays - solved
```

---

## Suggested badges and metadata

Place these in the top of this README or the repository profile to make it look professional:

* Build status (if you add CI)
* Submodules count
* Exercises completed (dynamic badge you update manually)
* License (MIT)

Example markdown snippet for badges:

```
![submodules](https://img.shields.io/badge/submodules-6-blue)
![exercises](https://img.shields.io/badge/exercises-~300-lightgrey)
![license](https://img.shields.io/badge/license-MIT-green)
```

---

## License & credits

* Default license: **MIT**.
* Credits: Instructor — **ENG/ Mohamed Abu Hadhoud** — for the course material and guidance.
* You (author): keep your name in the repository description and top-level `README`.

---

## 📫 Contact

- **Telegram**: [@Mohamed_Ragheb0](https://t.me/Mohamed_Ragheb0)

- **Email**: mohamedraghebomer@gmail.com
---

