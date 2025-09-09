# Session 1: Real-World Example - Why Variable Names Matter

Imagine you're working on a simple calculator app. You need to store two numbers that the user enters. Look at these two examples:

**Bad variable names:**
```python
x = 10
y = 5
result = x + y
```

**Good variable names:**
```python
first_number = 10
second_number = 5
sum_result = first_number + second_number
```

**Why this matters:**
When you come back to your code later (or when someone else reads it), the second version is much clearer! You can immediately see that you're adding two numbers together. The first version could be doing anything - maybe it's coordinates, maybe it's prices, maybe it's ages. Good variable names make your code self-documenting.

**Real example:** In 1999, NASA lost a $327 million Mars spacecraft because of confusing variable names. The software used variables that weren't clear about what units they contained (metric vs imperial), leading to a navigation error that destroyed the spacecraft.

**Key takeaways:**
- Use descriptive names that explain what the variable contains
- Avoid single letters like `x`, `y`, `z` unless it's obvious what they mean
- Make your code readable for others (and yourself in the future!)
