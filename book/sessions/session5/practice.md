# Session 5: Practice Exercise

Create a program that finds all prime numbers up to a given number:

```python
# Prime number finder
n = int(input("Enter a number to find primes up to: "))

print(f"Prime numbers up to {n}:")
print("=" * 25)

for num in range(2, n + 1):
    is_prime = True
    
    # Check if num is prime
    for i in range(2, int(num ** 0.5) + 1):
        if num % i == 0:
            is_prime = False
            break
    
    if is_prime:
        print(num, end=" ")

print()  # New line at the end
```