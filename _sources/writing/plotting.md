# Plots

- [Colors](https://gist.github.com/mwaskom/b35f6ebc2d4b340b4f64a4e28e778486)
- The axes of subplots should always match.  The easiest way to do this is to use high level plotting functions such as  [seaborn's figure level](https://seaborn.pydata.org/tutorial/function_overview.html#figure-level-vs-axes-level-functions) to make subfigures. If using lower level plotting functions, use `sharex, sharey` properties of the [subplot](https://matplotlib.org/stable/api/_as_gen/matplotlib.pyplot.subplots.html) or similar. 
