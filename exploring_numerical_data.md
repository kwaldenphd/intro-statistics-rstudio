# Option 1: Exploring Numerical Data

## Acknowledgements

This lab procedure is adapted from [Dr. Yibi Huang’s](http://www.stat.uchicago.edu/~yibi/) (Statistics, University of Chicago) Fall 2017 [Statistical Methods and Applications course](http://www.stat.uchicago.edu/~yibi/teaching/stat220/17aut/) ([STAT 220 labs](http://www.stat.uchicago.edu/~yibi/s220/labs/)).

Additional documentation, including definitions and additional resources, for this lab come from Danielle Navarro, [*Learning Statistics With R: A Tutorial for Psychology Students and Other Beginners*](https://learningstatisticswithr.com/book/) (2019).

**Statistical concepts covered:** mean, median, standard deviation, variance, quartiles, interquartile range, min, max

**Visualization types covered:** histograms, boxplots, scatterplots

**Lab notebook deliverables:**
- RScript file that includes your process/progress working through the lab steps.
- Brief summary (or summary comments throughout the lab) that describe challenges you faced and key takeaways.

**Resources:**

Danielle Navarro, [*Learning Statistics With R: A Tutorial for Psychology Students and Other Beginners*](https://learningstatisticswithr.com/book/) (2019).

Chapter 5 [Descriptive Statistics](https://learningstatisticswithr.com/book/descriptives.html)
- 5.1 [Measures of Central Tendency](https://learningstatisticswithr.com/book/descriptives.html#centraltendency)
  * 5.1.1 [The mean](https://learningstatisticswithr.com/book/descriptives.html#mean)
  * 5.1.3 [The median](https://learningstatisticswithr.com/book/descriptives.html#median)
- 5.2 [Measures of variability](https://learningstatisticswithr.com/book/descriptives.html#var)
  * 5.2.1 [Range](https://learningstatisticswithr.com/book/descriptives.html#range)
  * 5.2.2 [Interquartile range](https://learningstatisticswithr.com/book/descriptives.html#interquartile-range)
  * 5.2.4 [Variance](https://learningstatisticswithr.com/book/descriptives.html#variance)
  * 5.2.5 [Standard deviation](https://learningstatisticswithr.com/book/descriptives.html#sd)

Chapter 6 [Drawing graphs](https://learningstatisticswithr.com/book/graphics.html)
- 6.2 [An introduction to plotting](https://learningstatisticswithr.com/book/graphics.html#introplotting)
- 6.3.1 [Visual style of your histogram](https://learningstatisticswithr.com/book/graphics.html#visual-style-of-your-histogram)
- 6.5.1 [Visual style of your boxplot](https://learningstatisticswithr.com/book/graphics.html#visual-style-of-your-boxplot)
- 6.6 [Scatterplots](https://learningstatisticswithr.com/book/graphics.html#scatterplots)

# The Diamonds Dataset

1. The `diamonds` dataset is part of the `mosaic` library.

2. We can access the dataset by loading the `mosaic` library and usign the `data` function.

```R
# install mosaic package
install.packages("mosaic")

# load mosaic package
library(mosaic)

# access diamonds dataset
data(diamonds)
```

3. The `diamonds` dataset includes the following variables.
- `price`: price in U.S. dollars
- `carat`: weight of the diamond
- `cut`: quality of the cut (`Fair`, `Good`, `Very Good`, `Premium`, `Ideal`)
- `color`: diamond color, from `J` (worst) to `D` (best)
- `clarity`: a measurement of how clear the diamond is from `I1` (worst), `SI1`, `SI2`, `VS1`, `VS2`, `VVS1`, `VVS2` to `IF` (best)

4. The dataset also includes five physical measurements (see figure below): `depth`, `table`, `x`, `y`, and `z`

IMAGE

5. We can use `dim()` to get the dimensions of the diamond dataset, 53940 rows and 10 variables.
```R
dim(diamonds)
```

6. We can use `str()` to view the names of the variables.
```R
str(diamonds)
```

7. 
