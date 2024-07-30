# Getting started

ONS Theme for MkDocs is a powerful documentation framework on top of [MkDocs],
a static site generator for project documentation. If you're familiar with
Python, you can install ONS Theme for MkDocs with `pip`, the Python
package manager.

[MkDocs]: https://www.mkdocs.org

## Installation

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
git clone https://github.com/ONSdigital/ons-theme-for-mkdocs
```

Next, install the theme and its dependencies with:

```
pip install -e ons-theme-for-mkdocs
```

[GitHub]: https://github.com/ONSdigital/ons-theme-for-mkdocs
