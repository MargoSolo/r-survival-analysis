---
layout: page
title: Setup
root: .
---

This lesson assumes you have R and RStudio installed on your computer. The latest version of R can be downloaded [here](https://cran.r-project.org/mirrors.html). RStudio is an application (an integrated development environment or IDE) that facilitates the use of R and offers a number of nice additional features. It can be downloaded [here](https://www.rstudio.com/products/rstudio/download/).
You will need the free Desktop version for your computer.

The lesson is based on the Game of Thrones characters' mortality dataset that was published [here](https://figshare.com/articles/Game_of_Thrones_mortality_and_survival_dataset/8259680?mc_cid=6ee60dc1ef&mc_eid=f10fe3b3f2). Please save the following two files using `File - Save As` dialog in your browser.

1. Original [characters data](https://raw.githubusercontent.com/lauzikaite/r-novice-gapminder/gh-pages/_episodes_rmd/data/character_data_S01-S08.csv)
2. Additional [data encoding](https://raw.githubusercontent.com/lauzikaite/r-novice-gapminder/gh-pages/_episodes_rmd/data/encoding.csv) table


You can install all required R packages by running the following function in R console:
```r
install_dependencies <- function () {
  dependencies <- c("dplyr",  "ggplot2", "survival", "survminer")
  installed <- installed.packages()
  to_install <- subset(dependencies, !(dependencies %in% installed[, "Package"]))
  if (length(to_install) != 0) {
    if (!requireNamespace("BiocManager", quietly = TRUE)) {
      install.packages("BiocManager")
    }
    message("Installing packages: ", to_install, " ...")
    BiocManager::install(to_install)
  } else {
    message("All dependencies are already installed.")
  }
}
install_dependencies()
```

