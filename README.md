# 4 Control Flow Statements    

1. Java Conditions and If Statements  

* Use **if** to specify a block of code to be executed, if a specified condition is true.  
* Use **else** to specify a block of code to be executed, if the same condition is false.    
* Use **else** if to specify a new condition to test, if the first condition is false.  

**TODO**
  1. define correct UserName and Password.  
  2. match the user entered UserName and Password.  
  3. log the output of result.    

```java
import java.util.Scanner;

public class SimpleLogin {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String correctUsername = "user";
        String correctPassword = "password";

        System.out.print("Enter username: ");
        String username = scanner.nextLine();
        System.out.print("Enter password: ");
        String password = scanner.nextLine();

        // Check if the credentials are correct
        if (username.equals(correctUsername) && password.equals(correctPassword)) {
            System.out.println("Login successful!");
        } else {
            System.out.println("Invalid username or password.");
        }
        scanner.close();
    }
}
```



2. Java Conditions and If-elseIf Statements  

**TODO**
  1. Input the score you got.  
  2. wirte if-elseif for log the Grade you got according to score (A,B,C,D,F)  


```java
import java.util.Scanner;

public class GradeEvaluator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your score (0-100): ");
        int score = scanner.nextInt();

        // Determine the grade
        if (score >= 90) {
            System.out.println("Grade: A");
        } else if (score >= 80) {
            System.out.println("Grade: B");
        } else if (score >= 70) {
            System.out.println("Grade: C");
        } else if (score >= 60) {
            System.out.println("Grade: D");
        } else {
            System.out.println("Grade: F");
        }
        scanner.close();
    }
}
```

3. Jave Switch Statements.   


**TODO**
 1. improve above Grade output exmple with **Switch** Statements.   
 2. ince the score ranges are grouped (90-100 for 'A', 80-89 for 'B', etc.), dividing the score by 10 gives an integer between 0 and 10. This makes it easier to use in a switch statement.   
 3. Case 10 and 9 are grouped since both correspond to the grade 'A'. This ensures that even a perfect score of 100 is correctly handled.   
 4. The default case is used to catch scores below 60, which corresponds to the grade 'F'.  
 
 ```java 
import java.util.Scanner;

public class GradeEvaluator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter your score (0-100): ");
        int score = scanner.nextInt();

        // Determine the grade using switch
        switch (score / 10) {
            case 10: // For scores 100
            case 9:
                System.out.println("Grade: A");
                break;
            case 8:
                System.out.println("Grade: B");
                break;
            case 7:
                System.out.println("Grade: C");
                break;
            case 6:
                System.out.println("Grade: D");
                break;
            default:
                System.out.println("Grade: F");
        }
        scanner.close();
    }
}

 ```
