<p align="center">
    <img src=".github/assets/logo.svg" width="320px">
</p>

# MkDocs ONS Theme

This is an Office for National Statistics (ONS) branded theme that can be used in conjunction with MkDocs.

The purpose of this theme is to give users a way of generating styled documentation.

This theme leans heavily on the Material for MkDocs that was created by Martin Donath. His original files can be accessed [here](https://github.com/squidfunk/mkdocs-material).

## Getting Started

ONS Theme for MkDocs is a powerful documentation framework on top of [MkDocs], a static site generator for project documentation. If you're familiar with Python, you can install ONS Theme for MkDocs with `pip`, the Python package manager.

[MkDocs]: https://www.mkdocs.org

### Installation

#### With PIP

ONS Theme for MkDocs is published as a Python package and can be installed with `pip`, ideally by using a [virtual environment]. Open up a terminal and install ONS Theme for MkDocs with:

```sh
pip install ons-theme-for-mkdocs
```

This will automatically install compatible versions of all dependencies: [MkDocs], Markdown, Pygments, and Python Markdown Extensions.

!!! tip  
If you don't have prior experience with Python, we recommend reading [Using Python's pip to Manage Your Projects' Dependencies], which is a really good introduction on the mechanics of Python package management and helps you troubleshoot if you run into errors.

#### With Git

ONS Theme for MkDocs can be directly used from GitHub by cloning the repository into a subfolder of your project root which might be useful if you want to use the very latest version:

```sh
git clone https://github.com/ONSdigital/ons-theme-for-mkdocs
```

Next, install the theme and its dependencies with:

```sh
pip install -e ons-theme-for-mkdocs
```
