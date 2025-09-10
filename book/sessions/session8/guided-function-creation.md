# Guided Function Creation: Personal Finance Calculator

## Step-by-Step Function Development

Let's build the personal finance calculator functions step by step, applying computational thinking to solve the real-world problem.

## Step 1: Calculate Monthly Savings

### Problem Analysis
We need a function that takes income and expenses as input and returns the savings.

### Function Design
```python
def calculate_monthly_savings(income, expenses):
    """
    Calculate monthly savings based on income and expenses.
    
    Parameters:
    income (float): Monthly income amount
    expenses (float): Monthly expenses amount
    
    Returns:
    float: Monthly savings amount
    """
    savings = income - expenses
    return savings
```

### Testing the Function
```python
# Test with our sample data
income = 4000
expenses = 3200
savings = calculate_monthly_savings(income, expenses)
print(f"Monthly savings: ${savings}")  # Should output: Monthly savings: $800
```

## Step 2: Calculate Savings Rate

### Problem Analysis
We need to calculate what percentage of income is being saved.

### Function Design
```python
def calculate_savings_rate(income, expenses):
    """
    Calculate the percentage of income that is saved each month.
    
    Parameters:
    income (float): Monthly income amount
    expenses (float): Monthly expenses amount
    
    Returns:
    float: Savings rate as a percentage
    """
    savings = income - expenses
    savings_rate = (savings / income) * 100
    return savings_rate
```

### Testing the Function
```python
# Test with our sample data
income = 4000
expenses = 3200
rate = calculate_savings_rate(income, expenses)
print(f"Savings rate: {rate:.1f}%")  # Should output: Savings rate: 20.0%
```

## Step 3: Calculate Time to Reach Goal

### Problem Analysis
We need to determine how many months it will take to reach a savings goal.

### Function Design
```python
def calculate_time_to_goal(goal_amount, monthly_savings):
    """
    Calculate how many months it will take to reach a savings goal.
    
    Parameters:
    goal_amount (float): Target savings amount
    monthly_savings (float): Amount saved per month
    
    Returns:
    float: Number of months to reach the goal
    """
    if monthly_savings <= 0:
        return float('inf')  # Can't reach goal if not saving
    
    months = goal_amount / monthly_savings
    return months
```

### Testing the Function
```python
# Test with our sample data
goal = 10000
savings = 800
months = calculate_time_to_goal(goal, savings)
print(f"Time to reach goal: {months:.1f} months")  # Should output: Time to reach goal: 12.5 months
```

## Step 4: Create a Comprehensive Calculator

### Problem Analysis
We need a function that combines all our calculations into one comprehensive report.

### Function Design
```python
def generate_finance_report(income, expenses, goal_amount):
    """
    Generate a comprehensive personal finance report.
    
    Parameters:
    income (float): Monthly income amount
    expenses (float): Monthly expenses amount
    goal_amount (float): Target savings amount
    
    Returns:
    dict: Dictionary containing all financial calculations
    """
    monthly_savings = calculate_monthly_savings(income, expenses)
    savings_rate = calculate_savings_rate(income, expenses)
    time_to_goal = calculate_time_to_goal(goal_amount, monthly_savings)
    
    report = {
        'monthly_savings': monthly_savings,
        'savings_rate': savings_rate,
        'time_to_goal': time_to_goal
    }
    
    return report
```

### Testing the Comprehensive Function
```python
# Test with our sample data
income = 4000
expenses = 3200
goal = 10000

report = generate_finance_report(income, expenses, goal)

print("=== Personal Finance Report ===")
print(f"Monthly Income: ${income:,.2f}")
print(f"Monthly Expenses: ${expenses:,.2f}")
print(f"Monthly Savings: ${report['monthly_savings']:,.2f}")
print(f"Savings Rate: {report['savings_rate']:.1f}%")
print(f"Time to Reach Goal: {report['time_to_goal']:.1f} months")
```

## Key Learning Points

### 1. Function Decomposition
- Break complex problems into smaller, manageable functions
- Each function has a single responsibility
- Functions can call other functions

### 2. Parameter Design
- Choose meaningful parameter names
- Consider what data the function needs
- Think about the function's interface

### 3. Return Value Design
- Decide what the function should return
- Consider different data types (single value vs. collection)
- Handle edge cases (like division by zero)

### 4. Documentation
- Write clear docstrings
- Explain parameters and return values
- Include examples when helpful

### 5. Testing
- Test functions with real data
- Verify expected outputs
- Consider edge cases

## Next Steps

In the practice functions section, you'll create your own functions to solve similar real-world problems. Remember to:
- Start with the problem analysis
- Design the function interface
- Write the function body
- Test with real data
- Document your work