# Random Module

We can use `import random` to help us generate random numbers. 

`randit` will create a random integer, it will look like this:

```
print random.randint(0, 5)
```
where the output can be a number from 1 to 5. 

`random` for large numbers, so

```
import random
random.random() * 100
```

and it will give us a number from 1 to 100.

`choice` can be used to pick out an element from a list, it will look like this:

```
import random
myList = [2, 109, False, 10, "Lorem", 482, "Ipsum"]
random.choice(myList)
```

`shuffle` mixes up the order in the list.

```
from random import shuffle
x = [[i] for i in range(10)]
shuffle(x)

print(x) 
--> [[9], [2], [7], [0], [4], [5], [3], [1], [8], [6]]
```

`randrange` selects a random element from range. 

```
random.randrange(start, stop[, step])
```
An example is shown below:

```
import random
for i in range(3):
    print random.randrange(0, 101, 5)
```
## Risk Analysis

Risk analysis is used whenever a new software has been built. It is used to mitigate risks,prevent damages, and coming up with solutions. Here's a list of possible encounters of risk:

- Use of new hardware
- Use of new technology
- Use of new automation tool
- The sequence of code
- Availability of test resources for the application

## Risk Magnitude
Risk magnitude indicator is as follows: 

**High:** means the effect of the risk would be very high and non-tolerable. The company might face loss.

**Medium:** it is tolerable but not desirable. The company may suffer financially but there is a limited risk.

**Low:** it is tolerable. There lies little or no external exposure or no financial loss.

## Perspective of Risk Assessment

**Effect** – To assess risk by Effect. In case you identify a condition, event or action and try to determine its impact.

**Cause** – To assess risk by Cause is opposite of by Effect. Initialize scanning the problem and reach to the point that could be the most probable reason behind that.

**Likelihood** – To assess risk by Likelihood is to say that there is a probability that a requirement won’t be satisfied.

## Three Steps of Risk Analysis

1. Searching the risk

2. Analyzing the impact of each individual risk

3. Measures for the risk identified


