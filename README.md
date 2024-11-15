# GÉANT Python Developer interview questions/topics


1. Compare and discuss the differences/advantages/disadvantes of the following code snippets:

snippet 1

``` python
def square_numbers(data):
    result = []
    for item in data:
        result.append(item ** 2)
    return result


def remove_odd_numbers(data):
    result = []
    for item in data:
        if item % 2 == 0:
            result.append(item)
    return result


def process_data(data):
    result1 = remove_odd_numbers(data)
    result2 = square_numbers(result1)
    return result2


if __name__ == '__main__':
    input_data = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]
    output_data = process_data(input_data)
    for item in output_data:
        print(item)
```

snippet 2

```python

def square_numbers(data):
    for item in data:
        yield item ** 2


def remove_odd_numbers(data):
    for item in data:
        if item % 2 == 0:
            yield item


def process_data(data):
    result1 = remove_odd_numbers(data)
    result2 = square_numbers(result1)
    return result2


if __name__ == '__main__':
    input_data = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]
    output_data = process_data(input_data)
    for item in output_data:
        print(item)
```

snippet3

```python

def _is_even(number):
    return number % 2 == 0


def _compute_square(number):
    return number ** 2


def process_data(data):
    result1 = filter(_is_even, data)
    result2 = map(_compute_square, result1)
    return result2


if __name__ == '__main__':
    input_data = [1,2,3,4,5,6,7,8,9,10,11,12,13,14,15]
    output_data = process_data(input_data)
    for item in output_data:.
        print(item)
```

2. What are the differences between lists, tuples, sets and dicts in Python?

3. Can you describe ways you may iterate over them?

4. Imagine that you are writing an application that will apply the same logic to
   process multiple data sets in parallel.  Would you do this using mulitple threads
   or multiple processes (or some other method)?  Why?

5. Propose some unit tests for the following function:

   ```python
   def is_within_one_week(date):
   “””
    `date` should be a string representing some day/time that can be parsed
       This function returns True if the `date` string is within 1 week of the
       current time (before or after). Otherwise it returns False.
   “””
       # todo
       pass
   ```

6. Write a short Python program, or function, that loads the `urls.json` file in this
   repository.  It then prints out to the console for each element of the list, only for
   those elements of the list with `public == True`, text in the format:

   ```html
    <a href="url">title</a>
   ```
