# Creating your site

After you've [installed] ONS Theme for MkDocs, you can bootstrap your project
documentation using the `mkdocs` executable. Go to the directory where you want
your project to be located and enter:

```
mkdocs new .
```

This will create the following structure:

```bash
  .
  ├── docs/
  │ └── index.md
  └── mkdocs.yml
```

[installed]: index.md

## Configuration

### Minimal configuration

Simply set the `site_name` and add the following lines to `mkdocs.yml` to enable the theme in its basic format:

```yaml
site_name: My site
site_url: https://mydomain.org/mysite
theme:
  name: ons_mkdocs_theme
```

### Example: Full mkdocs.yml

This is an example of a mkdocs.yml file.

```yaml
site_name: Test
repo_name: Test
repo_url: https://example.com
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
  logo: assets/images/logo.svg # This should be writtten exactly like this
  favicon: assets/images/favicon.ico # This should be writtten exactly like this

nav:
  - Home: index.md
  - Getting started:
      - Installation: getting-started.md
      - Creating your site: creating-your-site.md
      - Publishing your site: publishing-your-site.md
      - Customization: customization.md
  - Contributing:
      - Reporting a bug: contributing/reporting-a-bug.md
      - Reporting a docs issue: contributing/reporting-a-docs-issue.md

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
      link: https://github.com/ONSdigital/ons-docs-site

copyright: |
  &copy;  <a href="https://www.ons.gov.uk">Office for National Statistics 2024</a>
```

## Previewing as you write

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

[--dirtyreload]: https://www.mkdocs.org/about/release-notes/#support-for-dirty-builds-990
[live preview]: http://localhost:8000

## Building your site

When you're finished editing, you can build a static site from your Markdown
files with:

```python
mkdocs build
```

This will create a new directory in your project root folder called `site`.

The contents of this directory make up your project documentation. There's no
need for operating a database or server, as it is completely self-contained.
The site can be hosted on [GitHub Pages], [GitLab Pages], a CDN of your choice
or your private web space.

[GitHub Pages]: publishing-your-site.md#github-pages
[GitLab pages]: publishing-your-site.md#gitlab-pages
