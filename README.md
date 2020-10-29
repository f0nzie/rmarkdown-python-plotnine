# A Python `plotnine` book built with Rmarkdown

## Motivation

The goal of `plotnine-book` is to show a practical application of a book where all the computations and plots have been generated using **Python**. **Rmarkdown** is the format being used in the writing of each of the chapters instead of the classic **Jupyter** notebooks.

**Rmarkdown** opens infinite creation possibilities to scientists, engineers and analysts for the production of documents, reports, analysis, tutorials, manuals, papers, thesis, presentations, slides, or even websites or blogs. The advantages of writing your documents in Rmarkdown is that your document and analysis are:

-   Documents are totally reproducible and able to be put under version control such as Git, GitHub, or other cloud repositories

-   Documents are fully written in text which can be opened at any time with a simple text editor

-   Multiple coding languages can be embedded in a single document

-   Python and R can mutually interchange values of objects or variables in the same Rmarkdown document

-   Rmarkdown documents can be built to be HTML books, Git books, PDF books, and few other output formats

## A book on Python computed with Python 

This book uses **Python** and Python packages for the generation of tables, plots and figures. R is only used to do the book compilation via the package `bookdown`. In this particular book, we used the following Python packages:

-   plotnine

-   matplotlib

-   numpy

-   pandas

-   warnings

## Pre-requisites

1.  A Python virtual environment with GNU Python and `virtualenv`. We will not use `conda` this time.
2.  An installation of R with the following packages installed: `bookdown`, `reticulate`
3.  A computer able to run GNU `make` to process the `Makefile` for this book

## Build the book

### Update current R installation with a recipe

Since we will be using some R packages to build the Rmarkdown book, among them `knitr`, first, we need to update our R installation. There is a rule in Makefile that takes care of that. Run it from the terminal with:

```
make renv/library
```

This will update the packages according to the recipe in the file `renv.lock`.

### Build the gitbook

Once R gets updated, we are ready to build the book. From a terminal, run:

    make gitbook

If the book builds successfully, it should open your browser with the main page of the book. This is all handled by `make` and the commands in `Makefile`.



## Optional after building the book

If you make changes to the Rmarkdown documents, you may want to tidy up or totally clean from auxiliary and files that were generated during the knitting process. The are two rules in the `Makefile`: `tidy` and `clean `.

### Tidy up the folder

This deletes the auxiliary files that were created during the book building process.

    make tidy

### Clean up the folder

Does `make tidy` plus deletes the publication folder, to start over fresh.

    make clean
