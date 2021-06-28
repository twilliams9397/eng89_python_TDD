# TDD - Test Driven Development

- We will use `unittest` and `pytest` modules
- `pip install pytest`
- `python -m unittest`
- `python -m unittest discover -v`
  
## Steps
- Firstly create the necessary Github repository for the project
- Once a Pycharm project has been started create a test file - in this case `calc_test.py` ensuring it has "test" in the name
- Within this file write to required tests and import the `unittest` and `pytest` modules, using the pip install method if necessary and import the class that will be tested
- In a new code file, write the code that is being tested - `simple_calc.py`
- After each stage is written, run the test file to ensure what has been adding is passing the tests
- When the required tests are passed, move onto the next iteration until the code is finished

![img.png](img.png)
```python
class SimpleCalc:

    def add(self, num1, num2):
        return num1 + num2

    def subtract(self, num1, num2):
        return num1 - num2

    def multiply(self, num1, num2):
        return num1 * num2

    def divide(self, num1, num2):
        return num1 / num2
```
This above is an example of a class that can be tested, and the test code for this is written below.
```python
import unittest
import pytest

from simple_calc import SimpleCalc

class CalcTest(unittest.TestCase):

    calc = SimpleCalc()

# assertions to write our test case
# we will use basic calc example to write tests first then the code

    def test_add(self):
        # naming convention is essential to have test in the name of method
        self.assertEqual(self.calc.add(3, 2), 5) # if True test will pass
        #return num1 + num2 is being tested

    def test_subtract(self):
        self.assertEqual(self.calc.subtract(3, 2), 1)

    def test_multiply(self):
        self.assertEqual(self.calc.multiply(3, 2), 6)

    def test_divide(self):
        self.assertEqual(self.calc.divide(6, 2), 3)
```
This above is the test code, where the `SimpleCalc` class is what is being tested. Each test function (e.g. `test_add`) will search in the SimpleCalc class for the function called (e.g. `add`) and check if the conditions passed are met. For example, does the `add` function return 5 if 3 and 2 are the inputs.

When the test code is run it will go through each test defined in the test class and return a pass or fail.

