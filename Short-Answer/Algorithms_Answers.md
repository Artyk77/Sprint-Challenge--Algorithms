#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
```python
  a = 0 # O(1)
  while (a < n * n * n): # O(N)
    a = a + n * n 
```

Runtime complexity (RC) for this algorithm is O(N) due to the only variable this loop depends on is `n`, therefore is only one loop.  `a` constant, so this conditional function only runs as many times as `n` the `n * n * n` and `n * n` cancel each other and leave it as `n`
, since N is the only number that may vary the scale of the runtime, it is said to be O(N).


b)
```python
sum = 0 #O(1)
  for i in range(n): #O(N)
    j = 1 #O(1)
    while j < n: #O(Log N)
      j *= 2 # Exp increased
      sum += 1 #O(1)
```

RC for this nested looping is O(N Log N). This is because there are two loops, one nested inside of the other, that depends on N. As a result, the inner loop, which depends on approaching N, increases exponentially, so the time to reach N is dwindled by half. Then, instead of O(N^2), RC is O(N Log N)

c)
```python
def bunnyEars(bunnies):
  if bunnies == 0: #O(1)
    return 0
  return 2 + bunnyEars(bunnies-1) #O(N)
```
RC for this function is O(N). This is because of the bunnyEars function having a single recursive callstack (i.e.The function operates over bunnyEars `n` + 1 times), and resolving once bunnies reaches 0 beacuse one conditio was met met, therefore the O(N) complexity.

## Exercise II

Suppose that you have an n-story building and plenty of eggs. Suppose also that an egg gets broken if it is thrown off floor f or higher, and doesn't get broken if dropped off a floor less than floor f. Devise a strategy to determine the value of f such that the number of dropped + broken eggs is minimized.

- Start at floor 0
- Scale linear until first egg breaks !
- Execute a binary search numerical solution (algorithM) because the bldg have to be sorted in order to be drawn the floor of F when egg breaks
- Split the number of floors by half, and drop an egg at mid floor.
- If it is broken at middle floor, deletes upper half of floors and work down till the egg doesnt break
- Whether is not broken, eliminate bottom half and work till egg breaks.
- The balance might be met through eggs broken and eggs dropped. 
