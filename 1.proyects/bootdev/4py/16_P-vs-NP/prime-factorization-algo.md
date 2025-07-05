---
id: prime-factorization-algo
aliases:
  - sqrt(n)
tags: []
---

```python
import math
def prime_factors(n):
    primes = []
    while n % 2 == 0:
        n = n / 2
        primes.append(2)
    for i in range(3, int(sqrt(n)) + 1, 2):
        while n % i == 0:
            n = n / i
            primes.append(int(i))
    if n > 2:
        primes.append(int(n))
    return primes
```

Boots: Consider this: suppose `n` can be written as a product of two integers `a * b = n`. What happens if both `a` and `b` are greater than the square root of `n`?

If you multiply two numbers, both larger than `sqrt(n)`, will their product ever equal `n` or will it be something else? What does this tell you about searching for factors larger than the square root?

    if a and b are bigger than than sqrt(n) then they could not ever equal n

Boots: Exactly right! If both `a` and `b` are greater than `sqrt(n)`, their product will be greater than `n`. That means at least one factor of any product less than or equal to `n` must be less than or equal to `sqrt(n)`.

So, if you find no factors up to `sqrt(n)`, what must be true about `n`? Why does that justify simply appending `n` to your primes list at the end if it's still greater than 2?

    means that its a prime number

