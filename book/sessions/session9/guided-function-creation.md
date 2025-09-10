# Guided Function Creation: Flexible Data Processor

## Step-by-Step Function Development

Let's build a flexible data processing system step by step, learning how to use `*args` and `**kwargs` to create powerful, reusable functions.

## Step 1: Basic Data Aggregator with *args

### Problem Analysis
We need a function that can calculate statistics for any number of data points.

### Function Design
```python
def calculate_statistics(*numbers):
    """
    Calculate basic statistics for any number of data points.
    
    Parameters:
    *numbers: Variable number of numerical values
    
    Returns:
    dict: Dictionary containing count, sum, average, min, and max
    """
    if not numbers:
        return {"error": "No numbers provided"}
    
    count = len(numbers)
    total = sum(numbers)
    average = total / count
    minimum = min(numbers)
    maximum = max(numbers)
    
    return {
        "count": count,
        "sum": total,
        "average": average,
        "min": minimum,
        "max": maximum
    }
```

### Testing the Function
```python
# Test with different numbers of arguments
stats1 = calculate_statistics(1, 2, 3, 4, 5)
print("Stats for 1,2,3,4,5:", stats1)
# Output: {'count': 5, 'sum': 15, 'average': 3.0, 'min': 1, 'max': 5}

stats2 = calculate_statistics(10, 20, 30)
print("Stats for 10,20,30:", stats2)
# Output: {'count': 3, 'sum': 60, 'average': 20.0, 'min': 10, 'max': 30}

stats3 = calculate_statistics(100)
print("Stats for 100:", stats3)
# Output: {'count': 1, 'sum': 100, 'average': 100.0, 'min': 100, 'max': 100}
```

## Step 2: Enhanced Data Processor with **kwargs

### Problem Analysis
We need to add configuration options to our statistics function.

### Function Design
```python
def enhanced_statistics(*numbers, **options):
    """
    Calculate statistics with configurable options.
    
    Parameters:
    *numbers: Variable number of numerical values
    **options: Configuration options including:
        - round_to: Number of decimal places to round to
        - include_median: Whether to include median calculation
        - format_output: Whether to format numbers nicely
    
    Returns:
    dict: Dictionary containing calculated statistics
    """
    if not numbers:
        return {"error": "No numbers provided"}
    
    # Get options with defaults
    round_to = options.get("round_to", 2)
    include_median = options.get("include_median", False)
    format_output = options.get("format_output", False)
    
    # Basic calculations
    count = len(numbers)
    total = sum(numbers)
    average = total / count
    minimum = min(numbers)
    maximum = max(numbers)
    
    # Round if requested
    if round_to is not None:
        average = round(average, round_to)
        total = round(total, round_to)
    
    # Calculate median if requested
    median = None
    if include_median:
        sorted_numbers = sorted(numbers)
        n = len(sorted_numbers)
        if n % 2 == 0:
            median = (sorted_numbers[n//2 - 1] + sorted_numbers[n//2]) / 2
        else:
            median = sorted_numbers[n//2]
        
        if round_to is not None:
            median = round(median, round_to)
    
    # Build result
    result = {
        "count": count,
        "sum": total,
        "average": average,
        "min": minimum,
        "max": maximum
    }
    
    if median is not None:
        result["median"] = median
    
    # Format output if requested
    if format_output:
        result = {k: f"{v:,.2f}" if isinstance(v, (int, float)) else v 
                 for k, v in result.items()}
    
    return result
```

### Testing the Function
```python
# Test with different options
data = [85, 92, 78, 96, 88, 91, 87]

# Basic usage
stats1 = enhanced_statistics(*data)
print("Basic stats:", stats1)

# With rounding
stats2 = enhanced_statistics(*data, round_to=1)
print("Rounded stats:", stats2)

# With median
stats3 = enhanced_statistics(*data, include_median=True)
print("Stats with median:", stats3)

# With formatting
stats4 = enhanced_statistics(*data, format_output=True, round_to=1)
print("Formatted stats:", stats4)
```

## Step 3: Flexible Data Filter with *args and **kwargs

### Problem Analysis
We need a function that can filter data based on various criteria.

### Function Design
```python
def filter_data(*data, **criteria):
    """
    Filter data based on various criteria.
    
    Parameters:
    *data: Variable number of data points
    **criteria: Filtering criteria including:
        - min_value: Minimum value to include
        - max_value: Maximum value to include
        - even_only: Include only even numbers
        - odd_only: Include only odd numbers
        - above_average: Include only values above average
    
    Returns:
    dict: Dictionary containing filtered results and statistics
    """
    if not data:
        return {"error": "No data provided"}
    
    # Get criteria with defaults
    min_value = criteria.get("min_value", None)
    max_value = criteria.get("max_value", None)
    even_only = criteria.get("even_only", False)
    odd_only = criteria.get("odd_only", False)
    above_average = criteria.get("above_average", False)
    
    # Start with all data
    filtered = list(data)
    
    # Apply filters
    if min_value is not None:
        filtered = [x for x in filtered if x >= min_value]
    
    if max_value is not None:
        filtered = [x for x in filtered if x <= max_value]
    
    if even_only:
        filtered = [x for x in filtered if x % 2 == 0]
    
    if odd_only:
        filtered = [x for x in filtered if x % 2 == 1]
    
    if above_average:
        average = sum(data) / len(data)
        filtered = [x for x in filtered if x > average]
    
    # Calculate statistics for filtered data
    if filtered:
        filtered_stats = {
            "count": len(filtered),
            "sum": sum(filtered),
            "average": sum(filtered) / len(filtered),
            "min": min(filtered),
            "max": max(filtered)
        }
    else:
        filtered_stats = {"error": "No data matches criteria"}
    
    return {
        "original_data": list(data),
        "filtered_data": filtered,
        "filtered_stats": filtered_stats,
        "criteria_used": criteria
    }
```

### Testing the Function
```python
# Test with different filtering criteria
test_data = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

# Filter by range
result1 = filter_data(*test_data, min_value=3, max_value=8)
print("Range filter (3-8):", result1)

# Filter even numbers
result2 = filter_data(*test_data, even_only=True)
print("Even numbers only:", result2)

# Filter above average
result3 = filter_data(*test_data, above_average=True)
print("Above average:", result3)

# Multiple filters
result4 = filter_data(*test_data, min_value=5, even_only=True)
print("Min 5 and even:", result4)
```

## Step 4: Complete Data Analysis System

### Problem Analysis
We need a comprehensive function that combines all our capabilities.

### Function Design
```python
def analyze_data(*data, analysis_type="basic", **options):
    """
    Comprehensive data analysis with multiple analysis types.
    
    Parameters:
    *data: Variable number of data points
    analysis_type: Type of analysis ("basic", "filtered", "comparative")
    **options: Analysis options including all previous options plus:
        - compare_with: Data to compare against
        - group_by: Group data by criteria
        - export_format: Format for results ("dict", "summary", "detailed")
    
    Returns:
    dict or str: Analysis results in requested format
    """
    if not data:
        return {"error": "No data provided"}
    
    # Get options
    export_format = options.get("export_format", "dict")
    
    if analysis_type == "basic":
        # Use our enhanced statistics function
        result = enhanced_statistics(*data, **options)
        
    elif analysis_type == "filtered":
        # Use our filter function
        result = filter_data(*data, **options)
        
    elif analysis_type == "comparative":
        # Compare with another dataset
        compare_with = options.get("compare_with", [])
        if not compare_with:
            return {"error": "No comparison data provided"}
        
        # Analyze both datasets
        data1_stats = enhanced_statistics(*data, **options)
        data2_stats = enhanced_statistics(*compare_with, **options)
        
        result = {
            "dataset1": {
                "data": list(data),
                "stats": data1_stats
            },
            "dataset2": {
                "data": list(compare_with),
                "stats": data2_stats
            },
            "comparison": {
                "avg_difference": data1_stats["average"] - data2_stats["average"],
                "count_difference": data1_stats["count"] - data2_stats["count"]
            }
        }
    
    else:
        return {"error": f"Unknown analysis type: {analysis_type}"}
    
    # Format output
    if export_format == "summary":
        return format_summary(result, analysis_type)
    elif export_format == "detailed":
        return format_detailed(result, analysis_type)
    else:
        return result

def format_summary(result, analysis_type):
    """Format results as a summary string"""
    if analysis_type == "basic":
        return f"Data Summary: {result['count']} values, avg: {result['average']}, range: {result['min']}-{result['max']}"
    elif analysis_type == "filtered":
        return f"Filtered: {result['filtered_stats']['count']} of {len(result['original_data'])} values match criteria"
    else:
        return "Summary not available for this analysis type"

def format_detailed(result, analysis_type):
    """Format results as a detailed string"""
    if analysis_type == "basic":
        return f"""Detailed Analysis:
Count: {result['count']}
Sum: {result['sum']}
Average: {result['average']}
Minimum: {result['min']}
Maximum: {result['max']}"""
    else:
        return "Detailed format not available for this analysis type"
```

### Testing the Complete System
```python
# Test the complete system
test_data = [85, 92, 78, 96, 88, 91, 87, 94, 89, 93]
compare_data = [80, 85, 90, 95, 100, 85, 90, 95, 80, 85]

# Basic analysis
basic_result = analyze_data(*test_data)
print("Basic analysis:", basic_result)

# Filtered analysis
filtered_result = analyze_data(*test_data, analysis_type="filtered", min_value=85)
print("Filtered analysis:", filtered_result)

# Comparative analysis
comparative_result = analyze_data(*test_data, analysis_type="comparative", compare_with=compare_data)
print("Comparative analysis:", comparative_result)

# Summary format
summary = analyze_data(*test_data, export_format="summary")
print("Summary:", summary)

# Detailed format
detailed = analyze_data(*test_data, export_format="detailed")
print("Detailed:", detailed)
```

## Key Learning Points

### 1. Progressive Complexity
- Start with simple `*args` functionality
- Add `**kwargs` for configuration options
- Combine both for maximum flexibility
- Build comprehensive systems step by step

### 2. Default Values and Error Handling
- Always provide sensible defaults for options
- Handle edge cases (empty data, invalid options)
- Return meaningful error messages
- Validate input data

### 3. Function Composition
- Build smaller, focused functions first
- Combine them into larger, more powerful functions
- Each function has a clear responsibility
- Functions can call other functions

### 4. Flexibility vs. Complexity
- `*args` and `**kwargs` make functions flexible
- But they can also make them complex
- Balance flexibility with usability
- Document your functions well

### 5. Real-World Application
- These patterns are used in real libraries and frameworks
- Understanding them helps you use existing code better
- They make your own code more reusable
- They're essential for building flexible APIs

## Testing Your Functions

Always test with different scenarios:

```python
# Test with different data sizes
small_data = [1, 2, 3]
large_data = list(range(1, 101))

# Test with different options
basic_options = {}
complex_options = {"round_to": 1, "include_median": True, "format_output": True}

# Test edge cases
empty_data = []
single_value = [42]
negative_numbers = [-5, -3, -1, 0, 1, 3, 5]
```

## Next Steps

In the practice functions section, you'll create your own flexible functions using `*args` and `**kwargs`. Remember to:
- Start simple and build up complexity
- Test with different data and options
- Handle edge cases gracefully
- Make your functions useful and reusable
