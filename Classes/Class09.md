# Read: Class 09
## Dunder Methods
### What Are Dunder Methods?
In Python, special methods are a set of predefined methods you can use to enrich your classes.

### Enriching a Simple Account Class
Throughout this article I will enrich a simple Python class with various dunder methods to unlock the following language features:

- Initialization of new objects
- Object representation
- Enable iteration
- Operator overloading `(comparison)`
- Operator overloading `(addition)`
- Method invocation
- Context manager support `(with statement)`


| Dunder Methods  |  The Usage | 
|:-:|:-:|
|  `__init__` | To construct account objects from the Account class |
|  `__str__` | The “informal” or nicely printable string representation of an object. This is for the enduser. |
|  `__repr__` |  The “official” string representation of an object. This is how you would make an object of the class. The goal of __repr__ is to be unambiguous.|
|  `__len__` | Iteration |
|  `__getitem__` | Iteration |
|  `__reversed__` |  To iterate over transactions in reversed order.|
|  `__eq__` | Operator Overloading for Comparing Accounts |
|  `__lt__` |  Operator Overloading for Comparing Accounts.|
|  `__add__` |  Operator Overloading for Merging Accounts|
|  `__call__` |  Callable Python Objects|
|  `__enter__` |  Context Manager Support and the With Statement |
|  `__exit__` |  Context Manager Support and the With Statement |



----

# Basic Statistics in Python — Probability
## What is probability?
At the most basic level, probability seeks to answer the question, `“What is the chance of an event happening?”` An event is some outcome of interest. To calculate the chance of an event happening, we also need to consider all the other events that can occur. The quintessential representation of probability is the humble coin toss. In a coin toss the only events that can happen are:

- Flipping a heads
- Flipping a tails

These two events form the sample space, the set of all possible events that can happen. To calculate the probability of an event occurring, we count how many times are event of interest can occur `(say flipping heads)` and dividing it by the sample space. Thus, probability will tell us that an ideal coin will have a 1-in-2 chance of being heads or tails. By looking at the events that can occur, probability gives us a framework for making predictions about how often events will happen. However, even though it seems obvious, if we actually try to toss some coins, we’re likely to get an abnormally high or low counts of heads every once in a while. If we don’t want to make the assumption that the coin is fair, what can we do? We can gather data! We can use statistics to calculate probabilities based on observations from the real world and check how it compares to the ideal.

## Conclusion
We started with descriptive statistics and then connected them to probability. From probability, we developed a way to quantatively show if two groups come from the same distribution. In this case, we compared two wine recommendations and found that they most likely do not come from the same score distribution. In other words, one wine type is most likely better than the other one. Statistics doesn’t have to be a field relegated to just statisticians. As a data scientist, having an intuitive understanding on common statistical measures represent will give you an edge on developing your own theories and the ability to subsequently test these theories. We barely scratched the surface of inferential statistics here, but the same general ideas here will help guide your intuition in your statistical journey. Our article discussed the advantages of the normal distribution, but statisticians have also developed techniques to adjust for distributions that aren’t normal.

## [Further Reading](https://www.dataquest.io/blog/basic-statistics-in-python-probability/)