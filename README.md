# WorldsSimplestCodeReview

[![Build Status](https://travis-ci.org/VanAndelInstitute/WorldsSimplestCodeReview.png?branch=master)](https://travis-ci.org/VanAndelInstitute/WorldsSimplestCodeReview)  [![codecov](https://codecov.io/gh/VanAndelInstitute/WorldsSimplestCodeReview/branch/master/graph/badge.svg)](https://codecov.io/gh/VanAndelInstitute/WorldsSimplestCodeReview)

## Cloning a repo into Rstudio

1. In RStudio, go to File -> New Project

2. In the New Project wizard, choose Version Control -> Git repository

3. Enter the URL of your fork and the location on your local machine where you'd
   like the repository saved.

4. Then Create Project.

5. In the top-right panel there should be a 'Git' tab where you can see what's
   changed, pull and push commits, and see the commit history.

## How to finish setting up your new package

Now that you've got a working package skeleton, there are a few steps to finish setting up all the integrations:

### 1. Git(Hub)

Go to https://github.com/VanAndelInstitute and create a new repository. Then, in the directory where this package is, create your git repository from the command line, add the files, and push it to GitHub:

    git init
    git add --all
    git commit -m "Initial commit of package skeleton"
    git remote add origin git@github.com:VanAndelInstitute/WorldsSimplestCodeReview.git
    git push -u origin master

### 2. Travis

Now you can go to [Travis](https://travis-ci.org/profile/VanAndelInstitute) and turn on continuous integration for your new package. You may need to click the "Sync account" button to get your new package to show up in the list.

If you have a codecov.io account, running your tests on Travis will trigger the code coverage job. No additional configuration is necessary

### 3. Appveyor

Go to [Appveyor's new project page](https://ci.appveyor.com/projects/new) and select your new repository from the list. Then you can go to the [badges](https://ci.appveyor.com/project/VanAndelInstitute/WorldsSimplestCodeReview/settings/badges) page, copy the markdown code it provides, and paste it up with the other badges above. (Their badge API has a random token in it, so `skeletor` can't include it in the template for you.)

### 4. Delete this "How to finish setting up your new package" section from your README.md

## Installing

<!-- If you're putting `WorldsSimplestCodeReview` on CRAN, it can be installed with

    install.packages("WorldsSimplestCodeReview") -->

The pre-release version of the package can be pulled from GitHub using the [devtools](https://github.com/hadley/devtools) package:

    # install.packages("devtools")
    devtools::install_github("VanAndelInstitute/WorldsSimplestCodeReview", build_vignettes=TRUE)

## For developers

The repository includes a Makefile to facilitate some common tasks.

### Running tests

`$ make test`. Requires the [testthat](https://github.com/hadley/testthat) package. You can also specify a specific test file or files to run by adding a "file=" argument, like `$ make test file=logging`. `test_package` will do a regular-expression pattern match within the file names. See its documentation in the `testthat` package.

### Updating documentation

`$ make doc`. Requires the [roxygen2](https://github.com/klutometis/roxygen) package.
