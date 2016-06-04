# Git-References
Listing of sources of information for living and thriving in the Git Environment

## Git and Github
Git is software that runs on your local computer that lets you manage the configurations of your files using standard practices.

Github is a web service that lets you create repositories of your files for web storage and for sharing.

Whereas you do not need to use both tools, they are most often used together to provide a powerful environment for multi-user, change management.

## Git Resources

* [Pro Git book](https://git-scm.com/book/en/v2)
* [Github Help](https://help.github.com/)
* [Git Reference](gitref.org)
* [Data Science School Blog](http://www.dataschool.io/tag/git/)
* [Git Guides](https://guides.github.com/)
* [Git SCM Help](https://git-scm.com/about)
* [Introduction to Git and GitHub on YouTube](https://youtu.be/h1e8oC7g0Ps?list=PL5-da3qGB5IBLMp7LtN8Nc3Efd4hJq0kD)

## Markdown Resources

* [Markdown Tutorials](http://www.markdowntutorial.com/)
* [Markdown Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* [What is Markdown?](http://whatismarkdown.com/)

## R Programming Tips

* Add runchecks at the bottom of your R Code to verify operation of the code. Here is an example template:

  ```
  # run checks
  test <- makeCacheMatrix(matrix(data=c(1:8,9.5), nrow=3, ncol=3))
  cacheSolve(test)
  clean environment
  rm(list=ls())
  ```

## Swirl
1. Install swirl
Since swirl is an R package, you can easily install it by entering a single command from the R console:
  ```
  install.packages("swirl")
  ```
If you've installed swirl in the past make sure you have version 2.2.21 or later. You can check this with:
  ```
  packageVersion("swirl")
  ```

2. Load swirl
Every time you want to use swirl, you need to first load the package. From the R console:
  ```
  library(swirl)
  ```

3. Install the R Progroamming course
swirl offers a variety of interactive courses, but for our purposes, you want the one called R Programming. Type the following from the R prompt to install this course:
  ```
  install_from_swirl("R Programming")
  ```

4. Start swirl and complete the lessons
Type the following from the R console to start swirl:
  ```
  swirl()
  ```
  
