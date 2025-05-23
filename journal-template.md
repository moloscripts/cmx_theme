---
title: Capitalized Title Here
author:
  # see ?rjtools::rjournal_pdf_article for more information
  - name: Author One
    affiliation: Affiliation
    address:
    - line 1
    - line 2
    url: https://journal.r-project.org
    orcid: 0000-0002-9079-593X
    email:  author1@work
  - name: Author Two
    url: https://journal.r-project.org
    email: author2@work
    orcid: 0000-0002-9079-593X
    affiliation: Affiliation 1
    address:
    - line 1 affiliation 1
    - line 2 affiliation 1
    affiliation2: Affiliation 2
    address2:
    - line 1 affiliation 2
    - line 2 affiliation 2
  - name: Author Three
    url: https://journal.r-project.org
    email: author3@work
    affiliation: Affiliation
    address:
    - line 1 affiliation
    - line 2 affiliation
abstract: >
  An abstract of less than 150 words.
preamble: |
  % Any extra LaTeX you need in the preamble
  
# per R journal requirement, the bib filename should be the same as the output 
# tex file. Don't forget to rename the bib file and change this example value.
# bibliography: RJreferences.bib

output: rjtools::rjournal_pdf_article
---

## Introduction

Introductory section which may include references in parentheses
[@R], or cite a reference such as @R in the text.

## Section title in sentence case

This section may contain a figure such as Figure \ref{fig:Rlogo}.

```{r, Rlogo, echo=FALSE, fig.cap='The logo of R.', out.width='2in', fig.align='center', fig.pos='htbp'}
knitr::include_graphics('Rlogo-5.png')
```

## Another section

There will likely be several sections, perhaps including code snippets, such as:

```{r}
x <- 1:10
plot(x)
```

## Summary

This file is only a basic article template. For full details of _The R Journal_ style and information on how to prepare your article for submission, see the [Instructions for Authors](https://journal.r-project.org/share/author-guide.pdf).

### About this format and the R Journal requirements

`rticles::rjtools::rjournal_pdf_article` will help you build the correct files requirements: 

* A R file will be generated automatically using `knitr::purl` - see
https://bookdown.org/yihui/rmarkdown-cookbook/purl.html for more information.
* A tex file will be generated from this Rmd file and correctly included in
`RJwapper.tex` as expected to build `RJwrapper.pdf`.
* All figure files will be kept in the default rmarkdown `*_files` folder. This
happens because `keep_tex = TRUE` by default in `rticles::rjtools::rjournal_pdf_article`
* Only the bib filename is to modifed. An example bib file is included in the
template (`RJreferences.bib`) and you will have to name your bib file as the
tex, R, and pdf files.
