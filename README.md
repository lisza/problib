# problib

<!-- [![PyPI version](https://img.shields.io/pypi/v/problib.svg)](https://pypi.python.org/pypi/problib) -->
<!-- ![Supported Python versions](https://img.shields.io/pypi/pyversions/problib.svg) -->

![GitHub license](https://img.shields.io/github/license/lisza/problib)

Small Python library to calculate and plot probabilities for Gaussian and Binomial distributions.

Note that this is a test Python package, it works fine but has some issues and solves no new problem. You can totally give it a try though!


## Installation
```
pip install problib
```

## Use
### Python
#### Gaussian
```
from problib import Gaussian
```

Create new gaussian distribution with mu=25 and sigma=2
```
gaussian = Gaussian(25, 2)
gaussian   # mean 25, standard deviation 0.5
```

Return mean and standard deviation
```
gaussian.mean    # 25.0
gaussian.stdev   # 2.0
```

Compute probability of x=15
```
gaussian.pdf(15)    # 0.19947
```

Add two Gaussian distributions together
```
gaussian_b =  Gaussian(80, 20)
gaussian + gaussian_b    # mean 105, standard deviation 20.09975
```

Plot data (requires loading data first)
```
gaussian.plot_histogram()
```

Plot normalized histogram of data and probability density function (requires loading data first)
```
gaussian.plot_histogram_pdf()
```
![gaussian_pdf_plot](https://github.com/lisza/problib/blob/master/gauss_histogram_pdf_plot.png)


#### Binomial
The Binomial distribution has the same methods as Gaussian but takes a success probability and trial size as required inputs

```
from problib import Binomial

binomial = Binomial(0.4, 20)

binomial.p    # 0.4
binomial.n    # 20
binomial.mean    # 8.0
binomial.stdev   # 2.19089


# Compute probabilty of k successful trials
binomial.pdf(5)    # 0.07465

# Plot data and probabilities
binomial.plot_bar()
binomial.plot_bar_pdf()
```
![binomial_pdf_plot](https://github.com/lisza/problib/blob/master/binomial_bar_pdf_plot.png)
