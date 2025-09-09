# Session 5: Real-World ExampleWhy Loop Control Matters

Imagine you're building a simple program that counts from 1 to 10. You want to use a loop to do this automatically instead of writing 10 separate print statements.

**The problem with infinite loops:**
```python
# This would run forever!
count = 1
while count < 10:
    print(count)
    # Oops! Forgot to increase count
    # This loop will never end!
```

**Real example:** In 2012, a financial company called Knight Capital had a computer program that was supposed to buy and sell stocks automatically. But there was a bug in their loop - it kept buying and selling the same stock over and over again in an infinite loop! In just 45 minutes, they lost $440 million because the loop never stopped. The company almost went bankrupt because of this simple programming mistake.

**The programming lesson:**
This shows why it's important to:
- Always make sure your loops have a way to end
- Test your loops to make sure they work correctly
- Be careful when writing loops that depend on user input
- Make sure your loop conditions are correct

**Key takeaways:**
- Always ensure your loops have proper termination conditions
- Test your loops with different inputs
- Be careful with while loops - they can run forever if not set up correctly
- Use for loops when you know how many times to repeat