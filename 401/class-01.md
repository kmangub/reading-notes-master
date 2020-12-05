# Pain and Suffering

What’s your perspective?

- The tech community is the place to be in this day and age because of its dynamic change for the better.

Why are you doing this?
- I'm doing this because I want to make my life and other's life easier by creating appplications. 

Do you want what comes at the end of this journey? 
- I want to become a software developer after I graduate Code Fellows.

Are you doing this for you?

- Not only me, but for other people too.

# Big O

Big O is a notation used in Computer Science or in an algorithm to show the worst-case scenario and the execution time required. 

## O(1)
The algorithm that executes at the same time no matter the size of the input data. An example is shown below:

```
bool IsFirstElementNull(IList<string> elements)
{
    return elements[0] == null;
}
```

## O(N)
An algorithm that grows in relation to the input data set. Example: 

```
bool ContainsValue(IList<string> elements, string value)
{
    foreach (var element in elements)
    {
        if (element == value) return true;
    }

    return false;
}
```

## O(N^2)
Proportional to the square of the size of the data set. Example: 
```
bool ContainsDuplicates(IList<string> elements)
{
    for (var outer = 0; outer < elements.Count; outer++)
    {
        for (var inner = 0; inner < elements.Count; inner++)
        {
            // Don't compare with self
            if (outer == inner) continue;

            if (elements[outer] == elements[inner]) return true;
        }
    }

    return false;
}
```

## O(2^N)
An algorithm that grows with each input data set added. Example:
```
int Fibonacci(int number)
{
    if (number <= 1) return number;

    return Fibonacci(number - 2) + Fibonacci(number - 1);
}
```

## Logarithms or O(logN)

Peaks at the beginning and then flattens as the data set increases; the time to complete also increases.




