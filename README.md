# CIS 340 Introduction to Programming in Python

## 1. Introduction

This repository contains the work to be completed for the **CIS 340 Introduction to Programming in Python** course.

## 2. Getting Started

### 2.1 Install PyCharm

1. Download PyCharm from https://www.jetbrains.com/pycharm/download
2. Install PyCharm using the default installation options.
3. Launch PyCharm after installation is complete.

### 2.2 Clone the Repository

1. Open a terminal or command prompt.
2. Navigate to the directory where you would like to store the course files.
3. Clone the repository:

```bash
git clone https://github.com/RapidOstrich/cis_340.git
```

4. Open PyCharm and select **Open**.
5. Browse to the cloned repository and open it as a project.

### 2.3 Configure uv in PyCharm

**uv** is recommended for Python package and virtual environment management.

#### Install uv

**Windows (PowerShell):**

```powershell
powershell -ExecutionPolicy ByPass -c "irm https://astral.sh/uv/install.ps1 | iex"
```

**macOS/Linux:**

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
```

Verify the installation:

```bash
uv --version
```

#### Install Project Dependencies

From the root of the repository, run:

```bash
uv sync
```

This creates the virtual environment and installs all dependencies in one step.

#### Configure PyCharm to Use the uv Environment

1. Open **File → Settings** (Windows/Linux) or **PyCharm → Settings** (macOS).
2. Navigate to **Project: CIS 340 → Python Interpreter**.
3. Click **Add Interpreter**.
4. Select **Existing Environment**.
5. Choose the Python executable located in:

**Windows:**

```text
.venv\Scripts\python.exe
```

**macOS/Linux:**

```text
.venv/bin/python
```

6. Click **OK** and apply the changes.

### 2.4 Set Up Pre-Commit Hooks

Pre-commit hooks automatically check your code for formatting and style issues before each commit. Run this once after cloning:

```bash
uv run pre-commit install
```

After this, every `git commit` will run the checks automatically. If a check fails, fix the reported issues and commit again.

## 3. Workflow

The `main` branch is protected — changes cannot be pushed directly. All work must go through a pull request:

1. Create a new branch from `main`:

```bash
git checkout main
git checkout -b your-branch-name
```

2. Make your changes and commit them.
3. Push the branch to GitHub:

```bash
git push origin your-branch-name
```

4. Open a pull request into `main` on GitHub and merge once the CI pipeline passes.

## 4. CI Pipeline

Every push and pull request runs the **Python CI** pipeline on GitHub Actions, which checks:

| Step | Tool | What it catches |
|---|---|---|
| Formatting | black | Code that isn't formatted consistently |
| Style | flake8 | Bad patterns, unused imports, line length |
| Syntax | py_compile | Python files that can't be parsed |

You can also trigger the pipeline manually from the **Actions** tab on GitHub using the **Run workflow** button.

If the pipeline fails on your pull request, read the error output, fix the issue locally, and push again.
