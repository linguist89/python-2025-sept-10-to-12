# Session 1: Guided Questions - Step by Step

Work through these questions step by step. Each question will guide you through the thinking process and show you exactly how to solve it.

### Question 1: Creating Your First Variable
**Problem:** Create a variable called `my_name` and assign your name to it, then print it.

**Step 1:** Think about what you need
- You need a variable name: `my_name`
- You need to assign a value (your name in quotes)
- You need to print the variable

**Step 2:** Write the code
```python
my_name = "Your Name Here"
print(my_name)
```

**Step 3:** Test it
Run the code and make sure it prints your name correctly.

### Question 2: Different Data Types
**Problem:** Create variables for your age (as a number), your height (as a decimal), and whether you like Python (as True/False).

**Step 1:** Identify the data types
- Age: integer (whole number)
- Height: float (decimal number)  
- Like Python: boolean (True or False)

**Step 2:** Write the code
```python
age = 25
height = 5.6
likes_python = True
```

**Step 3:** Print them to verify
```python
print("Age:", age)
print("Height:", height)
print("Likes Python:", likes_python)
```

### Question 3: Variable Naming Practice
**Problem:** Create variables for a person's first name, last name, and email address using good naming conventions.

**Step 1:** Think about good names
- Use snake_case (lowercase with underscores)
- Be descriptive
- Don't use Python keywords

**Step 2:** Write the code
```python
first_name = "John"
last_name = "Doe"
email_address = "john.doe@email.com"
```

**Step 3:** Verify the names are clear
These names clearly show what each variable contains.

### Question 4: String Variables
**Problem:** Create variables for a book title, author, and publication year, then create a sentence using them.

**Step 1:** Create the variables
```python
book_title = "Python Programming"
author = "Jane Smith"
publication_year = 2024
```

**Step 2:** Create a sentence
```python
sentence = f"The book '{book_title}' by {author} was published in {publication_year}."
print(sentence)
```

### Question 5: Number Variables
**Problem:** Create variables for a rectangle's length and width, then calculate and print the area.

**Step 1:** Create the variables
```python
length = 10
width = 5
```

**Step 2:** Calculate the area
```python
area = length * width
print(f"The area is {area} square units")
```

### Question 6: Boolean Variables
**Problem:** Create variables to track whether someone has a driver's license and is over 18.

**Step 1:** Create the variables
```python
has_license = True
is_over_18 = True
```

**Step 2:** Use them in a message
```python
if has_license and is_over_18:
    print("This person can drive!")
```

### Question 7: Variable Reassignment
**Problem:** Create a variable called `count` with value 5, then change it to 10, then to 15.

**Step 1:** Create the initial variable
```python
count = 5
print("Initial count:", count)
```

**Step 2:** Change the value
```python
count = 10
print("After first change:", count)
```

**Step 3:** Change it again
```python
count = 15
print("After second change:", count)
```

### Question 8: Multiple Variables in One Statement
**Problem:** Create three variables in one line: x = 1, y = 2, z = 3.

**Step 1:** Use multiple assignment
```python
x, y, z = 1, 2, 3
```

**Step 2:** Verify the values
```python
print("x =", x)
print("y =", y)
print("z =", z)
```

### Question 9: String Concatenation with Variables
**Problem:** Create variables for first name and last name, then combine them into a full name.

**Step 1:** Create the variables
```python
first_name = "Alice"
last_name = "Johnson"
```

**Step 2:** Combine them
```python
full_name = first_name + " " + last_name
print("Full name:", full_name)
```

### Question 10: Variable Types Check
**Problem:** Create variables of different types and use the `type()` function to check their types.

**Step 1:** Create different types
```python
name = "Python"
age = 30
height = 5.9
is_programming = True
```

**Step 2:** Check their types
```python
print("Type of name:", type(name))
print("Type of age:", type(age))
print("Type of height:", type(height))
print("Type of is_programming:", type(is_programming))
```

### Question 11: Variable Scope Practice
**Problem:** Create a variable outside a code block and print it.

**Step 1:** Create the variable
```python
course_name = "Python Programming"
```

**Step 2:** Print it
```python
print("Course:", course_name)
```

### Question 12: Constants (Uppercase Variables)
**Problem:** Create a constant for the value of pi and use it to calculate the area of a circle.

**Step 1:** Create the constant (uppercase name)
```python
PI = 3.14159
radius = 5
```

**Step 2:** Calculate the area
```python
area = PI * radius * radius
print(f"Area of circle: {area}")
```

### Question 13: Variable Naming Rules
**Problem:** Create variables that follow Python naming rules and some that don't (commented out).

**Step 1:** Good variable names
```python
user_name = "Alice"
user_age = 25
is_logged_in = True
```

**Step 2:** Bad variable names (commented out)
```python
# 2name = "Alice"     # Can't start with number
# user-name = "Alice"  # Can't use hyphens
# print = "Hello"      # Can't use Python keywords
```

### Question 14: Variable Initialization
**Problem:** Create variables and initialize them with default values.

**Step 1:** Initialize with defaults
```python
score = 0
player_name = ""
game_over = False
```

**Step 2:** Update the values
```python
score = 100
player_name = "Player1"
game_over = True
```

### Question 15: Variable Swapping
**Problem:** Create two variables and swap their values.

**Step 1:** Create the variables
```python
a = 10
b = 20
print("Before swap: a =", a, "b =", b)
```

**Step 2:** Swap the values
```python
a, b = b, a
print("After swap: a =", a, "b =", b)
```

### Question 16: Variable Expressions
**Problem:** Create variables and use them in mathematical expressions.

**Step 1:** Create the variables
```python
x = 5
y = 3
```

**Step 2:** Use in expressions
```python
sum_result = x + y
difference = x - y
product = x * y
quotient = x / y
print(f"Sum: {sum_result}, Difference: {difference}, Product: {product}, Quotient: {quotient}")
```

### Question 17: String Variables with Special Characters
**Problem:** Create a variable with a string that contains quotes and special characters.

**Step 1:** Use escape characters
```python
message = "She said, \"Hello, World!\""
print(message)
```

**Step 2:** Use triple quotes for multi-line
```python
multi_line = """This is a
multi-line string
with multiple lines"""
print(multi_line)
```

### Question 18: Variable Memory Practice
**Problem:** Create variables and understand how Python stores them in memory.

**Step 1:** Create variables
```python
original = "Python"
copy = original
```

**Step 2:** Check if they're the same
```python
print("Original:", original)
print("Copy:", copy)
print("Are they the same?", original is copy)
```

### Question 19: Variable Types Conversion
**Problem:** Create a variable and convert it to different types.

**Step 1:** Create a number
```python
number = 42
```

**Step 2:** Convert to different types
```python
string_version = str(number)
float_version = float(number)
print("Original:", number, type(number))
print("String:", string_version, type(string_version))
print("Float:", float_version, type(float_version))
```

### Question 20: Variable Best Practices
**Problem:** Create a complete example showing good variable practices.

**Step 1:** Use descriptive names
```python
student_name = "Alice Johnson"
student_age = 20
is_enrolled = True
gpa = 3.8
```

**Step 2:** Use them meaningfully
```python
print(f"Student: {student_name}")
print(f"Age: {student_age}")
print(f"Enrolled: {is_enrolled}")
print(f"GPA: {gpa}")
```
