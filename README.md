# GitHub Handbook

## Information

The `pages` site is driven by [Jekyll static site](https://jekyllrb.com/).

GitHub `pages` sites can be `private` or `public` in github.com. However, the repository behind those pages sites can be `private` or `internal` (if hosted in an organization) which restricts the users that have `write-access` to those that have explicit permission.

## Contributing as a member of the repository

* See [CONTRIBUTING.md](/CONTRIBUTING.md) for
  * How this Jekyll site is organized
  * How to use Markdown for writing/editing content
  * How to update the ```modified-date``` that displays on site pages.

## Development

This is a [Jekyll static site](https://jekyllrb.com/).

### Setting up your local dev environment

1. Clone/fork this repo.
2. For best results (urls work correctly), run locally at 127.0.0.1:4000/

    ```shell
    bundle exec jekyll serve --incremental
    ```

3. Whenever you make a change to content, also change the ```modified-date``` in the yml at the top of the relevant ```.md``` file. See `Updating Page Dates` section on the [CONTRIBUTING.md](/CONTRIBUTE.md) page for more info.

## Colophon

* Jekyll front-end code inspired by [login.gov](https://www.login.gov)
