# Steps in R studio

1. Creating the package: File >> New Project >> R Package
2. In Console, \code{library(devtools) library(roxygen2)} 
3. Write your own function: File >> New File >> R Script. Write your function in this R Script. !!! Save this R Script in the **R** folder of the package. Named it by the function name.
4. Make sure you are in the working directory as the package (by default you are in this directory after creating the package). Then run these code:
   \code{document()}
   \code{setwd('..')}
   \code{install('Name of your package')}
