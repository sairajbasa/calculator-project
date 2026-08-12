# Calculator Project

A simple Python calculator project created to understand **Python project structure, reusable modules, unit testing with pytest, and GitHub Actions CI**.

## 📁 Project Structure

```text
calculator-project/
│
├── .github/
│   └── workflows/
│       └── test-python.yml
│
├── src/
│   ├── __init__.py
│   ├── app.py
│   └── utils.py
│
├── tests/
│   └── test_app.py
│
├── requirements.txt
└── README.md
```

## 📌 Project Components

### `.github/workflows/`

Contains the GitHub Actions workflow.

* `test-python.yml` — Manually triggers the Python testing workflow.

### `src/`

Contains the application source code.

* `__init__.py` — Makes `src` a Python package.
* `app.py` — Main application file.
* `utils.py` — Contains reusable calculator functions.

### `tests/`

Contains automated tests.

* `test_app.py` — Tests the calculator functions using `pytest`.

### `requirements.txt`

Contains the Python dependencies required by the project.

```text
pytest
```

### `README.md`

Contains documentation about the project.

## ⚙️ Calculator Functions

The project provides four basic operations:

* Addition
* Subtraction
* Multiplication
* Division

Example:

```python
add(10, 5)        # 15
subtract(10, 5)   # 5
multiply(10, 5)   # 50
divide(10, 5)     # 2
```

## 🚀 Running the Project Locally

### 1. Clone the repository

```bash
git clone <repository-url>
cd calculator-project
```

### 2. Install dependencies

```bash
pip install -r requirements.txt
```

### 3. Run the application

```bash
python3 src/app.py
```

Expected output:

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

## 🧪 Running Tests Locally

Run the tests from the project root:

```bash
python -m pytest
```

Expected result:

```text
4 passed
```

The tests are located in:

```text
tests/test_app.py
```

and import the calculator functions from:

```text
src/utils.py
```

using:

```python
from src.utils import add, subtract, multiply, divide
```

## 🔄 GitHub Actions CI

This project uses **GitHub Actions** to automatically prepare the Python environment and execute the automated tests.

The workflow is located at:

```text
.github/workflows/test-python.yml
```

### Workflow Trigger

The workflow uses:

```yaml
on: workflow_dispatch
```

This means the workflow is triggered **manually**.

It does **not** automatically run when code is pushed to the repository.

### How to Run the Workflow

1. Open the GitHub repository.
2. Go to the **Actions** tab.
3. Select **Python Tests**.
4. Click **Run workflow**.
5. Select the branch if required.
6. Click **Run workflow**.

## 🔧 GitHub Actions Workflow

The current workflow is:

```yaml
name: Python Tests

on: workflow_dispatch

permissions:
  contents: read

jobs:
  test:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout repository
        uses: actions/checkout@v6

      - name: Setup Python
        uses: actions/setup-python@v6
        with:
          python-version: "3.12"

      - name: Install dependencies
        run: pip install -r requirements.txt

      - name: Run tests
        run: python -m pytest
```

## 🔍 Workflow Explanation

### 1. Workflow Name

```yaml
name: Python Tests
```

Defines the name displayed in the GitHub Actions interface.

### 2. Manual Trigger

```yaml
on: workflow_dispatch
```

Allows the workflow to be started manually from the GitHub Actions UI.

### 3. Permissions

```yaml
permissions:
  contents: read
```

Grants the workflow read-only access to repository contents.

### 4. Job

```yaml
jobs:
  test:
```

Defines a job named `test`.

### 5. Runner

```yaml
runs-on: ubuntu-latest
```

GitHub provides a temporary Ubuntu runner to execute the job.

### 6. Checkout Repository

```yaml
- name: Checkout repository
  uses: actions/checkout@v6
```

Checks out the repository code into the GitHub Actions runner workspace.

After this step, the runner can access:

```text
src/
tests/
requirements.txt
README.md
```

### 7. Setup Python

```yaml
- name: Setup Python
  uses: actions/setup-python@v6
  with:
    python-version: "3.12"
```

Sets up Python 3.12 on the Ubuntu runner.

### 8. Install Dependencies

```yaml
- name: Install dependencies
  run: pip install -r requirements.txt
```

Reads `requirements.txt` and installs the required Python packages.

In this project:

```text
requirements.txt
        ↓
      pytest
        ↓
   Installed on runner
```

### 9. Run Tests

```yaml
- name: Run tests
  run: python -m pytest
```

Runs pytest using Python.

The test flow is:

```text
python -m pytest
       ↓
tests/
       ↓
test_app.py
       ↓
Import functions from src/utils.py
       ↓
Execute test cases
       ↓
PASS / FAIL
```

## 🔄 Complete GitHub Actions Flow

```text
User
 │
 │ Manually clicks "Run workflow"
 ▼
GitHub Actions
 │
 ▼
Create Ubuntu Runner
 │
 ▼
Checkout Repository
 │
 ▼
Setup Python 3.12
 │
 ▼
Install requirements.txt
 │
 ▼
Run python -m pytest
 │
 ▼
tests/test_app.py
 │
 ├── Test add()
 ├── Test subtract()
 ├── Test multiply()
 └── Test divide()
 │
 ▼
PASS ✅ / FAIL ❌
```

## 🐍 Python Package Structure

The `src` directory contains:

```text
src/
├── __init__.py
├── app.py
└── utils.py
```

The `__init__.py` file allows `src` to be treated as a Python package.

Therefore, `test_app.py` can import functions using:

```python
from src.utils import add, subtract, multiply, divide
```

The relationship is:

```text
tests/test_app.py
       │
       │ imports
       ▼
src.utils
       │
       ▼
src/utils.py
       │
       ├── add()
       ├── subtract()
       ├── multiply()
       └── divide()
```

## 🎯 Learning Objectives

This project demonstrates:

* Python project structure
* Python modules
* Python packages
* `__init__.py`
* Reusable functions
* Unit testing
* pytest
* `requirements.txt`
* Git
* GitHub
* GitHub Actions
* Workflow triggers
* `workflow_dispatch`
* GitHub Actions runners
* `actions/checkout`
* `actions/setup-python`
* CI fundamentals
* Automated testing

## 📚 Key Concepts Learned

### Repository

The GitHub repository contains the application code, tests, dependencies, documentation, and GitHub Actions workflow.

### Runner

The runner is the temporary machine provided by GitHub to execute the workflow.

### Workflow

The YAML file under:

```text
.github/workflows/
```

defines what GitHub Actions should execute.

### Job

The `test` job runs on:

```yaml
runs-on: ubuntu-latest
```

### Steps

The job contains individual steps:

```text
Checkout
   ↓
Setup Python
   ↓
Install Dependencies
   ↓
Run Tests
```

## 📝 Future Improvements

Possible improvements include:

* Add more calculator operations
* Add more test cases
* Add code coverage
* Add Python linting
* Add `push` trigger
* Add pull request testing
* Build a Python package
* Build a Docker image
* Add Docker-based CI
* Add deployment stages
