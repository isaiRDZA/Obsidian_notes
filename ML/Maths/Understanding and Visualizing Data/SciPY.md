Provides a large number of functions that are useful for different types of scientific and engineering applications. Many SciPy functions operate on [[numpy]] arrays.

[[SciPy.Stats]] calculates for many probability distributions:
- Density and mass functions
- Cumulative distribution functions
- Quantile functions 
```Python
import numpy as np
from scipy import stats
import matplotlib.pyplot as plt
import pandas as pd
import seaborn as sns
```

Evaluating the [[cumulative distribution function]] (CFD) of the standard normal distribution at zero. Since zero is th median of the standard normal distribution, the resulting cumulative probability should be 1/2.

```Python
stats.norm.cfd(0)

# The median of a standast Strudent's t distribution with 10 degrees of freedom
print(stats.t(10).ppf(0.5))

#The 97.5 percentile of a standard Student's t distribution wirh 5 degrees of freedom
print(stats.t(5).ppf(0.975))


#The probability that a stadard normal value is less than or equal to 3
orubt(stats.expon.cdf(3))


#The height of the standard normal density function at 1
print(stats.norm.pdf(1))


#The probability of getting exactly 3 heads in 10 flips of a fair coin
print(stats.binom(10, 0.5).pmf(3))


#The probability of getting 3 or fewer heads in 10 flips of a fair coin
print(stats.binom(10, 0.5).cdf(3))

```

