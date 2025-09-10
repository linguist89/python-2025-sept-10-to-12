# Practice Functions: Building Flexible Functions with *args and **kwargs

## Instructions

For each problem below, create a function that uses `*args` and/or `**kwargs` to solve the real-world scenario. Follow these steps:

1. **Analyze the problem** - What inputs do you need? How many arguments might you receive?
2. **Design the function** - Choose appropriate use of `*args` and `**kwargs`
3. **Write the function** - Include docstrings and proper logic
4. **Test your function** - Use the provided test data to verify it works

## Problem 1: Flexible Calculator

### Scenario
You're building a calculator app that needs to handle different mathematical operations with any number of numbers.

### Requirements
Create a function that can perform basic operations (add, subtract, multiply, divide) on any number of values.

### Test Data
- Add: 1, 2, 3, 4, 5 → Result: 15
- Multiply: 2, 3, 4 → Result: 24
- Subtract: 100, 10, 5 → Result: 85 (100 - 10 - 5)
- Divide: 100, 2, 5 → Result: 10.0 (100 ÷ 2 ÷ 5)

### Your Function
```python
def flexible_calculator(operation, *numbers, **options):
    """
    Perform mathematical operations on any number of values.
    
    Parameters:
    operation (str): The operation to perform ("add", "subtract", "multiply", "divide")
    *numbers: Variable number of numerical values
    **options: Optional settings like 'round_to' for decimal places
    
    Returns:
    float: Result of the calculation
    """
    # Your code here
    pass
```

## Problem 2: Student Grade Manager

### Scenario
A teacher needs to manage student grades with flexible grading options and different calculation methods.

### Requirements
Create a function that can calculate student grades with various options like rounding, weighting, and grade curves.

### Test Data
- Grades: 85, 92, 78, 96, 88
- Options: round_to=1, apply_curve=True, curve_points=5
- Expected: Average with curve applied and rounded

### Your Function
```python
def calculate_student_grade(*grades, **options):
    """
    Calculate student grades with flexible options.
    
    Parameters:
    *grades: Variable number of grade values
    **options: Grading options including:
        - round_to: Number of decimal places
        - apply_curve: Whether to apply a grade curve
        - curve_points: Points to add for curve
        - drop_lowest: Whether to drop the lowest grade
        - weight: Weight for each grade (if provided)
    
    Returns:
    dict: Grade calculation results
    """
    # Your code here
    pass
```

## Problem 3: Shopping Cart with Discounts

### Scenario
An e-commerce site needs to calculate cart totals with various discount and tax options.

### Requirements
Create a function that can handle any number of items with different discount types and tax calculations.

### Test Data
- Items: 10.99, 5.50, 3.25, 15.00
- Options: discount_type="percentage", discount_value=10, tax_rate=8.5, free_shipping_threshold=25

### Your Function
```python
def calculate_cart_total(*item_prices, **options):
    """
    Calculate shopping cart total with discounts and taxes.
    
    Parameters:
    *item_prices: Variable number of item prices
    **options: Cart options including:
        - discount_type: "percentage" or "fixed"
        - discount_value: Discount amount or percentage
        - tax_rate: Tax rate as percentage
        - free_shipping_threshold: Minimum for free shipping
        - shipping_cost: Cost of shipping if not free
    
    Returns:
    dict: Cart calculation breakdown
    """
    # Your code here
    pass
```

## Problem 4: Text Formatter

### Scenario
A content management system needs to format text with various styling options.

### Requirements
Create a function that can format text with different options like case conversion, padding, and prefixes/suffixes.

### Test Data
- Text: "hello world python"
- Options: case="upper", prefix=">>> ", suffix=" <<<", padding=20, align="center"

### Your Function
```python
def format_text(*text_parts, **format_options):
    """
    Format text with various styling options.
    
    Parameters:
    *text_parts: Variable number of text strings to combine
    **format_options: Formatting options including:
        - case: "upper", "lower", "title", "capitalize"
        - prefix: Text to add at the beginning
        - suffix: Text to add at the end
        - padding: Total width for padding
        - align: "left", "center", "right"
        - separator: Character to join multiple text parts
    
    Returns:
    str: Formatted text
    """
    # Your code here
    pass
```

## Problem 5: Data Validator

### Scenario
A form processing system needs to validate different types of data with various validation rules.

### Requirements
Create a function that can validate any number of data fields with different validation criteria.

### Test Data
- Data: "john@example.com", "password123", 25, "New York"
- Validation rules: email_format=True, min_length=8, min_age=18, required_city=True

### Your Function
```python
def validate_data(*data_fields, **validation_rules):
    """
    Validate data fields with various rules.
    
    Parameters:
    *data_fields: Variable number of data values to validate
    **validation_rules: Validation options including:
        - email_format: Validate email format
        - min_length: Minimum length for strings
        - max_length: Maximum length for strings
        - min_age: Minimum age for numbers
        - max_age: Maximum age for numbers
        - required: Whether field is required
        - data_types: Expected data types
    
    Returns:
    dict: Validation results for each field
    """
    # Your code here
    pass
```

## Problem 6: Weather Data Aggregator

### Scenario
A weather app needs to process temperature data from multiple sources with different units and time periods.

### Requirements
Create a function that can aggregate weather data with unit conversion and time filtering options.

### Test Data
- Temperatures: 25, 28, 30, 27, 26 (in Celsius)
- Options: convert_to="fahrenheit", time_period="daily", include_stats=True, alert_threshold=30

### Your Function
```python
def process_weather_data(*temperatures, **options):
    """
    Process weather data with various options.
    
    Parameters:
    *temperatures: Variable number of temperature readings
    **options: Processing options including:
        - convert_to: "fahrenheit" or "celsius"
        - time_period: "hourly", "daily", "weekly"
        - include_stats: Whether to include statistics
        - alert_threshold: Temperature threshold for alerts
        - source: Data source identifier
        - location: Location of measurements
    
    Returns:
    dict: Processed weather data
    """
    # Your code here
    pass
```

## Problem 7: Flexible Logger

### Scenario
A logging system needs to handle different types of log messages with various formatting and output options.

### Requirements
Create a function that can log messages with different levels, formats, and output destinations.

### Test Data
- Messages: "User logged in", "Database error occurred", "System started"
- Options: level="info", format="timestamp", output="console", include_location=True

### Your Function
```python
def log_message(*messages, **log_options):
    """
    Log messages with various formatting and output options.
    
    Parameters:
    *messages: Variable number of message strings
    **log_options: Logging options including:
        - level: "debug", "info", "warning", "error", "critical"
        - format: "simple", "timestamp", "detailed"
        - output: "console", "file", "both"
        - include_location: Whether to include function location
        - timestamp_format: Format for timestamps
        - max_length: Maximum message length
    
    Returns:
    str: Formatted log message
    """
    # Your code here
    pass
```

## Problem 8: Configuration Manager

### Scenario
An application needs to manage configuration settings that can be set in different ways with various validation and default values.

### Requirements
Create a function that can handle configuration settings with defaults, validation, and different data types.

### Test Data
- Settings: "database_url", "max_connections", "debug_mode", "timeout"
- Values: "postgresql://localhost", 100, True, 30
- Options: validate_urls=True, min_connections=1, max_connections=1000, default_timeout=60

### Your Function
```python
def configure_settings(*setting_names, **config_options):
    """
    Configure application settings with validation and defaults.
    
    Parameters:
    *setting_names: Variable number of setting names
    **config_options: Configuration options including:
        - values: Dictionary of setting values
        - defaults: Dictionary of default values
        - validate_urls: Whether to validate URL settings
        - min_connections: Minimum for connection settings
        - max_connections: Maximum for connection settings
        - default_timeout: Default timeout value
        - required_settings: List of required settings
    
    Returns:
    dict: Validated configuration settings
    """
    # Your code here
    pass
```

## Testing Your Functions

After writing each function, test it with the provided data and additional test cases:

```python
# Example testing
result = flexible_calculator("add", 1, 2, 3, 4, 5, round_to=2)
print(f"Addition result: {result}")  # Should output: Addition result: 15.0

# Test with different options
result2 = flexible_calculator("multiply", 2, 3, 4, round_to=1)
print(f"Multiplication result: {result2}")  # Should output: Multiplication result: 24.0
```

## Advanced Challenges

Once you've completed the basic functions, try these advanced challenges:

### Challenge 1: Function Wrapper
Create a function that can wrap other functions with logging, timing, or error handling:

```python
def function_wrapper(func, *args, **kwargs):
    """
    Wrap any function with additional functionality.
    
    Parameters:
    func: The function to wrap
    *args: Arguments to pass to the function
    **kwargs: Options for wrapping (log=True, time=True, retry=3)
    
    Returns:
    The result of the wrapped function
    """
    # Your code here
    pass
```

### Challenge 2: Data Pipeline
Create a function that can process data through multiple transformation steps:

```python
def data_pipeline(*data, **transformations):
    """
    Process data through multiple transformation steps.
    
    Parameters:
    *data: Variable number of data items
    **transformations: Transformation options like:
        - steps: List of transformation functions
        - filter_none: Whether to filter out None values
        - sort: Whether to sort the results
        - unique: Whether to remove duplicates
    
    Returns:
    list: Transformed data
    """
    # Your code here
    pass
```

## Reflection Questions

After completing all functions, consider:

1. **Which function was most challenging to design? Why?**
2. **How did you decide when to use *args vs **kwargs?**
3. **What edge cases did you need to handle?**
4. **How could you make your functions more robust?**
5. **What real-world applications could benefit from these flexible functions?**

## Best Practices Summary

1. **Use *args for variable positional arguments** - When you don't know how many values you'll receive
2. **Use **kwargs for configuration options** - When you want to make functions customizable
3. **Provide sensible defaults** - Make your functions work even with minimal input
4. **Handle edge cases** - Empty inputs, invalid options, etc.
5. **Document your functions well** - Explain what options are available
6. **Test thoroughly** - Try different combinations of arguments and options

## Next Steps

Once you've mastered these flexible function patterns, you'll be ready to:
- Build more complex applications with flexible APIs
- Work with existing libraries that use these patterns
- Create reusable code components
- Design better function interfaces for your projects
