# PL EQ Blocks Issues

Currently, we have only been working on this element for one semester via one main developer. There are likely to be issues with the element. For this reason, it's recommended that you use the element with caution. We don't recommend using this element for graded assignments. (Or just make this worth 0 pnts so students can experiment with it without being penalized.)

## Front End
On the front end we haven't encountered any major issues. As in, currently we believe the front end works just as intended. The student can see their answer, edit it via drag and drop or keyboard and the answer is correctly sent to the server. (Additionally, the student's answer is also correctly saved)

## Back End
On the back end, we have a few known issues. We use pytest to test the solution checker against the following [40 test cases](https://github.com/PrairieLearn/pl-uiuc-mse458/blob/master/elements/pl-eq-blocks/eq_test.py). Note we plan to add more in the future.

Out of those 40 test cases, we have 4 that are currently failing.

### Square Root Failing Test Cases
These fail due to that our solution checker not being able to properly handle sqrts. We recommend that you don't use roots in your solution. 
```py title="Sqrt Failling Test Case #1"
{
    "student": "a^2 + b^2 = c^2",
    "solution": "abs(c) = (a^2 + b^2)^(1/2)", 
    "expected": True, 
    "variables": ["a", "b", "c"],
}
```

```py title="Sqrt Failling Test Case #2"
{
    "student": "ax^2 + bx + c = 0",
    "solution": "x = (-b + (b^2 - 4ac)^(1/2))/(2a)",
    "expected": False,
    "variables": ["a", "b", "c", "x"],
}
```

```py title="Sqrt Failling Test Case #3"
{
    "student": "(x - h)^2 + (y - k)^2 = r^2",
    "solution": "x^2 + y^2 - 2hx - 2ky + h^2 + k^2 - r^2 = 0",
    "expected": True,
    "variables": ["x", "y", "h", "k", "r"],
}
```

### Complex Numbers Failing Test Case
Re and Im functions are not currently supported. Instead we recommend you just a variable to replace the the imaginary part. Ex make the variable 'I' for your back end and use 'i' in your front end.

```py title="Complex Numbers Failling Test Case"
{
    "student": "z = x + iy",
    "solution": "x = Re(z), y = Im(z)",
    "expected": False,
    "variables": ["x", "y", "z", "i"],
}
```