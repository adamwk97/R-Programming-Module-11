Module 11 Assignment
================

"The code below contains a 'deliberate' bug! Find the bug and fix it.

Report on your blog the success or failure in your debugging procedure."

Original code:

``` r
#tukey_multiple <- function(x) {
#   outliers <- array(TRUE,dim=dim(x))
#   for (j in 1:ncol(x))
#    {
#    outliers[,j] <- outliers[,j] && tukey.outlier(x[,j])
#    }
#outlier.vec <- vector(length=nrow(x))
#    for (i in 1:nrow(x))
#    { outlier.vec[i] <- all(outliers[i,]) } return(outlier.vec) }
```

Fixed code:

``` r
tukey_multiple <- function(x) {
   outliers <- array(TRUE,dim=dim(x))
   for (j in 1:ncol(x))
    {
    outliers[,j] <- outliers[,j] && tukey.outliers(x[,j])
    }
outlier.vec <- vector(length=nrow(x))
    for (i in 1:nrow(x))
    { 
      outlier.vec[i] <- all(outliers[i,]) 
      } 
return(outlier.vec) 
}
```

I believe what was wrong with this code was the formatting. Once I properly indented and separated each line/section of the function it ran without a problem. It looks like the function is now supposed to detect outliers in an array/vector properly.

Once I try to run the function in my own vector, however, I receive an error detailing "could not find function "tukey.outliers"". I assume this is because tukey.outliers is a separate function that is not defined nor provided here but if that function were to be provided I am sure this code would run correctly.
