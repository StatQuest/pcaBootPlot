<!-- README.md is generated from README.Rmd. Please edit that file -->
PCA is very useful for creating 2-D graphs that can summarize data with many more dimensions. Such graphs are often used to determine how samples cluster and to identify outliers. Some questions that 2-D PCA plots can help anser are:

-   Are all of the "untreated" samples similar to each other?
-   Are all of the "treated" samples similar to each other (and different from the untreated)?
-   Can I identify subpopulations within a large number of samples?

One problem, however, with 2-D PCA plots is that they do not typically give any hint about the underlying variability in the data. If you were to re-do the experiment, there is no doubt that the new 2-D PCA plot would look different, but it would be helpful to know how different without having to actually re-do the work. If we knew that there would not be much difference in the new 2-D PCA plot, then we would have confidence our interpretation of the existing results.

pcaBootPlot attempts to provide a graphical sense of the underlying variability in a 2-D PCA plot by using bootstrapping. PCA is then performed on the bootstrapped samples and these results are plotted underneath the points generated from the original dataset.

Here's an example:

``` r
sample1=rnorm(n=100, mean=100, sd=10)
sample2=jitter(sample1, factor=10, amount=10)
sample3=rnorm(n=100, mean=100, sd=10)
 
data <- data.frame(ID=c(1:100), sample1, sample2, sample3)
 
pcaBootPlot(data, log2.transform = FALSE)   
```
