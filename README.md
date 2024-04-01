# Visual Update Express Docs

![Poetry](https://img.shields.io/badge/Poetry-%233B82F6.svg?style=for-the-badge&logo=poetry&logoColor=0B3D8D) [![Build and Deploy Workflow](https://github.com/soner-boztas/visual-update-express-docs/actions/workflows/build_and_deploy.yml/badge.svg?branch=main&event=push)](https://github.com/soner-boztas/visual-update-express-docs/actions/workflows/build_and_deploy.yml)

## Overview

This repository contains the source files for the official documentation of Visual Update Express.

The rendered documentation is hosted on GitHub Pages and is accessible through this URI: https://soner-boztas.github.io/visual-update-express-docs/

## Contributing

Any contributions to the Visual Update Express documentation is highly appreciated. Please use the _fork and pull request_ pattern for this intention.

## Setting up the Development Environment

In order to work on the documentation, you will first need to set up the development environment on your local machine. We use [MkDocs](https://www.mkdocs.org/) for the documentation and Python Poetry for dependency management. As a consequence, you need to have Python version `3.12+` installed as a prerequisite[^1]. As for Poetry, you are encouraged to install it via _pipx_ (`$ pipx install poetry`). Finally, you will need to set up your Poetry environment; follow these steps:
1. Clone this repository to the file system of your local machine.
2. Switch (`cd`) to the repository root folder (this is where the file `pyproject.toml` file resides).
3. Execute the command-line `poetry install` in your shell. This will create a Python virtual environment inside the repository root folder and install all dependencies into it (such as MkDocs).
4. Execute the command-line `poetry run mkdocs serve` in order to spawn a development web server for previewing any changes to the documentation source files. 

---

Author: Soner Boztas

[^1]: Any Python distribution such as CPython, Anaconda or Miniforge is fine. However, we recommend CPython: https://python.org.
