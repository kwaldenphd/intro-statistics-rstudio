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

4. The dataset also includes five physical measurements (see figure below).

IMAGE: data:image/jpeg;base64,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OBD68xFzB4h0bGDHw5WVQEREBERAREQEREBERAREQTe1nwWar8zVnqXr07PvuCsHmym9U1ebaz4LNV+Zqz1L16dn33BWDzZTeqagzaIiAThQ+1o/84aH/vPB6idW5PBas1jdq/XuqLfbdBRU1S3TdybWVl0q3OFK2drHsEALRl7u7JO7wGAOtBtRFEjto+8r96XP20feV+9ILVFFfbR95X70n20feV+9ILVFFfbR95X70n20feV+9ILVFFfbR95X70n20feV+9ILVFFfbR95X70n20feV+9ILVFFfbR95X70n20feV+9ILVFFfbR95X70n20feV+9ILVCor7aPvK/elwe2j7yv3pB82U425ai8zUPrJ1cLUrq/UWh9fzal13S251pulLDRT19qMhjoXRvcWOla8ZDXGQje5DhlbWgmjnhZNDIySKRocx7HbwcCMgg9YQdiJlEHlu/tTV/oH/ACSpvYn4I9L+bIfkhUl39qav9A/5JU3sT8Eel/NkPyQgrl5bx7U1f6F/+RXqWO1RK6DTVzlj4OjpJXN+EMKDBbE/BHpfzZD8kKuUjsUaW7JNLgjB9jID/wCgKuQEREBERAREQFhNYXuy2qibDqCGeemqssMUdvmq2uxjIc2NjsDiOazR5KK2pX64W+KitdtpLwG3BzhU3G32+WpdSQgd1uiNpxI7OGk8Bxd1AEKLS2orZqe2m4WSeSemEr4i6SCSIh7ThwLXtB4HhyWUWG0TJb3adporNb6y30UA6KKnq6SSne0DxteA7jzyefE5KzKAiIgIiICIiAiIgHktbQHtbbRexT3GmNUVGYPwaGvPNg8TZeY8ThyA4rZKxOsNOUOq9OVlmubSYKlm7vN76Nw4te09TmkAj4EGVC5UXsr1FW1tJV6e1I8fXFYninqyeHZLP+jqG/mvbx8hzyVogIiICIiAiIgIiICIhQYnWGoqLSum6y83Jx6ClZvbje+kdyaxvjc4kAeUrA7LNO11FS1modSNH1w314qKofi0YH2OnHkY3n5SeaxNOO2TtE7I/pNLaYmxD+BXV45v8rYuQ/OJ5rZIGEABcoiAiIgIiICx+p45JdNXOOH+kfSStbxxxLDhZBeW8e1NX+gf8koJzYs98myfTL5HOc422EkuOSe5HWq1SGxLwSaX82Q/JCr0BERAREQEREBERAREQEREE3tZ8Fmq/M1Z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

