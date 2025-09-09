# Session 4: Practice Exercise

Create a program that determines what type of triangle you have based on three side lengths:

```python
# Triangle type checker
print("Triangle Type Checker")
print("=" * 20)

# Get side lengths
side1 = float(input("Enter length of side 1: "))
side2 = float(input("Enter length of side 2: "))
side3 = float(input("Enter length of side 3: "))

# Check if it's a valid triangle
if side1 + side2 > side3 and side2 + side3 > side1 and side1 + side3 > side2:
    print("This is a valid triangle!")
    
    # Determine triangle type
    if side1 == side2 == side3:
        print("Type: Equilateral (all sides equal)")
    elif side1 == side2 or side2 == side3 or side1 == side3:
        print("Type: Isosceles (two sides equal)")
    else:
        print("Type: Scalene (all sides different)")
else:
    print("This is not a valid triangle!")
```