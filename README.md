# 5 Loop and Iteration    

1. basic While loop    

**TODO**  
  1. print numberss from 1 to 10 using a while loop.   

```java 
public class BasicWhileLoop {
    public static void main(String[] args) {
        int i = 1; // Initialization
        while (i <= 10) { // Condition check
            System.out.println(i);
            i++; // Increment
        }
    }
}
```

2. do-while loop   

**TODO**  
  1. write code that program asks for a password until the user enters the correct one ("java123").   

```java 
import java.util.Scanner;

public class PasswordCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String password;

        do {
            System.out.print("Enter the password: ");
            password = scanner.nextLine();
        } while (!password.equals("java123"));

        System.out.println("Access granted!");
        scanner.close();
    }
}
```

3. use **break** and **continue** with while loop.   

**TODO**    
  1. write program to print number from 1 to 10 but skip the number 5 using **continue**.    
  2. stop the loop when the number is 8 using **break**.  

```java 
public class BreakContinueExample {
    public static void main(String[] args) {
        int i = 1;

        while (i <= 10) {
            if (i == 5) {
                i++;
                continue; // Skip this iteration
            }
            if (i == 8) {
                break; // Exit the loop
            }
            System.out.println(i);
            i++;
        }
    }
}
```

result :   
```bash 
1  
2  
3  
4  
6  
7
```

4. basic **for** loop.   

**TODO**  
  1. write program to print numbers from 1 to 10 **for** loop.   

```java  
public class BasicForLoop {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            System.out.println(i);
        }
    }
}
```

5. Enhanced **for** loop (forEach).   


**TODO**  
  1. write program to print all elelments in an array using a for-each loop.    

```java 
public class ForEachExample {
    public static void main(String[] args) {
        int[] numbers = {10, 20, 30, 40, 50};

        for (int num : numbers) {
            System.out.println(num);
        }
    }
}
```

6. nested **for** loop.   

**TODO**  
  1. create a multiplication table (1 to 5) using a nested **for** loop.       

```java 
public class MultiplicationTable {
    public static void main(String[] args) {
        for (int i = 1; i <= 5; i++) {
            for (int j = 1; j <= 5; j++) {
                System.out.print(i * j + "\t");
            }
            System.out.println();
        }
    }
}
```

output :   
```bash 
1   2   3   4   5  
2   4   6   8   10  
3   6   9   12  15  
4   8   12  16  20  
5   10  15  20  25  
```

7. infinite **for** loop.   

**TODO**  
  1. craete an infinite loop that prints "Running..." continuously.    

```java 
public class InfiniteLoop {
    public static void main(String[] args) {
        for (;;) {
            System.out.println("Running...");
        }
    }
}
```

8. for loop with **break** and **continue** in for loop.   

**TODO**  
  1. write a program to print numbers from 1 to 10, but skip the number 5 using ***continue** and stop to loop if the number is 8 using **break**.    

```java 
public class BreakContinueExample {
    public static void main(String[] args) {
        for (int i = 1; i <= 10; i++) {
            if (i == 5) {
                continue; // Skip this iteration
            }
            if (i == 8) {
                break; // Exit the loop
            }
            System.out.println(i);
        }
    }
}
```

9. Reverse **for** loop.   

**TODO**  
  1. write a program to print numbers from 10 to 1 using a reverse **for** loop.    

```java 
public class ReverseForLoop {
    public static void main(String[] args) {
        for (int i = 10; i >= 1; i--) {
            System.out.println(i);
        }
    }
}
```

10. Loop multiple variables.   

**TODO**  
  1. write a program using a **for** loop with multiple variables, printing the sum of two counters in each iteration.   

```java 
public class MultipleVariablesLoop {
    public static void main(String[] args) {
        for (int i = 1, j = 10; i <= 5; i++, j--) {
            System.out.println("i: " + i + ", j: " + j + ", Sum: " + (i + j));
        }
    }
}
```

  output:  
  ```bash 
    i: 1, j: 10, Sum: 11  
    i: 2, j: 9, Sum: 11  
    i: 3, j: 8, Sum: 11  
    i: 4, j: 7, Sum: 11  
    i: 5, j: 6, Sum: 11
  ```
