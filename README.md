# calculator-project
# Calculator Project

A simple Python calculator project created to understand **Python project structure, unit testing, and GitHub Actions CI**.

## 📁 Project Structure

```text
calculator-project/
│
├── .github/
│   └── workflows/
│       └── test-python.yml
│
├── src/
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

### `src/`

Contains the application source code.

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

### `.github/workflows/`

Contains GitHub Actions workflow files.

* `test-python.yml` — Automatically runs the Python tests.

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
python src/app.py
```

Expected output:

```text
Addition: 15
Subtraction: 5
Multiplication: 50
Division: 2.0
```

## 🧪 Running Tests

Run:

```bash
pytest
```

If all tests pass, you should see output similar to:

```text
4 passed
```

## 🔄 GitHub Actions CI

This project uses **GitHub Actions** to automatically run the tests.

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
Setup Python
    ↓
Install Dependencies
    ↓
Run pytest
    ↓
PASS / FAIL
```

The workflow can also be started manually using the **Run workflow** button through `workflow_dispatch`.

## 🎯 Purpose of This Project

This project is mainly for learning:

* Python project structure
* Python modules
* Reusable functions
* Unit testing with pytest
* `requirements.txt`
* Git and GitHub
* GitHub Actions
* CI (Continuous Integration)
* Workflow triggers
* Automated testing

## 📚 Learning Flow

```text
Python Code
    ↓
Write Tests
    ↓
Push Code to GitHub
    ↓
GitHub Actions
    ↓
Automated Tests
    ↓
PASS / FAIL
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
