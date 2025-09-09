# Session 2: Real-World Example - Why Math Operations Matter

Imagine you're building a simple calculator app. You need to add two numbers that the user enters. This seems simple, but there are important things to consider:

**The problem with different data types:**
```python
# This works fine
price = 19.99
tax = 1.60
total = price + tax
print(total)  # Output: 21.59

# But what if we mix data types incorrectly?
price = "19.99"  # This is text, not a number!
tax = 1.60
total = price + tax  # ERROR! Can't add text and numbers
```

**Real example:** In 1996, a European rocket called Ariane 5 exploded just 37 seconds after launch, costing $370 million! The problem was that the rocket's computer tried to do math with numbers that were too big for the type of variable it was using. It's like trying to fit a gallon of water into a shot glass - it overflows and causes problems.

**The programming lesson:**
This shows why it's important to:
- Use the right data type for your numbers
- Test your math operations with different values
- Make sure your variables can handle the numbers you're working with

**Key takeaways:**
- Always check that your variables can hold the values you need
- Test your math with different numbers to make sure it works
- Be careful when mixing different types of data
