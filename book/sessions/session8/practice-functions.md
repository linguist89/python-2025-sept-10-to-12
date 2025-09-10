# Practice Functions: Real-World Problem Solving

## Instructions

For each problem below, create a function that solves the real-world scenario. Follow these steps:

1. **Analyze the problem** - What inputs do you need? What should the function return?
2. **Design the function** - Choose a good name and parameter list
3. **Write the function** - Include a docstring and proper logic
4. **Test your function** - Use the provided test data to verify it works

## Problem 1: Temperature Converter

### Scenario
You're building a weather application that needs to convert temperatures between Celsius and Fahrenheit for users in different countries.

### Requirements
Create a function that converts Celsius to Fahrenheit using the formula: `F = (C × 9/5) + 32`

### Test Data
- 0°C = 32°F
- 25°C = 77°F
- 100°C = 212°F

### Your Function
```python
def celsius_to_fahrenheit(celsius):
    """
    Convert temperature from Celsius to Fahrenheit.
    
    Parameters:
    celsius (float): Temperature in Celsius
    
    Returns:
    float: Temperature in Fahrenheit
    """
    # Your code here
    pass
```

## Problem 2: BMI Calculator

### Scenario
A fitness app needs to calculate Body Mass Index (BMI) to help users track their health goals.

### Requirements
Create a function that calculates BMI using the formula: `BMI = weight(kg) / height(m)²`

### Test Data
- Weight: 70 kg, Height: 1.75 m → BMI: 22.86
- Weight: 60 kg, Height: 1.65 m → BMI: 22.04

### Your Function
```python
def calculate_bmi(weight, height):
    """
    Calculate Body Mass Index (BMI).
    
    Parameters:
    weight (float): Weight in kilograms
    height (float): Height in meters
    
    Returns:
    float: BMI value
    """
    # Your code here
    pass
```

## Problem 3: Grade Calculator

### Scenario
A teacher needs to calculate final grades based on multiple assignment scores.

### Requirements
Create a function that takes a list of scores and returns the average grade.

### Test Data
- Scores: [85, 92, 78, 96, 88] → Average: 87.8
- Scores: [90, 95, 100, 85] → Average: 92.5

### Your Function
```python
def calculate_average_grade(scores):
    """
    Calculate the average of a list of grades.
    
    Parameters:
    scores (list): List of numerical scores
    
    Returns:
    float: Average of all scores
    """
    # Your code here
    pass
```

## Problem 4: Password Strength Checker

### Scenario
A website needs to validate password strength to ensure user security.

### Requirements
Create a function that checks if a password is strong enough:
- At least 8 characters long
- Contains at least one uppercase letter
- Contains at least one lowercase letter
- Contains at least one digit

### Test Data
- "Password123" → True (strong)
- "password" → False (no uppercase, no digit)
- "PASS123" → False (no lowercase)
- "Pass1" → False (too short)

### Your Function
```python
def is_strong_password(password):
    """
    Check if a password meets strength requirements.
    
    Parameters:
    password (str): Password to check
    
    Returns:
    bool: True if password is strong, False otherwise
    """
    # Your code here
    pass
```

## Problem 5: Shopping Cart Calculator

### Scenario
An e-commerce site needs to calculate the total cost of items in a shopping cart, including tax.

### Requirements
Create a function that calculates the total cost including tax:
- Take a list of item prices
- Add them together
- Apply a tax rate (e.g., 8.5%)
- Return the total cost

### Test Data
- Prices: [10.99, 5.50, 3.25], Tax: 8.5% → Total: $21.48
- Prices: [25.00, 15.00], Tax: 10% → Total: $44.00

### Your Function
```python
def calculate_total_cost(item_prices, tax_rate):
    """
    Calculate total cost of items including tax.
    
    Parameters:
    item_prices (list): List of item prices
    tax_rate (float): Tax rate as a percentage (e.g., 8.5 for 8.5%)
    
    Returns:
    float: Total cost including tax
    """
    # Your code here
    pass
```

## Problem 6: Text Analyzer

### Scenario
A content management system needs to analyze text for basic statistics.

### Requirements
Create a function that analyzes text and returns:
- Word count
- Character count (excluding spaces)
- Average word length

### Test Data
- Text: "Hello world Python programming" → Words: 4, Characters: 25, Avg Length: 6.25

### Your Function
```python
def analyze_text(text):
    """
    Analyze text and return basic statistics.
    
    Parameters:
    text (str): Text to analyze
    
    Returns:
    dict: Dictionary with 'words', 'characters', 'avg_length'
    """
    # Your code here
    pass
```

## Testing Your Functions

After writing each function, test it with the provided data:

```python
# Example testing
result = celsius_to_fahrenheit(25)
print(f"25°C = {result}°F")  # Should output: 25°C = 77.0°F
```

## Reflection Questions

After completing all functions, consider:

1. **Which function was most challenging to write? Why?**
2. **How did you handle edge cases (like empty lists or invalid input)?**
3. **What naming conventions did you use for your functions?**
4. **How could you make your functions more robust?**

## Next Steps

Once you've completed these practice functions, you'll be ready to move on to more complex function concepts in the next session, including:
- Functions with multiple parameters
- Functions that return multiple values
- Functions that work with different data types
- Error handling in functions