# Python PyTest Demo

![Tests](https://github.com/YOUR_GITHUB_USERNAME/python-pytest-demo/workflows/Run%20Tests/badge.svg)

A demonstration of Python testing with PyTest and GitHub Actions.

## Features

- Math utilities with comprehensive tests
- String utilities with error handling
- Automated testing with GitHub Actions
- Test coverage reporting
- Multi-Python version testing

## Running Tests

```bash
# Install dependencies
pip install -r requirements.txt

# Run all tests
PYTHONPATH=. pytest

# Run with coverage
PYTHONPATH=. pytest --cov=math_utils --cov=string_utils

# Run specific test file
PYTHONPATH=. pytest tests/test_math_utils.py
```
