# Swirl Notes
1. swirl Installation

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

And for easy copy and paste:
  ```
  install.packages("swirl")
  library(swirl)
  swirl()
  ```
