---
hide:
  - navigation
title: ONS MkDocs Theme - Setup
---

<style>
  .md-typeset h1,
  .md-content__button {
    display: none;
  }
</style>

<style> .md-typeset h1 { display: none; } .md-main__inner { margin-top: 0px; } .md-content__button { display: none; } </style>

## :race_car: Getting Started

Setting up your documentation site to use this theme couldn't be easier. The quickest and easiest way to get up and running is to install with `pip`.

To be able to use this theme, you need to be using at least **Python v3.11**.

### :computer: Installation

#### with pip

ONS MkDocs Theme is published as a Python package and can be installed with
`pip`, ideally by using a [virtual environment]. Open up a terminal and install
ONS MkDocs Theme with:

```
pip install ons_mkdocs_theme
```

This will automatically install compatible versions of all dependencies:
[MkDocs], [Markdown], [Pygments] and [Python Markdown Extensions][Python Markdown Extensions].

!!! tip

    If you don't have prior experience with Python, we recommend reading
    [Using Python's pip to Manage Your Projects' Dependencies], which is a
    really good introduction on the mechanics of Python package management and
    helps you troubleshoot if you run into errors.

#### with git

ONS MkDocs Theme can be directly used from [GitHub] by cloning the
repository into a subfolder of your project root folder.

Simply create a folder called `ons_mkdocs_theme`. In the terminal, ensure you are in the root folder directory of your project and run the following command:

```
mkdir ons_mkdocs_theme
```

You then need to `cd` into the new directory with the following command:

```
cd ons_mkdocs_theme
```

To clone the theme files, run the following command:

```
git clone https://github.com/ONSdigital/ons_mkdocs_theme
```

Next, install the theme and its dependencies with:

```
pip install -e .
```

[Create Your Site][create]{ .md-button .md-button--primary}

[GitHub]: https://github.com/ONSdigital/ons_mkdocs_theme
[virtual environment]: https://realpython.com/what-is-pip/#using-pip-in-a-python-virtual-environment
[semantic versioning]: https://semver.org/
[MkDocs]: https://mkdocs.org
[Markdown]: https://python-markdown.github.io/
[Pygments]: https://pygments.org/
[Python Markdown Extensions]: https://facelessuser.github.io/pymdown-extensions/
[Using Python's pip to Manage Your Projects' Dependencies]: https://realpython.com/what-is-pip/
[create]: creating-your-site.md
