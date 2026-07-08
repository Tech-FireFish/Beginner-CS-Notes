
# References
- [Basics of Programming](#basics-of-programming)
- [Data types](#data-types)
- [Variables](#variables)
- [Conditional Statements](#conditional-statements)
- [Iterative Statements](#iterative-statements)
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

> Operators used to compare numerical or string values:
- `>` : Greater than.
- `<` : Less than.
- `>=` : Greater than or equal to.
- `<=` : Less than or equal to.
- `==` : Equal to.
- `!=` : Not equal to.

> Logical operators for multiple conditions:
- `and` operator requires both conditions on either side of the operator to evaluate to True.
- `or` operator requires one condition on either side of the operator to evaluate to True.
- `not` operator negates a given condition so that it evaluates to `False` if the condition is `True` and to `True` if it is `False`.
- `in` operator checks whether a given value is an element of a sequence.
- `not in` operator checks whether a given value is NOT an element of a sequence.


# Iterative statements

[GO BACK TO REFERENCES](#references)

> Code that repeatedly executes a set of instructions.
- `for [loop_variable] [operator] [object(s)_list]: [action(s)]` specifies times of iteration in a specific sequence.
- `range([start_value](optional),[end_value],[value_of_change](optional))` specifies a sequence that will increase/decrease by a specific numerical value and only stops when the one value before the end_value is reached.
    - `range([end_value])` specifies a sequence starts with zero(0) with value increase by one each time, ends by one value before the end_value.
- `while [condition(s)] : [action(s)]` instructs the program to repeatively execute action(s) until the condition(s) have evaluate to True.
    - `while [loop_variable] [operator] [numerical_value] : [action(s)]` specifies an iteration that will continue and repeat until the numberical_value has reached.
- `break` keyword instructs to break out of a loop.
- `continue` keyword instructs to skip a loop iteration and continue with the next one.
- `Ctrl + Z` to break infinite loops.

# Credits

[GO BACK TO REFERENCES](#references)

- Tech-FireFish, contributor, [Profile_URL](https://github.com/Tech-FireFish)
- Google Cybersecurity Professional Certificate instructed by Google Career Certificates on Coursera platform, May 4, 2023, [URL](https://www.coursera.org/professional-certificates/google-cybersecurity).
