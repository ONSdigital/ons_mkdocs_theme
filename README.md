<p align="center" style="padding: 50px">
    <img src="https://onsdigital.github.io/ons_mkdocs_theme/assets/images/logo.svg" width="450px">
</p>

## :rocket: MkDocs ONS Theme

This is an Office for National Statistics (ONS) branded theme that can be used in conjunction with MkDocs.

The purpose of this theme is to give users a way of generating documentation that is styled for ONS.

This theme leans heavily on the Material for MkDocs that was created by Martin Donath. The original files can be accessed from [GitHub].

## :file_folder: Documentation

You can access the [documentation] for this package and see the theme live.

## Getting Started

ONS MkDocs Theme is a powerful documentation framework on top of [MkDocs], a static site generator for project documentation. If you're familiar with Python, you can install ONS MkDocs Theme with `pip`, the Python package manager.

## :computer: Installation

#### With PIP

ONS MkDocs Theme is published as a Python package and can be installed with `pip`, ideally by using a [virtual environment](https://conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html). Open up a terminal and install ONS MkDocs Theme with:

```py
pip install ons_mkdocs_theme
```

This will automatically install compatible versions of all dependencies: [MkDocs], [Markdown], [Pygments], and Python Markdown Extensions.

!!! tip  
If you don't have prior experience with Python, we recommend reading [Using Python's pip to Manage Your Projects' Dependencies](https://facelessuser.github.io/pymdown-extensions/), which is a really good introduction on the mechanics of Python package management and helps you troubleshoot if you run into errors.

#### With Git

ONS MkDocs Theme can be directly used from GitHub by cloning the repository into a subfolder of your project root.

```sh
git clone https://github.com/ONSdigital/ons_mkdocs_theme
```

Next, install the theme and its dependencies with:

```sh
pip install -e ons-theme-for-mkdocs
```

[MkDocs]: https://www.mkdocs.org
[GitHub]: https://github.com/squidfunk/mkdocs-material
[Markdown]: https://www.markdownguide.org/getting-started/#:~:text=Markdown%20is%20a%20lightweight%20markup,than%20using%20a%20WYSIWYG%20editor.
[Pygments]: https://pygments.org/
[documentation]: https://onsdigital.github.io/ons_mkdocs_theme/
