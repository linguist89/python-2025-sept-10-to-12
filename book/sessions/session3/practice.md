# Session 3: Practice Exercise

Create an interactive program that calculates the area and perimeter of a rectangle:

```python
# Rectangle Calculator
print("Rectangle Calculator")
print("=" * 20)

# Get dimensions from user
length = float(input("Enter the length: "))
width = float(input("Enter the width: "))

# Calculate area and perimeter
area = length * width
perimeter = 2 * (length + width)

# Display results
print(f"\nResults:")
print(f"Length: {length}")
print(f"Width: {width}")
print(f"Area: {area}")
print(f"Perimeter: {perimeter}")
```