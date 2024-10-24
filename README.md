# 3 Java Operators and Expressions    

1. Arithmetic Operators

**Description**: Java provides arithmetic operators like +, -, *, /, and % to perform basic mathematical operations.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        int a = 10;
        int b = 3;

        System.out.println("Addition: " + (a + b));
        System.out.println("Subtraction: " + (a - b));
        System.out.println("Multiplication: " + (a * b));
        System.out.println("Division: " + (a / b));
        System.out.println("Modulus: " + (a % b));
    }
}
```


2. Assignment Operators

**Description:** Assignment operators like =, +=, -=, *=, and /= are used to assign values to variables.

```java

package com.company;

public class Main {
    public static void main(String[] args) {
        int a = 5;
        a += 10;  // Equivalent to a = a + 10;
        System.out.println("Value of a: " + a);
    }
}
```

3. Comparison (Relational) Operators

**Description:** Comparison operators like ==, !=, <, >, <=, and >= are used to compare values.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        int x = 10, y = 20;
        System.out.println("x == y: " + (x == y));
        System.out.println("x != y: " + (x != y));
        System.out.println("x > y: " + (x > y));
        System.out.println("x < y: " + (x < y));
        System.out.println("x >= y: " + (x >= y));
        System.out.println("x <= y: " + (x <= y));
    }
}
```

4. Logical Operators

**Description:** Logical operators like &&, ||, and ! are used to form logical expressions, usually with boolean values.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        boolean condition1 = true;
        boolean condition2 = false;

        System.out.println("AND (&&) Operator: " + (condition1 && condition2));
        System.out.println("OR (||) Operator: " + (condition1 || condition2));
        System.out.println("NOT (!) Operator: " + (!condition1));
    }
}
```

5. Unary Operators

**Description:** Unary operators like +, -, ++, and -- operate on a single operand to modify its value or state.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        int num = 10;

        System.out.println("Initial value: " + num);
        System.out.println("Post-increment: " + num++);
        System.out.println("After post-increment: " + num);
        System.out.println("Pre-decrement: " + --num);
    }
}
```

6. Bitwise Operators

**Description:** Bitwise operators like &, |, ^, and ~ operate on binary representations of numbers.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        int a = 5;  // 0101 in binary
        int b = 3;  // 0011 in binary

        System.out.println("Bitwise AND: " + (a & b));  // 0001 -> 1
        System.out.println("Bitwise OR: " + (a | b));   // 0111 -> 7
        System.out.println("Bitwise XOR: " + (a ^ b));  // 0110 -> 6
        System.out.println("Bitwise Complement: " + (~a));  // 1010 -> -6
    }
}
```

7. Ternary Operator

**Description:** The ternary operator is a shorthand for if-else statements. It takes three operands: a condition, a value if true, and a value if false.  

```jave
package com.company;

public class Main {
    public static void main(String[] args) {
        int a = 10, b = 20;
        String result = (a > b) ? "a is greater" : "b is greater";
        System.out.println(result);
    }
}
```

8. Instanceof Operator

**Description:** The instanceof operator checks whether an object belongs to a specific class or subclass.  

```java
package com.company;

public class Main {
    public static void main(String[] args) {
        String str = "Hello";
        System.out.println("Is str an instance of String? " + (str instanceof String));
    }
}
```

9. Boolean and Boolean Expressions

* Boolean Variable Declaration: The exercise starts with boolean variable initialization to track conditions like isRaining and isWeekend.  

* Boolean Expressions: It demonstrates how to create and use boolean expressions that combine multiple conditions using logical operators (&& for AND, || for OR, and ! for NOT).  


```java
package com.company;

public class BooleanExpressionExample {
    public static void main(String[] args) {
        // 1. Declare boolean variables
        boolean isRaining = false;
        boolean isWeekend = true;

        // 2. Create boolean expressions
        boolean shouldTakeUmbrella = isRaining; // Take umbrella if it's raining
        boolean isFreeToGoOut = !isRaining && isWeekend; // Can go out if not raining and it's the weekend

        // 3. Print the boolean values and expressions
        System.out.println("Is it raining? " + isRaining); // Output: false
        System.out.println("Is it the weekend? " + isWeekend); // Output: true
        System.out.println("Should take an umbrella? " + shouldTakeUmbrella); // Output: false
        System.out.println("Is free to go out? " + isFreeToGoOut); // Output: true

        // 4. Conditional statements using boolean expressions
        if (isFreeToGoOut) {
            System.out.println("You can go out and enjoy your day!");
        } else {
            System.out.println("Stay inside and relax!");
        }

        // 5. More complex boolean expressions
        int temperature = 75; // Current temperature
        boolean isHot = temperature > 80; // Check if it's hot
        boolean isCold = temperature < 60; // Check if it's cold

        // Using logical operators
        if (isHot) {
            System.out.println("It's hot outside!");
        } else if (isCold) {
            System.out.println("It's cold outside!");
        } else {
            System.out.println("The weather is nice!");
        }
    }
}
```

10. Java Math   

```java 
package com.company;

public class MathFunctionsExample {
    public static void main(String[] args) {
        // 1. Absolute value
        double negativeValue = -15.5;
        double absoluteValue = Math.abs(negativeValue);
        System.out.println("Absolute value of " + negativeValue + " is: " + absoluteValue);

        // 2. Maximum and Minimum
        double a = 10.0;
        double b = 20.0;
        System.out.println("Max of " + a + " and " + b + " is: " + Math.max(a, b)); // Max: 20.0
        System.out.println("Min of " + a + " and " + b + " is: " + Math.min(a, b)); // Min: 10.0

        // 3. Square root
        double square = 25.0;
        double sqrtValue = Math.sqrt(square);
        System.out.println("Square root of " + square + " is: " + sqrtValue); // Sqrt: 5.0

        // 4. Power
        double base = 2.0;
        double exponent = 3.0;
        double powerValue = Math.pow(base, exponent);
        System.out.println(base + " raised to the power of " + exponent + " is: " + powerValue); // Power: 8.0

        // 5. Natural logarithm
        double logValue = Math.log(10);
        System.out.println("Natural logarithm of 10 is: " + logValue); // Log: 2.302585092994046

        // 6. Exponential function
        double expValue = Math.exp(1); // e^1
        System.out.println("Exponential of 1 is: " + expValue); // Exp: 2.718281828459045

        // 7. Trigonometric functions
        double angleInDegrees = 45.0;
        double angleInRadians = Math.toRadians(angleInDegrees);
        System.out.println("Sine of " + angleInDegrees + " degrees is: " + Math.sin(angleInRadians)); // Sin: 0.7071067811865475
        System.out.println("Cosine of " + angleInDegrees + " degrees is: " + Math.cos(angleInRadians)); // Cos: 0.7071067811865476
        System.out.println("Tangent of " + angleInDegrees + " degrees is: " + Math.tan(angleInRadians)); // Tan: 1.0

        // 8. Random number
        double randomValue = Math.random();
        System.out.println("Random number between 0 and 1: " + randomValue); // Random: [0.0, 1.0)

        // 9. Convert radians to degrees
        double radians = Math.PI;
        double degrees = Math.toDegrees(radians);
        System.out.println("PI radians in degrees is: " + degrees); // Degrees: 180.0

        // 10. Ceiling and Floor
        double decimalValue = 7.3;
        System.out.println("Ceiling of " + decimalValue + " is: " + Math.ceil(decimalValue)); // Ceiling: 8.0
        System.out.println("Floor of " + decimalValue + " is: " + Math.floor(decimalValue)); // Floor: 7.0
    }
}
```

