# Guided Function Creation: Simple Grade Calculator

## Step-by-Step Function Development

Let's build the grade calculator functions step by step, starting with the simplest functions and building up to more complex ones.

## Step 1: Calculate Average

### Problem Analysis
We need a function that takes a list of numbers and finds the average.

### Function Design
```python
def calculate_average(scores):
    total = 0
    count = 0
    
    for score in scores:
        total = total + score
        count = count + 1
    
    average = total / count
    return average
```

### Testing the Function
```python
# Test with our sample data
test_scores = [85, 92, 78, 96, 88]
average = calculate_average(test_scores)
print(f"Test average: {average}")  # Should output: Test average: 87.8
```

## Step 2: Convert to Letter Grade

### Problem Analysis
We need a function that takes a percentage and returns a letter grade.

### Function Design
```python
def percentage_to_letter_grade(percentage):
    if percentage >= 90:
        return "A"
    elif percentage >= 80:
        return "B"
    elif percentage >= 70:
        return "C"
    elif percentage >= 60:
        return "D"
    else:
        return "F"
```

### Testing the Function
```python
# Test with different percentages
print(percentage_to_letter_grade(95))  # Should output: A
print(percentage_to_letter_grade(87))  # Should output: B
print(percentage_to_letter_grade(75))  # Should output: C
print(percentage_to_letter_grade(65))  # Should output: D
print(percentage_to_letter_grade(45))  # Should output: F
```

## Step 3: Calculate Weighted Grade

### Problem Analysis
We need a function that combines different grades with different weights.

### Function Design
```python
def calculate_weighted_grade(test_average, homework_average, test_weight, homework_weight):
    test_contribution = test_average * (test_weight / 100)
    homework_contribution = homework_average * (homework_weight / 100)
    
    final_grade = test_contribution + homework_contribution
    return final_grade
```

### Testing the Function
```python
# Test with our sample data
test_avg = 87.8
homework_avg = 90.0
test_weight = 70
homework_weight = 30

final_grade = calculate_weighted_grade(test_avg, homework_avg, test_weight, homework_weight)
print(f"Final weighted grade: {final_grade:.2f}%")  # Should output: 88.46%
```

## Step 4: Complete Grade Calculator

### Problem Analysis
We need a function that puts everything together to calculate a complete grade.

### Function Design
```python
def calculate_student_grade(test_scores, homework_average, test_weight=70, homework_weight=30):
    # Calculate test average
    test_average = calculate_average(test_scores)
    
    # Calculate weighted final grade
    final_grade = calculate_weighted_grade(test_average, homework_average, test_weight, homework_weight)
    
    # Convert to letter grade
    letter_grade = percentage_to_letter_grade(final_grade)
    
    # Return all the results
    return test_average, final_grade, letter_grade
```

### Testing the Complete Function
```python
# Test with our sample data
test_scores = [85, 92, 78, 96, 88]
homework_average = 90.0

test_avg, final_grade, letter_grade = calculate_student_grade(test_scores, homework_average)

print("=== Student Grade Report ===")
print(f"Test scores: {test_scores}")
print(f"Test average: {test_avg:.1f}%")
print(f"Homework average: {homework_average}%")
print(f"Final grade: {final_grade:.2f}%")
print(f"Letter grade: {letter_grade}")
```

## How the Functions Work Together

### 1. Function Composition
- `calculate_student_grade` calls `calculate_average`
- `calculate_student_grade` calls `calculate_weighted_grade`
- `calculate_student_grade` calls `percentage_to_letter_grade`

### 2. Data Flow
```
test_scores → calculate_average → test_average
test_average + homework_average → calculate_weighted_grade → final_grade
final_grade → percentage_to_letter_grade → letter_grade
```

### 3. Reusability
Each function can be used independently:
```python
# Use just the average function
scores = [100, 95, 90, 85, 80]
avg = calculate_average(scores)
print(f"Average: {avg}")

# Use just the letter grade function
grade = percentage_to_letter_grade(88)
print(f"Letter grade: {grade}")
```

## Key Learning Points

### 1. Start Simple
- Begin with the easiest function (`calculate_average`)
- Build up to more complex functions
- Test each function as you build it

### 2. One Function, One Job
- `calculate_average` only calculates averages
- `percentage_to_letter_grade` only converts percentages
- `calculate_weighted_grade` only does weighted calculations

### 3. Functions Can Call Other Functions
- `calculate_student_grade` uses all the other functions
- This makes code organized and easy to understand
- Each function can be tested separately

### 4. Return Values
- Functions can return values that other functions can use
- `calculate_average` returns a number
- `percentage_to_letter_grade` returns a letter
- `calculate_student_grade` returns multiple values

## Testing Your Functions

Always test your functions with different data:

```python
# Test with different students
student1_scores = [85, 92, 78, 96, 88]
student1_homework = 90.0

student2_scores = [95, 98, 92, 96, 94]
student2_homework = 88.0

# Calculate grades for both students
test_avg1, final1, letter1 = calculate_student_grade(student1_scores, student1_homework)
test_avg2, final2, letter2 = calculate_student_grade(student2_scores, student2_homework)

print(f"Student 1: {final1:.1f}% ({letter1})")
print(f"Student 2: {final2:.1f}% ({letter2})")
```

## Next Steps

In the practice functions section, you'll create your own functions to solve similar problems. Remember to:
- Start with the simplest function first
- Test each function with real data
- Build up to more complex functions
- Make sure each function does one thing well