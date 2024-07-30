# Creating your site

After you've [installed] ONS Theme for MkDocs, you can bootstrap your project
documentation using the `mkdocs` executable. Go to the directory where you want
your project to be located and enter:

```
mkdocs new .
```

This will create the following structure:

```
 .
 ├─ docs/
 │  └─ index.md
 └─ mkdocs.yml
```

[installed]: getting-started.md

## Configuration

### Minimal configuration

Simply set the `site_name` and add the following lines to `mkdocs.yml` to enable the theme:

```
  site_name: My site
  site_url: https://mydomain.org/mysite
  theme:
    name: ons-theme-for-mkdocs
```

## Previewing as you write

MkDocs includes a live preview server, so you can preview your changes as you
write your documentation. The server will automatically rebuild the site upon
saving. Start it with:

```
mkdocs serve
```

1.  If you have a large documentation project, it might take minutes until
    MkDocs has rebuilt all pages for you to preview. If you're only interested
    in the current page, the [`--dirtyreload`][--dirtyreload] flag will make
    rebuilds much faster:

    ```
    mkdocs serve --dirtyreload
    ```

Point your browser to [localhost:8000][live preview] and you should see the current version of the site:

[--dirtyreload]: https://www.mkdocs.org/about/release-notes/#support-for-dirty-builds-990
[live preview]: http://localhost:8000

## Building your site

When you're finished editing, you can build a static site from your Markdown
files with:

```
mkdocs build
```

The contents of this directory make up your project documentation. There's no
need for operating a database or server, as it is completely self-contained.
The site can be hosted on [GitHub Pages], [GitLab Pages], a CDN of your choice
or your private web space.

[GitHub Pages]: publishing-your-site.md#github-pages
[GitLab pages]: publishing-your-site.md#gitlab-pages
