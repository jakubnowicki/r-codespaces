# GitHub Codespaces configuration for R

This repository contains a basic configuration that allows working with R in [GitHub Codespaces](https://github.com/features/codespaces).
It includes [`R`](https://marketplace.visualstudio.com/items?itemName=Ikuyadeu.r) and
[`R LSP Client`](https://marketplace.visualstudio.com/items?itemName=REditorSupport.r-lsp) VSCode extensions.
It comes with `renv` setup which includes `languageserver` package required to enable the latter extension.
To install it, open R in Codespaces console and type `renv::restore()`.

## Adjusting configuration to your needs

### Different R version

This configuration is based on `rocker/r-ver:4.0.0-ubuntu18.04` Docker image with installed dependencies required by `languageserver` package.
You can change that and replace the current image with the one of your choice in `.devcontainer/Dockerfile`.
Check [rocker repositories](https://hub.docker.com/u/rocker) for available options.

Remember that current Dockerfile is suited for images based on Ubuntu.

### Installing R packages

I strongly recommend using [`renv`](https://rstudio.github.io/renv/index.html) when it comes to setting your working environment in R.
This configuration comes with initalized workspace but you can easily create your own one. Just remember that `languageserver` is required for `R LSP Client` extension to work (it needs to be installed, adding to `renv.lock` file is optional).

### Adding VSCode extensions

Besides extensions for R, this configuration includes a few additional ones that can be helpful in development.
You can add additional extensions in `.devcontainer/devcontainer.json` file in "extensions" section.
