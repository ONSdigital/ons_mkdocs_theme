# Publishing your site

The great thing about hosting project documentation in a `git` repository is
the ability to deploy it automatically when new changes are pushed. MkDocs
makes this ridiculously simple.

## GitHub Pages

If you're already hosting your code on GitHub, [GitHub Pages] is certainly
the most convenient way to publish your project documentation. It's free of
charge and pretty easy to set up.

[GitHub Pages]: https://pages.github.com/

Using [GitHub Actions] you can automate the deployment of your project
documentation. At the root of your repository, create a new GitHub Actions
workflow, e.g. `.github/workflows/ci.yml`, and copy and paste the following
contents:

```yaml
name: "Deploy GitHub Pages"

on:
  push:
    branches:
      - main

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Check out repository
        uses: actions/checkout@v4

      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: "3.11"

      - name: Install dependencies
        run: |
          python -m pip install --upgrade pip
          pip install -r requirements.txt

      - name: Build the MkDocs site
        run: python -m mkdocs build

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./site
```

Now, when a new commit is pushed to `main` branches,
the static site is automatically built and deployed. Push your changes to see
the workflow in action.

If the GitHub Page doesn't show up after a few minutes, go to the settings of
your repository and ensure that the [publishing source branch] for your GitHub
Page is set to `gh-pages`.

[GitHub Actions]: https://github.com/features/actions
[MkDocs plugins]: https://github.com/mkdocs/mkdocs/wiki/MkDocs-Plugins
[personal access token]: https://docs.github.com/en/github/authenticating-to-github/creating-a-personal-access-token
[GitHub secrets]: https://docs.github.com/en/actions/configuring-and-managing-workflows/creating-and-storing-encrypted-secrets
[publishing source branch]: https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site
[manual page]: https://man7.org/linux/man-pages/man1/date.1.html

## GitLab Pages

If you're hosting your code on GitLab, deploying to [GitLab Pages] can be done
by using the [GitLab CI] task runner. At the root of your repository, create a
task definition named `.gitlab-ci.yml` and copy and paste the following
contents:

```yaml
pages:
  stage: deploy
  image: python:latest
  script:
    - pip install ons-theme-for-mkdocs
    - mkdocs build --site-dir public
  artifacts:
    paths:
      - public
  rules:
    - if: "$CI_COMMIT_BRANCH == $CI_DEFAULT_BRANCH"
```

Now, when a new commit is pushed to the [default branch], the static site is automatically built and deployed. Commit and push
the file to your repository to see the workflow in action.

### with MkDocs

If you prefer to deploy your project documentation manually, you can just invoke
the following command from the directory containing the `mkdocs.yml` file:

```
mkdocs gh-deploy --force
```

This will build your documentation and deploy it to a branch
`gh-pages` in your repository. See [this overview in the MkDocs
documentation] for more information. For a description of the
arguments, see [the documentation for the command].

[this overview in the MkDocs documentation]: https://www.mkdocs.org/user-guide/deploying-your-docs/#project-pages
[the documentation for the command]: https://www.mkdocs.org/user-guide/cli/#mkdocs-gh-deploy
[GitLab Pages]: https://gitlab.com/pages
[GitLab CI]: https://docs.gitlab.com/ee/ci/
[masked custom variables]: https://docs.gitlab.com/ee/ci/variables/#create-a-custom-variable-in-the-ui
[default branch]: https://docs.gitlab.com/ee/user/project/repository/branches/default.html
[Azure]: https://bawmedical.co.uk/t/publishing-a-material-for-mkdocs-site-to-azure-with-automatic-branch-pr-preview-deployments/763
[Cloudflare Pages]: https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-cloudflare/
[DigitalOcean]: https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-digitalocean-app-platform/
[Flyio]: https://documentation.breadnet.co.uk/cloud/fly/mkdocs-on-fly/
[Netlify]: https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-netlify/
[Vercel]: https://www.starfallprojects.co.uk/projects/deploy-host-docs/deploy-mkdocs-material-vercel/
[Codeberg Pages]: https://andre601.ch/blog/2023/11-05-using-codeberg-pages/
