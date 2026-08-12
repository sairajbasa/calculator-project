# Calculator Project

A simple Python calculator project created to understand **Python project structure, modules, unit testing, and GitHub Actions CI**.

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

Contains GitHub Actions workflow files.

* `test-python.yml` — Automatically sets up Python and runs the automated tests.

### `src/`

Contains the application source code.

* `__init__.py` — Makes `src` a Python package so modules inside `src` can be imported using statements such as `from src.utils import add`.
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

## 🧪 Running Tests

Run the tests from the project root:

```bash
python -m pytest
```

Expected result:

```text
4 passed
```

Using `python -m pytest` ensures that Python executes pytest as a module from the project root, allowing the `src` package to be imported correctly.

## 🔄 GitHub Actions CI

This project uses **GitHub Actions** to automatically run the Python tests.

The workflow is located at:

```text
.github/workflows/test-python.yml
```

The workflow is triggered by:

```yaml
on:
  push:
  workflow_dispatch:
```

### Workflow Process

```text
git push
    ↓
GitHub Repository
    ↓
GitHub Actions
    ↓
Checkout Repository
    ↓
Setup Python 3.12
    ↓
Install Dependencies
    ↓
python -m pytest
    ↓
Run tests
    ↓
PASS / FAIL
```

The workflow can also be started manually using the **Run workflow** button through `workflow_dispatch`.

## 🔗 Python Package Structure

The `src` directory contains an `__init__.py` file:

```text
src/
├── __init__.py
├── app.py
└── utils.py
```

This allows `src` to be treated as a Python package.

Therefore, the test file can import functions from `utils.py` using:

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
utils.py
       │
       ├── add()
       ├── subtract()
       ├── multiply()
       └── divide()
```

## 🎯 Purpose of This Project

This project is mainly for learning:

* Python project structure
* Python packages and `__init__.py`
* Python modules
* Reusable functions
* Unit testing with pytest
* `requirements.txt`
* Git and GitHub
* GitHub Actions
* Workflow triggers
* CI (Continuous Integration)
* Automated testing

## 📚 Learning Flow

```text
Write Python Code
       ↓
Create Tests
       ↓
Push Code to GitHub
       ↓
GitHub Actions Triggered
       ↓
Ubuntu Runner
       ↓
Setup Python
       ↓
Install Dependencies
       ↓
Run pytest
       ↓
Tests PASS / FAIL
```

## 📝 Future Improvements

Possible future improvements include:

* Add more calculator operations
* Add more test cases
* Add code coverage
* Add linting
* Build a Docker image
* Add a Docker workflow
* Add deployment through GitHub Actions
* Publish the application as a Python package
