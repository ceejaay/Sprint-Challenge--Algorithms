Add your answers to the Algorithms exercises here.

```
a)  a = 0
    while (a < n * n * n):
      a = a + n * n
```

The above algorithm is `O(n^2)`.
if `n == 2`,  the loop will run until `a == 8`.
In this expression: `a = a + n * n` `a` is set to `4`.
The second time around `a` will become `8`. `4 + 2 * 2 == 8`
The expression `a + n * n` is only increments `a` by half the required number.


```
b)  sum = 0

    for i in range(n):
      i += 1
      for j in range(i + 1, n):
        j += 1
        for k in range(j + 1, n):
          k += 1
          for l in range(k + 1, 10 + k):
            l += 1
            sum += 1
```
The above algorithm runtime is O(n^4).
In each for loop the amount the loop runs is incremented by 1.
After the `i` loop, `j` will run once for each `i` loop plus one. So if `i` is 1. The `j` loop will run once plus one. So twice. If `i` is 5, `j` will run six times for each item.
We drop the `+1` constant, thus the algorithm has four `for` loops, there for the runtime is `O(n^4)`



```
c)  def bunnieEars(bunnies):
      if bunnies == 0:
        return 0

      return 2 + bunnyEars(bunnies-1)
```

The above algorithm is `O(n*2)`.
For each `n` or `bunnies` the ` return 2 + bunnyEars(bunnies-1)` runs twice.

```
Suppose that you have an _n_-story building and plenty of eggs. Suppose also
that an egg gets broken if it is thrown off floor _f_ or higher, and doesn't get
broken if dropped off a floor less than floor _f_. Devise a strategy to
determine the value of _f_ such that the number of dropped eggs is minimized.

Write out your proposed algorithm in plain English or pseudocode and give the
runtime complexity of your solution.

```

This is a plan for the above problem:

First, I would start at the top floor. Drop an egg, see if it breaks.
    If it broke, I would go down to the Top floor / 2. Drop an egg. If it breaks, I would reapeat cutting the number of floors in half until I found a floor where dropping the egg does not break it.
    I would remember the last floor where the egg broke, and the floor where the egg didn't break.
    Then I would go to the floor halfway between the egg-breaking floor and the non-egg-breaking floor.
    If the breaks from that height. I would go down half the floors between the current floor, and the floor where the egg didn't break. I would repeat until I find the floor where current floor + 1 breaks. and Current floor -1 where it doesn't break.
    That floor between the floor where the egg breaks and the floor where it doesn't break is the highest floor where the egg doesn't break.

    The runtime for this solution is O(log n). For each egg drop, we cut the number of floors in half.
