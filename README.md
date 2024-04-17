# pru-learnr
testing webr for intro to R

Basic motivation/example taken from https://github.com/ethanwhite/datacarp-interactive/tree/main.

## Setting up webR 

quarto add coatless/quarto-webr

webr::install("dplyr")

## Usage

For each document, place the webr filter in the document's header:

filters:
  - webr
Then, place the R code for webR in a code block marked with {webr-r}

following to a pages YAML front-matter to install any packages available for web

webr:
  packages: ['dplyr', 'readr']

---
title: webR in Quarto HTML Documents
format: html
engine: knitr
filters:
  - webr
---

This is a webR-enabled code cell in a Quarto HTML document.


project: in _quarto.yml:

  resources: 
    - "webr-serviceworker.js"
    - "webr-worker.js"

```{webr-r}
fit = lm(mpg ~ am, data = mtcars)

summary(fit)
```