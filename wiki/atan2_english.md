<!--
Meta Description: # Understanding `atan2`: The C Function for Calculating the Arc Tangent ## Synopsis The `atan2` function in C is a mathematical function used to compu...
Meta Keywords: angle, atan2, function, quadrant, double
-->

# Understanding `atan2`: The C Function for Calculating the Arc Tangent

## Synopsis
The `atan2` function in C is a mathematical function used to compute the angle whose tangent is the quotient of two specified numbers, typically representing the y-coordinate and x-coordinate of a point in Cartesian coordinates.

## Documentation
### Purpose
The `atan2` function is designed to calculate the arc tangent of the two variables \(y\) and \(x\), returning the angle in radians. Unlike the simple `atan` function, `atan2` takes into account the signs of both arguments to determine the correct quadrant of the resulting angle.

### Usage
The function is defined in the `<math.h>` header file and follows the syntax:

```c
double atan2(double y, double x);
```

- **Parameters**:
  - `y`: The ordinate (the vertical coordinate).
  - `x`: The abscissa (the horizontal coordinate).

- **Return Value**:
  - Returns the angle in radians between the positive x-axis and the point (x, y).
  - The range of the result is \(-\pi\) to \(\pi\).

### Example
Here is a basic example of using the `atan2` function in a C program:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double y = 1.0;
    double x = 1.0;
    double angle = atan2(y, x);

    printf("The angle in radians is: %f\n", angle);
    printf("The angle in degrees is: %f\n", angle * (180.0 / M_PI));

    return 0;
}
```

### Explanation
#### Common Pitfalls and Gotchas
- **Quadrant Determination**: `atan2` correctly identifies the quadrant of the angle based on the signs of `y` and `x`. For instance:
  - If \(y > 0\) and \(x > 0\), the angle is in the first quadrant.
  - If \(y > 0\) and \(x < 0\), the angle is in the second quadrant.
  - If \(y < 0\) and \(x < 0\), the angle is in the third quadrant.
  - If \(y < 0\) and \(x > 0\), the angle is in the fourth quadrant.
  
- **Division by Zero**: If `x` is zero and `y` is positive, `atan2` returns \(\frac{\pi}{2}\); if `x` is zero and `y` is negative, it returns \(-\frac{\pi}{2}\). If both are zero, the behavior is implementation-defined.

- **Units**: The output of `atan2` is in radians. If degrees are required, a conversion must be performed by multiplying the result by \(\frac{180}{\pi}\).

## One Line Summary
The `atan2` function in C computes the arc tangent of two variables, providing the angle in radians while considering the signs of both inputs to determine the correct quadrant.