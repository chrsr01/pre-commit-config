# Pre-commit Hooks for Jupyter Notebooks

This repository contains a set of pre-commit hooks I use for working with Jupyter Notebooks. These hooks help maintain a clean and consistent codebase by enforcing formatting rules, trimming unnecessary whitespace, and stripping output from notebooks before committing.

## Why Use Pre-commit Hooks?
Pre-commit hooks are scripts that run automatically before you make a commit. They help:
- Prevent unnecessary large files from being committed.
- Ensure consistent formatting of Python imports.
- Strip output from Jupyter Notebooks to avoid unwanted diffs.
- Maintain cleaner and more maintainable code.

## Installation
### 1. Paste `pre-commit-config.yaml` in your Repository 
Ensure you have `pre-commit` installed. If not, install it using:

```bash
pip install pre-commit
```

Alternatively, if you are using `conda`, install it via:

```bash
conda install -c conda-forge pre-commit
```

### 3. Install the Pre-commit Hooks
Run the following command to install the hooks:

```bash
pre-commit install
```

This will set up the pre-commit hooks in your local Git repository.

## Configured Hooks
The `.pre-commit-config.yaml` file in this repository includes the following hooks:

### General Code Cleanups
- **trailing-whitespace**: Removes trailing whitespace.
- **end-of-file-fixer**: Ensures files end with a newline.
- **check-yaml**: Checks for syntax errors in YAML files.
- **check-added-large-files**: Prevents committing large files by mistake.

### Python Imports Formatting
- **isort**: Automatically sorts Python imports for better readability and consistency.

### Jupyter Notebook Cleaning
- **nbstripout**: Strips output from Jupyter notebooks before committing to keep diffs clean.
  - This is particularly useful in collaboration settings where notebook output should not be version-controlled.
  - The hook installs `.gitattributes` to enforce stripping for all notebooks in the repository.

## Running Hooks Manually
To run the pre-commit hooks manually on all files, use:

```bash
pre-commit run --all-files
```

This is useful if you want to check the status of all files before committing.

## Updating Hooks
To update the pre-commit hooks to their latest versions, run:

```bash
pre-commit autoupdate
```
