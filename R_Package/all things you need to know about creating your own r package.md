# Steps in R studio

1. Creating the package: File >> New Project >> R Package

2. In Console, run these code:   ```library(devtools) library(roxygen2)}``` 
 
3. Write your own function: File >> New File >> R Script. Write your function in this R Script. !!! Save this R Script in the **R** folder of the package. Named it by the function name.
 
4. Make sure you are in the working directory as the package (by default you are in this directory after creating the package). Then run these code:
   ```
   document()
   setwd('..')
   install('Name of your package')
   ```
5. check whether you have installed the package successfully.

6. Add documentation


# Notes

1. everytime when you run `document()`, delete the old 'NAMESPACE` file.
2. if you restart R, how do you test whether your package works or not?

```
library(devtools)
library(roxygen2')
setwd('out of your package directory')
install('Package name')
library('Package name')   
function_name
?function_name
```

3. when you have internal error, restart R session may solve it
4. when you `@import ggplot2` but the function suggests that 'did not find ggplot`, this is maybe because you did not create `NAMESPACE` file rightly.  
