<!--
Meta Description: # Understanding the `tan` Function in C: A Comprehensive Guide ## Synopsis The `tan` function in C is a standard mathematical function used to compute...
Meta Keywords: tan, function, tangent, angle, radians
-->

# Understanding the `tan` Function in C: A Comprehensive Guide

## Synopsis
The `tan` function in C is a standard mathematical function used to compute the tangent of an angle given in radians. It is part of the `<math.h>` library and is widely used in applications involving trigonometry, geometry, and physics.

## Documentation
### Purpose
The `tan` function calculates the tangent of a specified angle. The tangent of an angle in a right triangle is defined as the ratio of the length of the opposite side to the length of the adjacent side. In mathematical terms, `tan(x) = sin(x) / cos(x)`, where `x` is measured in radians.

### Usage
To use the `tan` function, you need to include the `<math.h>` header file in your C program. The function prototype is as follows:

```c
#include <math.h>
double tan(double x);
```

### Parameters
- `x`: A double representing the angle in radians.

### Return Value
The function returns the tangent of the angle `x` as a double. If `x` is an infinite value, the function returns `NaN` (Not a Number). If `x` is an odd multiple of π/2 (90 degrees, 270 degrees, etc.), the function will also return `NaN`, indicating that the tangent is undefined at those points.

## Examples
Here are some basic usage examples of the `tan` function in C:

### Example 1: Basic Usage
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 4; // 45 degrees in radians
    double result = tan(angle);
    printf("The tangent of 45 degrees is: %f\n", result);
    return 0;
}
```

### Example 2: Calculating Tangent of Different Angles
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angles[] = {0, M_PI / 4, M_PI / 2, M_PI}; // 0, 45, 90, 180 degrees
    for (int i = 0; i < 4; i++) {
        printf("The tangent of %.2f radians is: %f\n", angles[i], tan(angles[i]));
    }
    return 0;
}
```

### Example 3: Handling Undefined Values
```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle = M_PI / 2; // 90 degrees in radians
    double result = tan(angle);
    if (isnan(result)) {
        printf("The tangent of 90 degrees is undefined.\n");
    } else {
        printf("The tangent of 90 degrees is: %f\n", result);
    }
    return 0;
}
```

## Explanation
When using the `tan` function, keep in mind the following common pitfalls and notes:

- **Input in Radians**: Ensure that the input angle is in radians. If you have the angle in degrees, convert it to radians by multiplying by `π/180` before passing it to `tan`.
  
- **Undefined Values**: The `tan` function will return `NaN` for angles where the tangent is undefined, such as odd multiples of π/2. Always check for `NaN` when working with angles near these values to avoid unexpected behavior in your program.

- **Precision**: The results from the `tan` function can suffer from floating-point precision issues, especially for very large or very small input values. Use the results cautiously in critical calculations.

## One Line Summary
The `tan` function in C computes the tangent of an angle in radians, returning a double value or `NaN` for undefined angles.