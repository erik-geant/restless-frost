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
