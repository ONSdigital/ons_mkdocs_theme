# Customization

Project documentation is as diverse as the projects themselves and ONS MkDocs Theme is a great starting point for making it look beautiful. However, as you
write your documentation, you may reach a point where small adjustments are
necessary to preserve your brand's style.

## Adding assets

[MkDocs] provides several ways to customize a theme. In order to make a few
small tweaks to ONS Theme for MkDocs, you can just add CSS files to
the `docs` directory.

[MkDocs]: https://www.mkdocs.org

### Additional CSS

If you want to tweak some colors or change the spacing of certain elements,
you can do this in a separate style sheet. The easiest way is by creating a
new style sheet file in the `docs` directory:

```sh
.
├─ docs/
│  └─ stylesheets/
│     └─ extra.css
└─ mkdocs.yml
```

Then, add the following lines to `mkdocs.yml`:

```yaml
extra_css:
  - stylesheets/extra.css
```

## Extending the theme

If you want to alter the HTML source (e.g. add or remove some parts), you can
extend the theme. MkDocs supports [theme extension], an easy way to override
parts of ONS Theme for MkDocs without forking from git. This ensures that you
can update to the latest version more easily.

[theme extension]: https://www.mkdocs.org/user-guide/customizing-your-theme/#using-the-theme-custom_dir

### Setup and theme structure

Enable ONS Theme for MkDocs as usual in `mkdocs.yml`, and create a new folder
for `overrides` which you then reference using the [`custom_dir`][custom_dir]
setting:

```yaml
theme:
  name: material
  custom_dir: overrides
```

!!! warning "Theme extension prerequisites"

    As the [`custom_dir`][custom_dir] setting is used for the theme extension
    process, ONS Theme for MkDocs needs to be installed via `pip` and referenced
    with the [`name`][name] setting in `mkdocs.yml`. It will not work when
    cloning from `git`.

The structure in the `overrides` directory must mirror the directory structure
of the original theme, as any file in the `overrides` directory will replace the
file with the same name which is part of the original theme. Besides, further
assets may also be put in the `overrides` directory:

```{ .sh .no-copy }
.
├─ .icons/                             # Bundled icon sets
├─ assets/
│  ├─ images/                          # Images and icons
│  ├─ javascripts/                     # JavaScript files
│  └─ stylesheets/                     # Style sheets
├─ partials/
│  ├─ integrations/                    # Third-party integrations
│  │  ├─ analytics/                    # Analytics integrations
│  │  └─ analytics.html                # Analytics setup
│  ├─ languages/                       # Translation languages
│  ├─ actions.html                     # Actions
│  ├─ alternate.html                   # Site language selector
│  ├─ comments.html                    # Comment system (empty by default)
│  ├─ consent.html                     # Consent
│  ├─ content.html                     # Page content
│  ├─ copyright.html                   # Copyright and theme information
│  ├─ feedback.html                    # Was this page helpful?
│  ├─ footer.html                      # Footer bar
│  ├─ header.html                      # Header bar
│  ├─ icons.html                       # Custom icons
│  ├─ language.html                    # Translation setup
│  ├─ logo.html                        # Logo in header and sidebar
│  ├─ nav.html                         # Main navigation
│  ├─ nav-item.html                    # Main navigation item
│  ├─ pagination.html                  # Pagination (used for blog)
│  ├─ palette.html                     # Color palette toggle
│  ├─ post.html                        # Blog post excerpt
│  ├─ progress.html                    # Progress indicator
│  ├─ search.html                      # Search interface
│  ├─ social.html                      # Social links
│  ├─ source.html                      # Repository information
│  ├─ source-file.html                 # Source file information
│  ├─ tabs.html                        # Tabs navigation
│  ├─ tabs-item.html                   # Tabs navigation item
│  ├─ tags.html                        # Tags
│  ├─ toc.html                         # Table of contents
│  ├─ toc-item.html                    # Table of contents item
│  └─ top.html                         # Back-to-top button
├─ 404.html                            # 404 error page
├─ base.html                           # Base template
├─ blog.html                           # Blog index page
├─ blog-archive.html                   # Blog archive index page
├─ blog-category.html                  # Blog category index page
├─ blog-post.html                      # Blog post page
└─ main.html                           # Default page
```

[custom_dir]: https://www.mkdocs.org/user-guide/configuration/#custom_dir
[name]: https://www.mkdocs.org/user-guide/configuration/#name

### Overriding partials

In order to override a partial, we can replace it with a file of the same name
and location in the `overrides` directory. For example, to replace the original
`footer.html` partial, create a new `footer.html` partial in the `overrides`
directory:

```{ .sh .no-copy }
.
├─ overrides/
│  └─ partials/
│     └─ footer.html
└─ mkdocs.yml
```

MkDocs will now use the new partial when rendering the theme. This can be done
with any file.

### Overriding blocks

Besides overriding partials, it's also possible to override (and extend)
template blocks, which are defined inside the templates and wrap specific
features. In order to set up block overrides, create a `main.html` file inside
the `overrides` directory:

```{ .sh .no-copy }
.
├─ overrides/
│  └─ main.html
└─ mkdocs.yml
```

Then, e.g. to override the site title, add the following lines to `main.html`:

```html
{% extends "base.html" %} {% block htmltitle %}
<title>Lorem ipsum dolor sit amet</title>
{% endblock %}
```

If you intend to **add** something to a block rather than to replace it
altogether with new content, use `{{ super() }}` inside the block to include the
original block content. This is particularly useful when adding third-party
scripts to your docs, e.g.

```html
{% extends "base.html" %} {% block scripts %}
<!-- Add scripts that need to run before here -->
{{ super() }}
<!-- Add scripts that need to run afterwards here -->
{% endblock %}
```

The following template blocks are provided by the theme:

| Block name  | Purpose                                         |
| :---------- | :---------------------------------------------- |
| `analytics` | Wraps the Google Analytics integration          |
| `announce`  | Wraps the announcement bar                      |
| `config`    | Wraps the JavaScript application config         |
| `container` | Wraps the main content container                |
| `content`   | Wraps the main content                          |
| `extrahead` | Empty block to add custom meta tags             |
| `fonts`     | Wraps the font definitions                      |
| `footer`    | Wraps the footer with navigation and copyright  |
| `header`    | Wraps the fixed header bar                      |
| `hero`      | Wraps the hero teaser (if available)            |
| `htmltitle` | Wraps the `<title>` tag                         |
| `libs`      | Wraps the JavaScript libraries (header)         |
| `outdated`  | Wraps the version warning                       |
| `scripts`   | Wraps the JavaScript application (footer)       |
| `site_meta` | Wraps the meta tags in the document head        |
| `site_nav`  | Wraps the site navigation and table of contents |
| `styles`    | Wraps the style sheets (also extra sources)     |
| `tabs`      | Wraps the tabs navigation (if available)        |
