# Steps to create a library in Pypi

[![inverse code](https://img.shields.io/badge/inverse-code-brown)](https://github.com/aniceto-jolela/inverse_code)
[![pypi](https://img.shields.io/badge/pypi-build-blue)](https://pypi.org/)


### 1. Prepare your project structure

First, make sure your project has the proper structure:

your-library/ <br/>
├── src/ <br/>
│   └── your_library/ <br/>
│       ├── __init__.py <br/>
│       └── ... (your code files) <br/>
├── tests/ <br/>
│   └── ... (your test files) <br/>
├── README.md <br/>
├── LICENSE <br/>
├── pyproject.toml <br/>
└── setup.cfg (or setup.py) <br/>

### 2. Create necessary configuration files

You'll need a `pyproject.toml` file and either `setup.cfg` or `setup.py`. Modern Python packaging recommends using `pyproject.toml` with `setup.cfg`.

Here's a sample `pyproject.toml`:

```bash
[build-system]
[build-system]
requires = ["hatchling >= 1.26"]
build-backend = "hatchling.build"

[project]
name = "inverse_code"
version = "1.2"
requires-python = ">=3.10"
author = "Aniceto Jolela"
author-email = "otecina500@gmail.com"
maintainers = [{name="Aniceto Jolela", email="otecina500@gmail.com"}]
description = "Reverse Code is a library created for Python to help developers encrypt and retrieve their data in a simple way."
readme = {file = "README.md", content-type = "text/markdown"}
license = {text = "MIT"}
keywords = ["inverse_code", "inverse-code", "code", "ascii", "convert","helpers","decode","encode","win1252","asciitable","binary","bin","dec","hex","oct","unittest","test","pylintrc","yield","readme","library"]
classifiers = [
# How mature is this project? Common values are
#   3 - Alpha
#   4 - Beta
#   5 - Production/Stable
"Development Status :: 5 - Production/Stable",

# Indicate who your project is intended for
"Intended Audience :: Developers",
"License :: OSI Approved :: MIT License",

# Specify the Python versions you support here.
"Programming Language :: Python :: 3",
"Programming Language :: Python :: 3.10",
"Programming Language :: Python :: 3.11",
"Programming Language :: Python :: 3.12",
"Programming Language :: Python :: 3.13",
"Topic :: Software Development :: Libraries :: Python Modules",
"Topic :: Security :: Cryptography",
"Operating System :: OS Independent",
]

dependencies = [
    "requests",
]

[project.optional-dependencies]
pdf = ["ReportLab>=1.2", "RXP"]
rest = ["docutils>=0.3", "pack==1.1,==1.3"]
dev = [
    "pytest>=7.4.0",
    "black>=23.7.0",
    "isort>=5.12.0",
]

[project.urls]
"Homepage" = "https://github.com/aniceto-jolela/inverse_code"
"Documentation" = "https://github.com/aniceto-jolela/inverse_code/blob/main/README.md"
"Repository" = "https://github.com/aniceto-jolela/inverse_code"
"Tests" = "https://github.com/aniceto-jolela/inverse_code/tree/main/tests"
"ASCII Reference" = "https://www.ascii-code.com/"

[project.scripts]
inverse-code-cli = "inverse_code.cli:main"

[tool.hatch.build.targets.wheel]
packages = ["inverse_code"]

[tool.hatch.build.targets.sdist]
include = [
    "inverse_code",
    "README.md",
    "INVERSE_CODE.md",
    "HELPERS.md",
    "ASCII.md",
    "CONVERT.md",
    "LICENSE",
]

[tool.hatch.build]
packages = ["inverse_code"]
include = [
    "inverse_code/inverse_code/**/*.py",
    "inverse_code/inverse_code/**/*.txt",
    "inverse_code/inverse_code/**/*.md",
]


```
And a sample setup.cfg:
```bash
[metadata]
name = your-library-name
version = 0.1.0
author = Your Name
author_email = your.email@example.com
description = A short description of your library
long_description = file: README.md
long_description_content_type = text/markdown
url = https://github.com/yourusername/your-library
project_urls =
    Bug Tracker = https://github.com/yourusername/your-library/issues
classifiers =
    Programming Language :: Python :: 3
    License :: OSI Approved :: MIT License
    Operating System :: OS Independent

[options]
package_dir =
    = src
packages = find:
python_requires = >=3.6

[options.packages.find]
where = src
```
### 3. Install required tools
```bash
pip install build twine
```
4. Build your package
```bash
# This creates a distribution in the dist/ directory.
python -m build 
```

### 5. Create PyPI accounts
If you haven't already, create accounts on:

> TestPyPI (for testing): https://test.pypi.org/account/register/ 

> PyPI (for production): https://pypi.org/account/register/

### 6. Upload to TestPyPI first (recommended)
```bash
python -m twine upload --repository testpypi dist/*
```

You'll be prompted for your TestPyPI username and password.
### 7. Test the installation
```bash
pip install --index-url https://test.pypi.org/simple/ your-library-name
```
### 8. Upload to the real PyPI
Once you've confirmed everything works:
```bash
python -m twine upload dist/*
```
9. Install from PyPI
```bash
pip install your-library-name
```
#
Each of these build backends has different strengths and trade-offs.

#### Setuptools

- Pros: Mature, widely used, well-documented, comprehensive functionality
- Cons: Configuration can be verbose, older syntax can be complex
- Best for: Libraries that need compatibility with older Python versions or have complex build requirements

#### Hatchling

- Pros: Modern, simple configuration, fast, good developer experience
- Cons: Newer than setuptools (though stable)
- Best for: New projects wanting a clean, straightforward configuration that follows modern packaging standards

#### Flt-core

- Pros: Very simple for straightforward packages, minimal configuration
- Cons: Less feature-rich for complex build scenarios
- Best for: Simple, pure Python packages where you want minimal configuration

Poetry-core

- Pros: Excellent dependency resolution, lock files ensure reproducibility
- Cons: Some behavior differences from other tools, best when using Poetry for the full workflow
- Best for: Projects where dependency management is critical, or if you already use Poetry

#### PDM-backend

- Pros: PEP 621 compliant, modern features, good dependency management
- Cons: Smaller community than setuptools
- Best for: Projects that want modern tooling with good dependency management