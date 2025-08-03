<!--
Meta Description: # Understanding the `cos` Function in C: Calculate the Cosine of an Angle ## Synopsis The `cos` function in C is a mathematical function that computes...
Meta Keywords: cos, function, radians, angle, double
-->

# Understanding the `cos` Function in C: Calculate the Cosine of an Angle

## Synopsis
The `cos` function in C is a mathematical function that computes the cosine of a given angle (in radians). It is part of the C standard library and is commonly used in various applications, including scientific computations, graphics programming, and engineering simulations.

## Documentation
### Purpose
The `cos` function is used to return the cosine of an angle specified in radians. It is defined in the `<math.h>` header file and is crucial for performing trigonometric calculations in C.

### Usage
To utilize the `cos` function, include the `<math.h>` header at the beginning of your C program. The function has the following signature:

```c
double cos(double x);
```

- **Parameters**: 
  - `x`: The angle in radians for which the cosine value is to be computed.

- **Returns**: 
  - The function returns the cosine of `x` as a double-precision floating-point number.

### Example Code
Here are some basic usage examples of the `cos` function:

```c
#include <stdio.h>
#include <math.h>

int main() {
    double angle1 = 0.0;     // Angle in radians
    double angle2 = M_PI / 3; // 60 degrees in radians
    double angle3 = M_PI;    // 180 degrees in radians

    printf("cos(%f) = %f\n", angle1, cos(angle1));  // Output: 1.000000
    printf("cos(%f) = %f\n", angle2, cos(angle2));  // Output: 0.500000
    printf("cos(%f) = %f\n", angle3, cos(angle3));  // Output: -1.000000

    return 0;
}
```

## Explanation
When using the `cos` function, it is essential to ensure that the angle is provided in radians, as providing an angle in degrees will yield incorrect results. To convert degrees to radians, use the formula:

```c
radians = degrees * (M_PI / 180);
```

### Common Pitfalls
1. **Unit Confusion**: Remember that the `cos` function expects the angle in radians. Mixing radians and degrees can lead to unexpected results.
2. **Including the Header File**: Ensure that you include `<math.h>` at the top of your program, or the compiler will not recognize the `cos` function.
3. **Compilation Issues**: When using math functions, you might need to link the math library explicitly during compilation. Use the `-lm` flag with `gcc`:

   ```bash
   gcc -o my_program my_program.c -lm
   ```

4. **Precision**: The result of the `cos` function is a double. Be mindful of floating-point precision issues when comparing results.

## One Line Summary
The `cos` function in C computes the cosine of an angle specified in radians, essential for various mathematical and engineering applications.