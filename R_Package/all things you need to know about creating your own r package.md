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
5. If you want to rename your R package, you should change the name in ‘DESCRIPTION’ file. (if you only change the name of r project and the folder name, your package name will not be changed.)
6. Packages Dependencies: 'Imports' and 'Depends'. Both of these fields contain package dependencies which are installed when you install the package. However, the difference between them is that the packages listed in depends are attached when the package is loaded, whereas the packages listed in imports are not.

# Possible issues



# step by step

ref: https://r-pkgs.org/man.html

## Function documentation

1. add roxygen2 comments to you function file (.R files)
2. run devtools::document() to convert roxygen2 comments to .Rd files (remember to delete current 'NAMESPACE' files before running) (By default, each roxygen2 block will generate a single documentation topic, i.e. one .Rd file2 in the man/ directory.)
3. preview documentation with ?
4. rinse and repeat until the documentation looks the way you want.

roxygen2 comments start with '#'. The set of all roxygen2 comments is called a block. 

Blocks are broken up by tags.

tag: 

@tagName tagValue

The content of a tag extends from the end of the tag name to the start of the next tag 

three elements:

- introduction (text) e.g. introduction includes the *title* (“Remove duplicated strings”) and a basic *description* of what the function does.

- tag

- function 


### Tile 

What do functions have in common that doesn’t need to be repeated in every title? What is unique to that function and should be highlighted?

#### positive example:

mutate(): Create, modify, and delete columns.

summarise(): Summarise each group to fewer rows.

filter(): Subset rows using column values.

select(): Subset columns using their names and types.

arrange(): Arrange rows by column values.


features:

- succinctly description what the function does.

- describ whether it affects rows, columns, groups

- use synonyms, don't repeat the function name (for this may give user more chance to understand what is the function) 

#### negative case study:

str_detect(): Detect the presence or absence of a _pattern_ in _a string_.
str_extract(): Extract matching _patterns_ from _a string_.
str_locate(): Locate the position of _patterns_ in _a string_.
str_match(): Extract matched groups from _a string_.

- to much repetition

- repeat the function name 

### Description

purpose:  summarize the goal of the function, usually in under a paragraph. 

- it's okay for it to be a little duplicative of the rest of the documentation (if they are same thing expressed in two different ways, will be useful for readers to understand)

- keep it all up to date. Although need a little extra work, extra effort is often worth it


example:

```
#' Detect the presence/absence of a pattern
#'
#' `str_detect()` returns a logical vector `TRUE` if `pattern` is found within
#' each element of `string` or a `FALSE` if not. It's equivalent
#' `grepl(pattern, string)`.
```

when description is multiple paragraphs or a bulleted list, must specify `@description`

### Details

any additional details or explanation that you think your function needs.

if there is a lot of information, use markdown headings to break all `details` up into sections.  (or use `@section title

example:

dplyr::mutate

Notes: these headings come immediately after the description they are shown much later (after the function arguments and return value) in the rendered documentation.

### Arguments (important)

Goal: documenting how each argument affects the output of the function.

Format: @param argument_name a_description_of_its_action

Notes: 1. specify `default value` and keep consitent & update 

2. if an argument has a fixed set of possible parameters, we should list them. 
example:

`str_trim()`

```
#' @param side Side on which to remove whitespace: `"left"`, `"right"`, or
#'   `"both"` (the default).
```

2. 

`str_wrap()`

```
#' @param whitespace_only A boolean.
#'   * `TRUE` (the default): wrapping will only occur at whitespace.
#'   * `FALSE`: can break on any non-word character (e.g. `/`, `-`).
```




