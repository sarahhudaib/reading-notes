# Matplotlib

## Introduction
matplotlib is probably the single most used Python package for 2D-graphics. It provides both a very quick way to visualize data from Python and publication-quality figures in many formats. We are going to explore matplotlib in interactive mode covering most common cases.

## IPython
IPython is an enhanced interactive Python shell that has lots of interesting features including named inputs and outputs, access to shell commands, improved debugging and much more. It allows interactive matplotlib sessions that have Matlab/Mathematical-like functionality.

## pyplot
pyplot provides a convenient interface to the matplotlib object-oriented plotting library. It is modeled closely after Matlab(TM). Therefore, the majority of plotting commands in pyplot have Matlab(TM) analogs with similar arguments. Important commands are explained with interactive examples.

## Simple plot
In this section, we want to draw the cosine and sine functions on the same plot. Starting from the default settings, we'll enrich the figure step by step to make it nicer.

----

# Visualizing regression models
Many datasets contain multiple quantitative variables, and the goal of an analysis is often to relate those variables to each other. We previously discussed functions that can accomplish this by showing the joint distribution of two variables. It can be very helpful, though, to use statistical models to estimate a simple relationship between two noisy sets of observations. The functions discussed in this chapter will do so through the common framework of linear regression.

``` python
import numpy as np
import seaborn as sns
import matplotlib.pyplot as plt
```


``` python
sns.set_theme(color_codes=True)
```

``` python
tips = sns.load_dataset("tips")
```

 - To obtain quantitative measures related to the fit of regression models, you should use `statsmodels`. 

 >> The goal of `seaborn`, however, is to make exploring a dataset through visualization quick and easy, as doing so is just as (if not more) important than exploring a dataset through tables of statistics.

-----

# Functions to draw linear regression models
Two main functions in seaborn are used to visualize a linear relationship as determined through regression. These functions, `regplot()` and `lmplot()` are closely related, and share much of their core functionality. 

>> It is important to understand the ways they differ, however, so that you can quickly choose the correct tool for particular job.

