# reproducible project template

Flexible repo template for reproducible slides with Quarto and continuous deployment via GitHub actions

See https://robinlovelace.github.io/reproducible-project-template/slides for the content, the most important parts of which are:

- You can use this repo as a template for your own reproducible slides by clicking on 'Use this template' at https://github.com/Robinlovelace/reproducible-project-template or with the following command using the [gh cli tool](https://cli.github.com/):

```sh
gh repo create repo-name --public --description "slides for xyz conference" --template robinlovelace/reproducible-project-template
```

- Quarto is a powerful tool for creating reproducible documents
- Set-up GitHub pages with:

```sh
quarto publish gh-pages
```

- Use [GitHub actions](.github/workflows/) to automatically deploy your slides to GitHub pages

## Reproducible slide projects build with this

- Deploying cross-language in high impact projects, auto-updated and deployed with every commit, with R and Python code running and generating results shown in the slides: https://github.com/Robinlovelace/cross_language_projects