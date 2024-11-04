# Tutorial: Programmic Pixel Painter

## Course Structure
1) **Theory (A)**: I/O, Conditions and Loops
2) **Exercises**: Input Validation and Drawing Shapes
3) **Theory (B)**: Functions
3) **Theory (C)**: Arrays and Matricies
4) **Application**: Making Pixel Art

## Prerequisites
> You must have the local python set up, but Python Tutor is very helpful (especially is the later theory sections)

### Python Tutor Online
- https://pythontutor.com/python-compiler.html

### Local
- Python 3
	- NumPy - https://numpy.org/
	- PIL - https://pillow.readthedocs.io/en/stable/
- Code editor
## Preamble
This course assumes **no** *programming knowledge* but *basic maths*.

It also expects *you* to do some **researching online** and **documentation reading** yourself. This ability to research is expected and common-place in programming.

*The terminology may not be perfect but is aimed to be understandable.*
## Course

### Theory (A)
This is a few snippets of code to show how certain things work. The challanges are recommended to get a full understanding.

#### I/O (input/output)
> First let's get try and output something
```py
print("Hello World!") # >>> Hello World!
```
> Heres how we can do it with variables
```py
name = "MechaMango"
greeting = "Hello"
print(greeting + ", my name is " + name + "!") # >>> Hello, my name is MechaMango
```

> Now let's get input from the console
```py
name = "MechaMango"
greeting = "Hello"
print(greeting + ", my name is " + name + "!")

# ---

your_name = input("What is your name? ") # <<< type your name
print(greeting + ", " + your_name)

your_age = input("How old are you " + your_name + "? ") # <<< type your age
print("Wow " + your_age + "?!")
```
> But wait, try the lines again but type words instead of numbers...
>
> This still works even though only numbers should work. Let's fix that.

#### Conditions
```py
name: str = "MechaMango" # See: https://docs.python.org/3/library/stdtypes.html#text-sequence-type-str
greeting: str = "Hello"
print(greeting + ", my name is " + name + "!")

your_name: str = input("What is your name? ")
print(greeting + ", " + your_name)

your_age_as_string: str # Note that we don't have to have a value to start with...
your_age_as_string = input("How old are you " + your_name + "? ") # but we can give it here

if your_age_as_string.isdigit(): # https://docs.python.org/3/library/stdtypes.html#str.isdigit
	your_age_as_integer: int = int(your_age_as_string) # turn the string into a int, See: https://docs.python.org/3/library/functions.html#int
	print("Wow " + your_age + "?!")
else: # is not a digit
	print(your_age_as_string + " is not a number T-T")
```

> This now checks the correct "type" of the variable. (There are more types but let's work with str and int for now)

> The if/else is rather self explanitory, and uses a **boolean expression** (true/false) to decide which block of code to run
```py
if <condition>: # https://docs.python.org/3/tutorial/controlflow.html#if-statements
	then do this
else: 
	do this
```

#### Loops
> You might notice that our code so far runs once and then stops, but we want something that will keep running.
```py
while True:
	print("How do you stop this...")
```
> Lets use what we learnt earlier in [[#### Conditions]] to stop it
```py
counter: int = 10
while counter > 0:
	# See:
	# - https://docs.python.org/3/reference/expressions.html#value-comparisons
	# - https://docs.python.org/3/reference/compound_stmts.html#the-while-statement
	print(counter + "...")
	counter -= 1
print("Lift off!")
```
> Challenge: How would you do this with `break` instead? (See: https://docs.python.org/3/tutorial/controlflow.html#break-and-continue-statements)

> Theres a second kind of loop called a `for` loop:
```py
text: str = "YMCA"
for character in text: # See: https://docs.python.org/3/tutorial/controlflow.html#for-statements
	print(character)

count_up: int = input() # Note that we don't have to have a prompt here.
for i in range(count_up): # Makes a set of numbers from 0 (inclusive) to count_up (exclusive).
	print(i)
```

> Challenge: Can you change the code so that it counts from 0 to 20 by 2? (`0, 2, ... , 18, 20`)

### Exercises
The following are exercises to do which will help you in the [[## Application]] section.
#### Input validation
> Write a program that can test if the input is a decimal number and if it is within a range:
```py
lower_bound: float = -20 # Hint: what is a float? (find this yourself)
upper_bound: float = 999.03

# TODO: Get input
# TODO: Check range
# TODO: Print result
```

> Now make the program continue to ask for input until a valid number is given:
```py
lower_bound: int = -20
upper_bound: int = 999
while True:
	# TODO: Get input
	# TODO: Check range
	# TODO: Print result
	# TODO: How do we exit a loop?
print("Valid! :D")
```

#### Drawing Shapes
> Draw a line of `n` length, where `n` is given by input:

**Input**:
```
5
```
**Output**:
```
*****
```

> Draw a square that is `n` by `n`:

**Input**:
```
4
```
**Output**:
```
****
****
****
****
```
> Draw a square that is `n` by `m`:

**Input**:
```
4
3
```
**Output**:
```
***
***
***
***
```
> Draw a triangle that is `n` by `n`:

**Input**:
```
4
```
**Output**:
```
*
**
***
****
```

> Draw a right leaning triangle that is `n` by `n`:

**Input**:
```
4
```
**Output**:
```
   *
  **
 ***
****
```

> Draw a pyramid that is `n` by `m`:

**Input**:
```
3
5
```
**Output**:
```
*****
 ***
  *
```
**Input**:
```
2
4
```
**Output**:
```
****
 **
```

> Draw a hollow rectangle that is `n` by `m`:

**Input**:
```
5
8
```
**Output**:
```
********
*      *
*      *
*      *
********
```

> Draw a different hollow rectangle that is `n` by `m`:

**Input**:
```
5
8
```
**Output**:
```
*------*
|      |
|      |
|      |
*------*
```

### Theory (B)
A quick section on the basics of functions.
#### Anatomy of a Function
```py
def function_name(condition_1: int, condition_2, condition_x) -> bool: # https://docs.python.org/3/tutorial/controlflow.html#defining-functions
	pass # for an empty function
	return True == False # What value should this function return (give back), See: https://docs.python.org/3/reference/simple_stmts.html#return
```

#### Uses of Functions
> Functions are useful for letting us repeat code without having to type it again.
```py
# Try to comment on each line with what each line does
def print_fancy_header(header_txt: str, gap_size: int) -> None:
	header_length: int = len(header_txt) + 4
	print(txt_with_gap(header_bar(header_length), gap_size))
	print(txt_with_gap("| " + header_txt + " |", gap_size))
	print(txt_with_gap(header_bar(header_length), gap_size))

def header_bar(header_length: int) -> str:
	header_str: str = '+'
	for i in range(gap_size-2):
		header_str += '='
	return new_txt + '+'

def txt_with_gap(txt: str, gap_size: int) -> str:
	new_txt: str = ""
	for i in range(gap_size):
		new_txt += ' '
	new_txt += txt
	return new_txt

print_fancy_header("What a fancy title indeed o_o", 5)
```
### Theory (B)
A quick section on arrays and matricies.

#### Array (List)
> Arrays aka Lists (https://docs.python.org/3/tutorial/datastructures.html#more-on-lists)
```py
array_str: List[int] = ["never", "gonna", "let", "you", "down~"]
array_ints: List[int] = [404, 418, 42]

print(array_str)
i:int = 0
while i < len(array_ints):
	print(array_ints[i]) # print the ith element (starting at 0 = first)

print()

print(array_ints)
for item in array_ints:
	print(item)
```
> Challenge: What is the relationship between a `str` and a `list`

#### Matrix (Lists of Lists)
> If we have multiple lists:
```py
row_1: List[int] = [1, 2, 3]
row_2: List[int] = [4, 5, 6]
row_3: List[int] = [7, 8, 9]
```
> We can combine them to make a matrix (sometimes known as a 2D array)
```py
matrix: List[List[int]] = [[1, 2, 3],
						   [4, 5, 6],
						   [7, 8, 9]]
```
> Challenge: Make a function that can print any `n` by `m` matrix neatly.

### Application
Now we try to make a little toy program to apply our new knowledge.

There may be some stuff that you may have to search up - this is part of the fun!

#### Part 1 - Making Shapes
> Make the following functions (give it parameters as needed):
```py
"""The following functions should return a matrix, that draws the represents the following shapes."""
def make_matrix_rectangle() -> List[List[bool]]: return [[]]
def make_matrix_square() -> List[List[bool]]: return [[]] # How can you make a square from a rectangle?
def make_matrix_circle() -> List[List[bool]]: return [[]]
def make_matrix_heart() -> List[List[bool]]: return [[]] # As long as this looks good to you its fine

"""The following functions should print the shape to console, using "*" to draw."""
def print_rectangle() -> None: pass
def print_square() -> None: pass
def print_circle() -> None: pass
def print_heart() -> None: pass
```

#### Part 2 - Making Menus
> Display a menu to choose a shape, then specify the parameters based on the shape (Hint: use `match`)
```
                  +==========================+
                  |                          |
                  | Programmic Pixel Painter |
                  |                          |
                  +==========================+
What shape?
	1) Square
	2) Rectangle
	3) Circle
	4) Heart
	...
	5) Exit
```
> After typing `1` or `Square` (any combination of upper/lower case) ask for input:
```
! Square was selected !
What is the length of the Square?
```
> Then print the shape and go back to the menu (don't exit the program).
#### Part 3 - Making Pictures
Note that there is a bit of "magic" that is used here and might not be explained. Feel free to find out how they work/ what they do.
> First modify the program to also ask if you want to print the image as text or as a png:
```
! Square (5x5) !
What format?
	A) Text
	B) PNG
```
> Same as before but allow a letter instead of a number

> Now add the following code at the top of your file.
>
> Note: at this point you MUST have python set up locally on you computer to proceed (See: [[## Prerequisites]]).
```py
import numpy as np
from PIL import Image

def bool_matrix_to_color_matrix(matrix: List[List[bool]]) -> List[List[Tuple[int, int, int]]]:
	m_c: List[List[Tuple[int, int, int]]] = []
	for row in matrix:
		colour_row: List[Tuple[int, int, int]] = [] # Think: why can we reuse "colour_row"?
		for item in row:
			rgb_tuple: Tuple[int, int, int]
			if item: # Think: what type is item here
				rgb_tuple = (255, 255, 255)
			else:
				rgb_tuple = (0, 0, 0)
			colour_row.append(rgb_tuple)
		m_c.append(colour_row)
	return m_c

def matrix_to_img(name: str,  matrix: List[List[Tuple[int, int, int]]]) -> None:
	m = np.array(matrix)
	image = Image.fromarray(m, mode="RGB")
	image.save(name + ".png")
```
> Use these functions as needed and voila! an image!
## Further Activities
> - Challenge: Add padding (blank spaces) around the shape
> - Challenge: How can you modify `bool_matrix_to_color_matrix` so that you can choose the colour
> - Think: What is a "deep" and "shallow" copy (Use Python tutor)
