---
hide:
  - navigation
title: ONS MkDocs Theme - Creating Your Site
---

<style>
  .md-typeset h1,
  .md-content__button {
    display: none;
  }
</style>

<style> .md-typeset h1 { display: none; } .md-main__inner { margin-top: 0px; } .md-content__button { display: none; } </style>

After you've [installed] ONS MkDocs Theme, you can create your project
documentation using the `mkdocs` executable. In the terminal, ensure you are in your project's root folder and run the following command:

```
mkdocs new .
```

This will add the following file structure:

```bash
  .
  ├── docs/
  │ └── index.md
  └── mkdocs.yml
```

## :cook: Configuration

Simply add the following lines to `mkdocs.yml` to enable the theme in its basic format:

```yaml
site_name: <insert site name>
repo_name: <insert repo name>
repo_url: <insert repo url>
docs_dir: docs

theme:
  name: ons_mkdocs_theme
  features:
    - announce.dismiss
    - content.action.edit
    - content.action.view
    - content.code.annotate
    - content.code.copy
    - content.code.select
    - content.footnote.tooltips
    - content.tabs.link
    - content.tooltips
    - navigation.tabs
    - navigation.tabs.sticky
    - navigation.top
    - navigation.tracking
    - search.highlight
    - search.share
    - search.suggest
  language: en
  logo: assets/images/logo.svg
  favicon: assets/images/favicon.ico

plugins:
  - search:
      enabled: true

markdown_extensions:
  - abbr
  - admonition
  - attr_list
  - def_list
  - footnotes
  - md_in_html
  - pymdownx.highlight:
      anchor_linenums: true
      line_spans: __span
      pygments_lang_class: true
  - pymdownx.emoji:
      emoji_index: !!python/name:material.extensions.emoji.twemoji
      emoji_generator: !!python/name:material.extensions.emoji.to_svg

extra:
  social:
    - icon: fontawesome/brands/github
      link: <insert repo link>

# Do not remove the copy right section. But you can change the copyright information.
copyright: |
  &copy;  <a href="https://www.ons.gov.uk">Office for National Statistics 2024</a>
```

The `plugins` and `features` can be removed or new ones added to you liking. To view the available plugins and feature, take a look at [Material for MkDocs][material]

!!! banner "Information"

    If your site contains only 1 page then edit the **index.md** file in the **docs** folder. For information on how to write Markdown file, the [Markdown Guide][Markdown Guide] will explain how to do this.

For a documentation site with more than 1 page, you can add a navigation section to the `mkdocs.yml` file, like so....

```yaml
nav:
  - Home: index.md
  - Getting started:
      - Installation: getting-started.md
      - Creating your site: creating-your-site.md
      - Publishing your site: publishing-your-site.md
      - customisation: customisation.md
  - Contributing:
      - Reporting a bug: contributing/reporting-a-bug.md
      - Reporting a docs issue: contributing/reporting-a-docs-issue.md
```

!!! banner "Information"

    If there is no navigation section in the `mkdocs.yml` file, there is no navigation displayed at the top of the site.

    The first layer of indentation, for example `Home`, is the name and link that will appear on the navigation at the top of the site.

    The second indentation that you can see after `Getting Started`, is the name and link that will display on left side navigation when the user clicks on `Getting Started`.

You can edit the contents of the `nav` section to your liking, but it must follow the same format. The links are relative to the `docs` folder.

## :computer: Previewing as you write

MkDocs includes a live preview server, so you can preview your changes as you
write your documentation. The server will automatically rebuild the site upon
saving. Start it with:

```python
mkdocs serve
```

Point your browser to [localhost:8000][live preview] and you should see the current version of the site:

1.  If you have a large documentation project, it might take minutes until
    MkDocs has rebuilt all pages for you to preview. If you're only interested
    in the current page, the [`--dirtyreload`][--dirtyreload] flag will make
    rebuilds much faster:

```python
mkdocs serve --dirtyreload
```

When you are happy with the contents of the site you can then move on to building it for deployment.

[Building Your Site][building]{ .md-button .md-button--primary}

[Markdown Guide]: https://www.markdownguide.org/
[installed]: setup.md
[material]: https://squidfunk.github.io/mkdocs-material/plugins/
[--dirtyreload]: https://www.mkdocs.org/about/release-notes/#support-for-dirty-builds-990
[live preview]: http://localhost:8000
[building]: building-your-site.md
