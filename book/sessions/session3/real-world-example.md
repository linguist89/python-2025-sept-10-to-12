# Session 3: Real-World ExampleWhy Input Validation Matters

Imagine you're building a simple age calculator. You ask the user for their birth year and calculate their age. This seems simple, but what if the user types something unexpected?

**The problem with bad input:**
```python
# What if the user types "abc" instead of a number?
birth_year = input("Enter your birth year: ")
age = 2024 - birth_year  # ERROR! Can't subtract text from a number
```

**Real example:** In the 1980s, a medical machine called Therac-25 was used to treat cancer patients with radiation. The machine's software didn't properly check the input from doctors. When doctors typed commands too quickly, the machine sometimes gave patients 100 times more radiation than intended, causing serious injuries. This happened because the software didn't validate the input properly.

**The programming lesson:**
This shows why it's important to:
- Always check what the user types before using it
- Give clear instructions to users
- Handle unexpected input gracefully
- Test your programs with different types of input

**Key takeaways:**
- Always validate user input before using it
- Give users clear instructions about what to type
- Handle errors gracefully with helpful messages
- Test your programs with different inputs