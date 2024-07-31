## :rocket: ONS MkDocs Theme

This is an Office for National Statistics (ONS) branded theme that can be used in conjunction with MkDocs.

The purpose of this theme is to give users a way of generating documentation that is styled for ONS.

This theme leans heavily on the Material for MkDocs that was created by Martin Donath. The original files can be accessed from [HERE](https://github.com/squidfunk/mkdocs-material).

## :file_folder: Documentation

You can access the [documentation] for this package and see the theme live.

## :race_car: Getting Started

ONS Theme for MkDocs is a powerful documentation framework on top of [MkDocs], a static site generator for project documentation. If you're familiar with Python, you can install ONS Theme for MkDocs with `pip`, the Python package manager.

[MkDocs]: https://www.mkdocs.org

## :computer: Installation

### with pip

ONS Theme for MkDocs is published as a Python package and can be installed with
`pip`, ideally by using a [virtual environment]. Open up a terminal and install
ONS Theme for MkDocs with:

```
pip install ons-theme-for-mkdocs
```

This will automatically install compatible versions of all dependencies:
[MkDocs], [Markdown], [Pygments] and [Python Markdown Extensions].

!!! tip

    If you don't have prior experience with Python, we recommend reading
    [Using Python's pip to Manage Your Projects' Dependencies], which is a
    really good introduction on the mechanics of Python package management and
    helps you troubleshoot if you run into errors.

[virtual environment]: https://realpython.com/what-is-pip/#using-pip-in-a-python-virtual-environment
[semantic versioning]: https://semver.org/
[Markdown]: https://python-markdown.github.io/
[Pygments]: https://pygments.org/
[Python Markdown Extensions]: https://facelessuser.github.io/pymdown-extensions/
[Using Python's pip to Manage Your Projects' Dependencies]: https://realpython.com/what-is-pip/

### with git

ONS Theme for MkDocs can be directly used from [GitHub] by cloning the
repository into a subfolder of your project root which might be useful if you
want to use the very latest version:

```
git clone https://github.com/ONSdigital/ons_mkdocs_theme
```

Next, install the theme and its dependencies with: Requires Python 3.11 and above

```
conda create -n ons_mkdocs_theme python=3.11

conda activate ons_mkdocs_theme

pip install -e .
```

[GitHub]: https://github.com/ONSdigital/ons_mkdocs_theme
