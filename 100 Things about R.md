# 1. How to tell what packages you have used in R?

the list.functions.in.file() function from NCmisc (install.packages("NCmisc")) quite helpful for this:
list.functions.in.file(filename, alphabetic = TRUE)
For more info see this link: https://rdrr.io/cran/NCmisc/man/list.functions.in.file.html

a note -- you need to load the packages first, otherwise NCmisc doesn't know from what package the function comes. 

If you're using RStudio and want to use this to check the script you have open, run list.functions.in.file(rstudioapi::getSourceEditorContext()$path, alphabetic = TRUE)

Bryan Shalloway wrote a package {funspotr} that essentially does list.functions.in.file but outputs things in a dataframe format and makes a few other small changes: github.com/brshallo/funspotr 

´list.functions.in.file´ does not work if there are spanish or other rare characters in your codefiles.

# 2. What should you do if there is blank source window when opening R script?

If you open an R script into RStudio and the script appears to be blank, select File -> Reopen with encoding and ensure that the appropriate encoding is selected in the presented Choose Encoding dialog window.

