It's like a chain reaction where each number depends on the two before it. The first ten numbers of the Fibonacci sequence are: 0, 1, 1, 2, 3, 5, 8, 13, 21, and 34. Each number is the sum of the two before it.

```python
def fibonacci(n): 
	if n <= 1: 
		return n 
	else: 
		return fibonacci(n-1) + fibonacci(n-2) 

for i in range(10): 
	print(fibonacci(i))
```