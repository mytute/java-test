# 2 Java Variables and Data Types.    

Primitives:

    1. int: Stores integers (whole numbers) without decimals.
    2. double: Stores floating-point numbers (large or small decimals).
    3. float: Stores fractional numbers, smaller precision compared to double.
    4. boolean: Holds true or false values.
    5. char: Stores a single character enclosed in single quotes (e.g., 'A').
    6. byte: 8-bit signed integer, ranges from -128 to 127.
    7. short: 16-bit signed integer, useful for saving memory.
    7. long: 64-bit integer, holds very large numbers.

Reference Types:

    * String: An object that represents a sequence of characters.
    * Arrays and Objects: Complex data structures or custom types.


1. Declare and initialize an integer variable.

**Description:** Integers are widely used to store whole numbers, such as counters or indexes.
**Where to use:** Use int when memory overhead isn’t a concern and when working with whole numbers.
**To Do:** Declare an int variable to store the value 42 and print it.

```java
public class Main {
    public static void main(String[] args) {
        int number = 42;
        System.out.println(number);
    }
}
```

2. Understanding Primitive Data Types    

**Primitive** - for storing simple values. 
**Reference** - for storing complex objects.

**Description**: Java’s primitive data types are the building blocks of data manipulation. There are eight primitive data types: ==int==, ==double==, ==boolean==, ==char==, ==byte==, ==short==, ==long==, and ==float==.
**Where to use:** Use them to store simple values directly in memory, which makes them highly efficient.
**To Do:** Create a variable for each of these types and print their values.

```java
public class DataTypesDemo {
    public static void main(String[] args) {
        int age = 25;
        double salary = 55000.75;
        boolean isActive = true;
        char grade = 'A';
        byte byteValue = 10;
        short shortValue = 500;
        long largeNumber = 10000000000L;
        float pi = 3.14f;

        System.out.println(age + ", " + salary + ", " + isActive + ", " + grade);
        System.out.println(byteValue + ", " + shortValue + ", " + largeNumber + ", " + pi);

        // hole number
        long viewsCount = 3_123_456_789L;
        // (java)not declare as 'int' have to add end"L or l"
        // can divide number using underscore
        System.out.println(viewsCount);

        // number with desimal
        float price = 10.99F;
        // (java)not to declare as 'double' add end"F or f".
        System.out.println(price);

        // define character
        char letter = 'A';
        // use single '' for char. for string  double ""
        System.out.println(letter);

        // define boolean
        boolean isEligible = true;
        // value can be only true or false.
        System.out.println(isEligible);
        
    }
}
```

3. Understanding Java Reference Data Types.    

**description**   
In Java, reference data types store references (addresses) to the actual objects in memory. Common reference data types include arrays, strings, and custom objects like instances of classes. Unlike primitive data types (e.g., int or double), these do not store the actual data directly.

This explores reference data types using:

    Array
    String
    Custom Object

**Todo**  
  1. Create and manipulate an array as a reference data type.  
  2. Use the String class to demonstrate reference behavior.  
  3. Create a custom class and demonstrate how variables hold references to its objects.  
  4. Compare two references to check if they point to the same object.  

```java 
package com.company;

import java.util.Arrays;

public class ReferenceDataTypeExample {

    // 1. Custom class as a reference data type
    static class Person {
        String name;

        Person(String name) {
            this.name = name;
        }
    }

    public static void main(String[] args) {
        // 2. Array as a reference data type
        int[] numbers = {1, 2, 3};
        System.out.println("Original Array: " + Arrays.toString(numbers)); // Output: [1, 2, 3]
        
        // Modify the array through its reference
        numbers[0] = 99;
        System.out.println("Modified Array: " + Arrays.toString(numbers)); // Output: [99, 2, 3]

        // 3. String as a reference data type
        String str1 = new String("Hello");
        String str2 = new String("Hello");

        // Compare two strings using '==' and 'equals()'
        System.out.println("str1 == str2: " + (str1 == str2)); // Output: false (different references)
        System.out.println("str1.equals(str2): " + str1.equals(str2)); // Output: true (same content)

        // 4. Custom object reference behavior
        Person person1 = new Person("Alice");
        Person person2 = person1;  // Both point to the same object in memory

        System.out.println("Person1's name: " + person1.name); // Output: Alice
        System.out.println("Person2's name: " + person2.name); // Output: Alice

        // Modify the name using person2 reference
        person2.name = "Bob";
        System.out.println("Person1's name after modification: " + person1.name); // Output: Bob

        // 5. Compare object references
        System.out.println("person1 == person2: " + (person1 == person2)); // Output: true (same reference)
    }
}
```

4. Another variable type in Class.   

**description**   
    * Instance Variables (class-level variables)  
    * Local Variables (inside methods or blocks)  
    * Static Variables (shared across all instances)  
    * final Variables (constants that cannot be changed after initialization)  

**To Do**  
    1. Create a class with static, instance, and local variables.  
    2. Use the final keyword to declare a constant.  
    3. Print the value of all variables and demonstrate modifying non-final variables.  
    4. Try modifying a final variable to see the compiler error.   

```java 
package com.company;

public class VariableExample {
    // 1. Instance variable (each object gets its own copy)
    int instanceVar = 10;

    // 2. Static variable (shared across all objects of this class)
    static int staticVar = 20;

    // 3. Final variable (constant, cannot be changed)
    final int FINAL_VAR = 100;

    public void demonstrateVariables() {
        // 4. Local variable (only available inside this method)
        int localVar = 30;
        System.out.println("Local Variable: " + localVar); // Output: 30

        // Modify instance and static variables
        instanceVar = 50;
        staticVar = 60;

        System.out.println("Modified Instance Variable: " + instanceVar); // Output: 50
        System.out.println("Modified Static Variable: " + staticVar); // Output: 60

        // Attempting to modify the final variable (Uncomment to see error)
        // FINAL_VAR = 200; // Compilation error: cannot assign a value to final variable
    }

    public static void main(String[] args) {
        // Create an object to access instance variables
        VariableExample example = new VariableExample();

        // Print initial values
        System.out.println("Initial Instance Variable: " + example.instanceVar); // Output: 10
        System.out.println("Initial Static Variable: " + staticVar); // Output: 20
        System.out.println("Final Variable: " + example.FINAL_VAR); // Output: 100

        // Demonstrate usage of variables
        example.demonstrateVariables();
    }
}
```

5. Java Type Casting    

**Overview**
    * Perform implicit (widening) and explicit (narrowing) type conversions.
    * Convert String to int and int to char.
    * Use object casting with instanceof to safely cast.
    * Observe data loss with narrowing conversions.
    * Understand boolean casting limitations.

**To Do**   
  1. Widen an ==int== to ==double==.  
  2. Narrow a ==double== to ==int==.  
  3. Convert a numeric string to an ==int== using ==Integer.parseInt()==.  
  4. Convert an ==int== to ==char==.  
  5. Use ==instanceof== to check an object type and cast it to a ==string==.  
  6. Attempt to cast a ==boolean== to an ==int== and explain the result.  

```java 
package com.company;

public class AllInOneCasting {

    public static void main(String[] args) {
        // 1. Widening (Implicit) Casting: int to double
        int intValue = 42;
        double doubleValue = intValue;
        System.out.println("Widened int to double: " + doubleValue); 
        // Output: Widened int to double: 42.0

        // 2. Narrowing (Explicit) Casting: double to int
        double pi = 3.14159;
        int narrowedValue = (int) pi;  // Fractional part lost
        System.out.println("Narrowed double to int: " + narrowedValue); 
        // Output: Narrowed double to int: 3

        // 3. String to int conversion
        String str = "123";
        int parsedInt = Integer.parseInt(str);
        System.out.println("String to int: " + parsedInt); 
        // Output: String to int: 123

        // 4. int to char conversion (ASCII)
        int charCode = 65;
        char character = (char) charCode;
        System.out.println("int to char: " + character); 
        // Output: int to char: A

        // 5. Safe object casting using instanceof
        Object obj = "Hello, Java!";
        if (obj instanceof String) {
            String castedStr = (String) obj;
            System.out.println("Casted object to String: " + castedStr); 
            // Output: Casted object to String: Hello, Java!
        }

        // 6. Attempting boolean to int casting (Will not compile)
        boolean flag = true;
        // int boolToInt = (int) flag;  // Uncomment to see compilation error
        System.out.println("Note: Boolean cannot be cast to int.");
        // Output: Note: Boolean cannot be cast to int.
    }
}
```

