# Knitr and bookdown

## Reading
>https://yihui.name/knitr/

>https://bookdown.org/yihui/bookdown/

## Getting started

In RStudio:
```
install.packages("bookdown")
install.packages("knitr") #should be included in RStudio
```
You also need to install [LaTex](https://www.latex-project.org/get/). It is huge and will take a long time to download. I recommend installing [TinyTex](https://yihui.name/tinytex/), which can be installed via R.
```
install.packages('tinytex')
tinytex::install_tinytex()
```
## Introducing knitr and bookdown

The [knitr](https://cran.r-project.org/web/packages/knitr/index.html) package is an incredibly important tool for generating reproducible research. KnitR enables you to generate documents in R that are a mixture of code and text. [Bookdown](https://bookdown.org/yihui/bookdown/) is a package that focuses on generating long form articles, books & reports.

Both knitr and Bookdown use R Markdown.

An example of a fully executable published manuscript can be found here: https://github.com/caseywdunn/siphonophore_phylogeny_2017/blob/master/manuscript.rmd

### Reproducible manuscripts

Open up Reproducible_manuscript.rmd in RStudio. Press the "knit" button on the top panel to generate a pdf document that is a mix of text and figures.

## Exercise

Using Reproducible_manuscript.rmd as a template, start your own reproducible manuscript within the your new github repo. Try playing around with the settings in the code chunk, for example, try `include=FALSE` to stop some of your R code from printing within the knitted document.  
