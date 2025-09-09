# Session 6: Real-World ExampleWhy Functions Matter

Imagine you're building a simple calculator app. You need to add, subtract, multiply, and divide numbers. Instead of writing the same code over and over again, you can create functions to do each operation.

**The problem with repeating code:**
```python
# Without functions - lots of repeated code
num1 = 10
num2 = 5
result1 = num1 + num2
print(f"10 + 5 = {result1}")

num3 = 20
num4 = 3
result2 = num3 + num4
print(f"20 + 3 = {result2}")

# This gets repetitive and hard to maintain!
```

**Real example:** In 2014, a security bug called "Heartbleed" affected millions of websites worldwide. The problem was in a function that was supposed to keep secure connections alive. The function didn't properly check the input it received, so hackers could trick it into giving away secret information like passwords and credit card numbers. This happened because the function wasn't designed to handle unexpected input safely.

**The programming lesson:**
This shows why it's important to:
- Always check the input your functions receive
- Make sure your functions handle unexpected situations
- Test your functions with different inputs
- Design functions that are safe and reliable

**Key takeaways:**
- Functions help you avoid repeating code
- Always validate the input your functions receive
- Test your functions thoroughly
- Make your functions clear and easy to understand