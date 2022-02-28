# Testing and Modules
## What is Unit tests and TDD?

### Unit tests: 

     Unit tests are some pieces of code to exercise the input, the output and the behavior of your code. 

### TDD tests:
     Test-Driven Development is a strategy to think (and write!) tests first.
----

# Baby Steps:
1. what is the smaller test that we can do against a function. 

```python
  def test_should_return_female_when_the_name_is_from_female_gender():
    detector = GenderDetector()
    expected_gender = detector.run(‘Ana’)
    assert expected_gender == ‘female’
```
2. There are some details to pay attention. The first one is the test name. The tests can be considered as your alive documentation. 

3. The test file name should follow the same name of module name.
4.  It’s ideal to separate the tests folder from production code (the implementation)
5. Other thing to care about is the structure. A convention widely used is the `AAA`: **Arrange, Act and Assert**. 
>> * Arrange: you need to organize the data needed to execute that piece of code (input)
>> *  Act: here you will execute the code being tested (exercise the behaviour)
>> *  Assert: after executing the code, you will check if the result (output) is the same as you were expecting

----
 
# The Cycle: 
## The cycle is made by three steps:

* 🆘 Write a unit test and make it fail (it needs to fail because the feature isn’t there, right? If this test passes, call the Ghostwriters, really)
* ✅ Write the feature and make the test pass! (you can dance after that)
* 🔵 Refactor the code — the first version doesn’t need to be the beautiful one (don’t be shy)

---
# Takeaways
## [To remember:](https://code.likeagirl.io/in-tests-we-trust-tdd-with-python-af69f47e6932)
* The greatest advantage about TDD is to craft the software design 
first.
* Your code will be more reliable: after a change you can run your tests and be in peace.
* Beginning may be hard — and that’s fine. You just need to practice!
----

# What does the if __name__ == “__main__”: do?
Before executing code, Python interpreter reads source file and define few special variables/global variables.

>> If the python interpreter is running that module (the source file) as the main program, it sets the special `__name__` variable to have a value `“__main__”`. If this file is being imported from another module, `__name__ `will be set to the module’s name. Module’s name is available as value to `__name__` global variable. 

> A module is a file containing Python definitions and statements. The file name is the module name with the suffix .py appended. 

When we execute file as command to the python interpreter, 

     python script.py

``` python
print ("Always executed")

if __name__ == "__main__":
	print ("Executed when invoked directly")
else:
	print ("Executed when imported")

``` 

>> All of the code that is at indentation level 0 [Block 1] gets executed. Functions and classes that are defined are, well, defined, but none of their code runs.
Here, as we executed script.py directly` __name__` variable will be `__main__`. So, code in this if block[Block 2] will only run if that module is the entry point to your program. 
Thus, you can test whether your script is being run directly or being imported by something else by testing `__name__` variable.
If script is getting imported by some other module at that time `__name__ `will be module name.


``` python
if __name__ == "__main__":
	my_function()

import myscript

myscript.my_function()

```
---
## Advantages : 

* Every Python module has it’s` __name__ `defined and if this is ‘`__main__’`, it implies that the module is being run standalone by the user and we can do corresponding appropriate actions.
* If you import this script as a module in another script, the `__name__ `is set to the name of the script/module.
* Python files can act as either reusable modules, or as standalone programs.
* if `__name__ == “main”:` is used to execute some code only if the file was run directly, and not imported.

----

# Recursion

## What is Recursion? 
The process in which a function calls itself directly or indirectly is called recursion and the corresponding function is called as recursive function. Using recursive algorithm, certain problems can be solved quite easily. Examples of such problems are Towers of Hanoi (TOH), Inorder/Preorder/Postorder Tree Traversals, DFS of Graph, etc.

## A Mathematical Interpretation

Let us consider a problem that a programmer have to determine the sum of first n natural numbers, there are several ways of doing that but the simplest approach is simply add the numbers starting from 1 to n. So the function simply looks like,

    approach(1) – Simply adding one by one
    f(n) = 1 + 2 + 3 +……..+ n
but there is another mathematical approach of representing this

    approach(2) – Recursive adding 
    f(n) = 1                  n=1
    f(n) = n + f(n-1)    n>1

![alt text](./assets/recursion.jpg "recursion")

# What are the advantages of recursive programming over iterative programming? 
Recursion provides a clean and simple way to write code. Some problems are inherently recursive like tree traversals, Tower of Hanoi, etc. For such problems, it is preferred to write recursive code. We can write such codes also iteratively with the help of a stack data structure. For example refer Inorder Tree Traversal without Recursion, Iterative Tower of Hanoi.