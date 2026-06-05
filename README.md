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

#### Create the Virtual Environment

From the root of the repository:

```bash
uv venv
```

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

#### Install Project Dependencies

If the repository contains a `pyproject.toml` file, install dependencies with:

```bash
uv sync
```

PyCharm will now use the project's virtual environment for development and execution.
