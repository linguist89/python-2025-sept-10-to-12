# Session 6: Practice Exercise

Create a program with functions to calculate the area and perimeter of different shapes:

```python
# Shape calculator functions
import math

def rectangle_area(length, width):
    return length * width

def rectangle_perimeter(length, width):
    return 2 * (length + width)

def circle_area(radius):
    return math.pi * radius ** 2

def circle_perimeter(radius):
    return 2 * math.pi * radius

# Interactive shape calculator
print("Shape Calculator")
print("=" * 15)

shape = input("Enter shape (rectangle, circle): ").lower()

if shape == "rectangle":
    length = float(input("Enter length: "))
    width = float(input("Enter width: "))
    area = rectangle_area(length, width)
    perimeter = rectangle_perimeter(length, width)
    print(f"Area: {area}")
    print(f"Perimeter: {perimeter}")

elif shape == "circle":
    radius = float(input("Enter radius: "))
    area = circle_area(radius)
    perimeter = circle_perimeter(radius)
    print(f"Area: {area:.2f}")
    print(f"Perimeter: {perimeter:.2f}")

else:
    print("Invalid shape!")
```

::::{tip} Function Best Practices
- Use descriptive names for functions and parameters
- Keep functions small and focused on one task
- Use docstrings to document what your function does
- Return values instead of printing inside functions when possible
::::

::::{card} Quick Check
What will be the output of this code?
```python
def multiply(x, y):
    return x * y

result = multiply(3, 4)
print(result)
```
::::

::::{card} Quick Check
What's wrong with this function?
```python
def add_numbers(a, b):
    result = a + b
    print(result)

sum = add_numbers(5, 3)
print(sum * 2)
```
::::