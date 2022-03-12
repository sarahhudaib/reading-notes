# How to use the Random Module in Python
> When to use it?


We want the computer to pick a random number in a given range Pick a random element from a list, pick a random card from a deck, flip a coin etc. When making your password database more secure or powering a random page feature of your website.


## Random functions
>Randint

>> Usage : 
If we wanted a random integer, we can use the `randint` function `Randint` accepts two parameters: a lowest and a highest number. Generate integers between 1,5. The first value should be less than the second.

>>>  Example
``` python
import random
print random.randint(0, 5)
# This will output either 1, 2, 3, 4 or 5.
```

>Random

>> Usage : 
If you want a larger number, you can multiply it.

>>>  Example
``` python
import random
random.random() * 100
```

>Choice

>> Usage : 
Generate a random value from the sequence sequence.
usually comes with lists
>>>  Example
``` python
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```

>Shuffle

>> Usage : 
The shuffle function, shuffles the elements in list in place, so they are in a random order.
>>>  Example
``` python
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)
Output:
# print x  gives  [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
# of course your results will vary
```

>Randrange

>> Usage : 
Generate a randomly selected element from range(start, stop, step)

>>>  Example
``` python
random.randrange(start, stop[, step])
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```

----
# What is Risk Analysis in Software Testing and how to perform it?

Risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.

## Why use Risk Analysis?
In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a `test plan` has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.

----

# Test Coverage
Test coverage is a useful tool for `finding untested parts` of a codebase. Test coverage is of little use as a numeric statement of how good your tests are.

>>  One sign you are testing too much is if your tests are slowing you down. If it seems like a simple change to code causes excessively long changes to tests, that's a sign that there's a problem with the tests.