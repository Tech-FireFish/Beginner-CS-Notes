
# References
- [Basics of Programming](#basics-of-programming)
- [Data types](#data-types)
- [Variables](#variables)
- [Conditional Statements](#conditional-statements)
- [Iterative Statements](#iterative-statements)
- [Functions](#functions)
- [Modules and Libraries](#modules-and-libraries)
- [Code Readability](#code-readability)
- [Credits](#credits)

# Basics of programming

[GO BACK TO REFERENCES](#references)

- `#` specifies comments that are only readable inside the script.
- `print()` displays a specified object(s) to the screen.
    - > you can do mathematical expression directly using `print()`.
    - > `print(1+1)` outputs `2`.
- `""` and `''` specifies string(s).
- Numerical data DON NOT need quotation marks.

# Data types

[GO BACK TO REFERENCES](#references)

**String :**
>String data is data consisting of ordered sequence of characters, represented by double quotation(`""`) and signle quotation(`''`).
- Both `""` and `''` specifies ordered sequences of characters.
- Example(s) : `"Hello World"` is a string data.

**List :**
>Lists data is a data structure that consists of a collection of data in sequential form.
- `[]` brackets specifies a collection of data with comma to sperate each object.
- Examples(s) : 
    - `[1,2,3,4,5]`
    - `[True, False, False, True]`
    - `["approved","rejected","processing"]`

**Integer :**
> Integer data is data consisting of a number that doesn't include a decimal point.
- Example(s) : 
    - `1`
    - `-1`
    - `0`

**Float :**
> Float data is data consisting of a number that does include a decimal point. 
- `//` instructs to output the nearest whole number from a calculation.
    - `print(1/2)` outputs `0.5`.
    - `print(1//2)` outputs `0`.
- Example(s) :
    - `1.1`
    - `-1.1`
    - `0.0`

**Boolean :**
> Boolean data is data that can only be either `True` or `False`.
- Example(s) :
    - `True`
    - `False`

**Tuple :**
> Tuple data is a data structure that consists of a collection of data that cannot be changed.
- `([object], [object(s)],...)` specifies a collection of data that cannot be changed.
- Example(s) :
    - `("Python", 3.14, True)`
    - `(True, False, True)`
    - `(12, -21, 434, 43, 2, 80)`

**Dictionary :**
> Dictionary data is data that consists of one or more key-value pairs. Each key is mapped to a value.
- `{[key] : [value], ...}` specifies one or more key-value pairs.
- Example(s) :
    - `{"Python" : 3.14}`
    -   Organized format:
        ``` 
            { 
            "username": "coder123",
            "email": "user@example.com",
            "role": "admin"
            } 
        ```

**Set :**
> Set data is data that consists of an unorderd collection of unique values.
- Examples :
    - `{1,2,3}`
    - `{"confidentiality", "integrity", "availability"}`

# Variables

[GO BACK TO REFERENCES](#references)
**Variable :**
> A container that stores data. \
> It can not be `True`, `False`, or `if`.
- `[object] = [value]` assigns a specific value to an object.
- `type()` procedure displays the data type of the input data.
- Example(s) : 
    - `username = "Tech-FireFish"`
    - `username_list = ["name1", "name2",...]`
    - `username_active = True`
    - `username_id = 1234`


# Conditional statements

[GO BACK TO REFERENCES](#references)

**Conditional statments :**
> A statement that evaluates code to determine if it meets a specified set of conditions.

Model:

```
if [condition(s)]:
    [action(s)]
elif [condition(s)]:
    [action(s)]
else:
    [action(s)]
```
- `if`: starts the conditional statement.
- `[condition(s)]` : instructs conditions to verify.
- `[action(s)]` : specifies execution(s) once the condition meets.
- `elif` :(optional) instructs another condition statement if the first conditional statement is not true.
- `else` : (optional) instrcuts action(s) to execute if one or more conditional statements fail.
- Examples: 
```
if status == 200:
    print("Successful")
elif status == 400:
    print("Fail")
else:
    print("Undefined errer")
```
**Operators :**
> Operators used to compare numerical or string values:
- `>` : Greater than.
- `<` : Less than.
- `>=` : Greater than or equal to.
- `<=` : Less than or equal to.
- `==` : Equal to.
- `!=` : Not equal to.

**Logical operators :**
> Logical operators for multiple conditions:
- `and` operator requires both conditions on either side of the operator to evaluate to True.
- `or` operator requires one condition on either side of the operator to evaluate to True.
- `not` operator negates a given condition so that it evaluates to `False` if the condition is `True` and to `True` if it is `False`.
- `in` operator checks whether a given value is an element of a sequence.
- `not in` operator checks whether a given value is NOT an element of a sequence.


# Iterative statements

[GO BACK TO REFERENCES](#references)

**For loop :**
> Perform tasks that involve iterating through lists a predetermined number of times. 
- `for [loop_variable] [operator] [object(s)_list]: [action(s)]` specifies times of iteration in a specific sequence.

**While loop :**
> Perform tasks based on certain conditions evaluating to True.
- `while [condition(s)] : [action(s)]` instructs the program to repeatively execute action(s) until the condition(s) have evaluate to True.

*Different forms:*
- `while [loop_variable] [operator] [numerical_value] : [action(s)]` specifies an iteration that will continue and repeat until the numberical_value has reached.

**Good to know :**
- `range([start_value](optional),[end_value],[value_of_change](optional))` specifies a sequence that will increase/decrease by a specific numerical value and only stops when the one value before the end_value is reached.
    - `range([end_value])` specifies a sequence starts with zero(0) with value increase by one each time, ends by one value before the end_value.
- `break` keyword instructs to break out of a loop.
- `continue` keyword instructs to skip a loop iteration and continue with the next one.
- `Ctrl + Z` to break infinite loops.


# Functions
> A section of code that can be reused in a program.

**Define a Func :**
- `def [func_name](): [action(s)]` defines a function with a specific name and blocks of code to execute.
- Example(s):
    - `def print_hello_world(): print("Hello World")`

**Func call :**
- `[func_name]()` instruct the system to execute actions inside this function.
- Examples:
    - `print_hello_world()`

**Parameter :**
> An object that is included in a function defition for use in that function.
- `def [func_name]([parameter]): [func_body]` specifies a function with input object required.
- Example(s) : 
    - `def greet_to_someone(name): print("Hello " + name)`

**Argument**
> The data brought into a function when it is called.
- Example(s) : 
    - `greet_to_someone("Tech_FireFish")`, "Tech_FireFish" is the argument

**Return statement :**
> A statement that executes inside a function and sends infomraiton back to the function call.
- `return` keyword returns information from a function.

**Global variables :**
> Global variables are variables accessible throughout the program.

**Local variables :**
> Local variables are parameters and variables assigned within a function that aren't usable outside of a function.


# Modules and libraries 

- `print([object(s)])` outputs a specified object to the screen. 
- `type([object(s)])` returns the data type of its argument.
- `max([object(s)])` returns the largest numeric input passed into it
- `min([object(s)])` returns the smallest numeric input passed into it
- `sorted([object(s)])` sorts the components of a list. 

**Liberary :**
> A collection of modules that provide code user can access in their programs.

**Module :**
> A file that contains addititional functions, variables, classes and any kind of runnable code.
- `import [module_name]` searches for a module or library in a system and adds it to the local Python environment.
- `from [library_name] import [module_name] imports a specific function from the Python Standard Library.

**Install external library :**
- `%pip install [library_name]` installs the inputed library(s).

# Code readability

- `#` starts a line that contains a Python comment

- `"""` documentation strings starts and ends a multi-line string that is often used as a Python comment; multi-line comments are used when you need more than 79 characters in a single comment. 

- [PEP 8 – Style Guide for Python Code](https://peps.python.org/pep-0008/)

# Credits

[GO BACK TO REFERENCES](#references)

- Tech-FireFish, contributor, [Profile_URL](https://github.com/Tech-FireFish)
- Google Cybersecurity Professional Certificate instructed by Google Career Certificates on Coursera platform, May 4, 2023, [URL](https://www.coursera.org/professional-certificates/google-cybersecurity).
