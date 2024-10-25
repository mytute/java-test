# 7 Java String and String Manipulation     

```java 
public class StringMethodsExercise {
    public static void main(String[] args) {
        // 1. String Initialization
        String str = "Hello Java World!";
        String anotherStr = "java";

        // 2. Length of String
        System.out.println("Length of str: " + str.length()); // Expected Output: Length of str: 17

        // 3. Character at a specific index
        System.out.println("Character at index 1: " + str.charAt(1)); // Expected Output: Character at index 1: e

        // 4. Unicode of character at a position
        System.out.println("Unicode at index 1: " + str.codePointAt(1)); // Expected Output: Unicode at index 1: 101

        // 5. Compare two strings (case-sensitive and case-insensitive)
        System.out.println("Compare with 'java': " + str.compareTo(anotherStr)); // Expected Output: Compare with 'java': -32
        System.out.println("Compare ignoring case: " + str.compareToIgnoreCase(anotherStr)); // Expected Output: Compare ignoring case: 0

        // 6. Check if string contains a sequence
        System.out.println("Contains 'Java': " + str.contains("Java")); // Expected Output: Contains 'Java': true

        // 7. Concatenating strings
        String combined = str.concat(" Let's code!");
        System.out.println("Concatenated String: " + combined); // Expected Output: Concatenated String: Hello Java World! Let's code!

        // 8. Check if a string starts or ends with specific characters
        System.out.println("Starts with 'Hello': " + str.startsWith("Hello")); // Expected Output: Starts with 'Hello': true
        System.out.println("Ends with 'World!': " + str.endsWith("World!")); // Expected Output: Ends with 'World!': true

        // 9. Find the first and last index of a character
        System.out.println("First index of 'a': " + str.indexOf('a')); // Expected Output: First index of 'a': 7
        System.out.println("Last index of 'a': " + str.lastIndexOf('a')); // Expected Output: Last index of 'a': 11

        // 10. Check if the string is empty
        String emptyStr = "";
        System.out.println("Is emptyStr empty? " + emptyStr.isEmpty()); // Expected Output: Is emptyStr empty? true

        // 11. Substring from a string
        System.out.println("Substring (6, 10): " + str.substring(6, 10)); // Expected Output: Substring (6, 10): Java

        // 12. Convert to upper and lower case
        System.out.println("To Upper Case: " + str.toUpperCase()); // Expected Output: To Upper Case: HELLO JAVA WORLD!
        System.out.println("To Lower Case: " + str.toLowerCase()); // Expected Output: To Lower Case: hello java world!

        // 13. Replace characters and trim spaces
        String spacedStr = "  Hello  ";
        System.out.println("Trimmed String: '" + spacedStr.trim() + "'"); // Expected Output: Trimmed String: 'Hello'
        System.out.println("Replace 'Java' with 'Kotlin': " + str.replace("Java", "Kotlin")); // Expected Output: Replace 'Java' with 'Kotlin': Hello Kotlin World!

        // 14. Format a string
        System.out.println(String.format("Pi is approximately %.2f", Math.PI)); // Expected Output: Pi is approximately 3.14

        // 15. Convert string to byte array and char array
        byte[] byteArray = str.getBytes();
        char[] charArray = str.toCharArray();
        System.out.println("Byte array: " + java.util.Arrays.toString(byteArray)); // Expected Output: Byte array: [72, 101, 108, 108, 111, 32, 74, 97, 118, 97, 32, 87, 111, 114, 108, 100, 33]
        System.out.println("Char array: " + java.util.Arrays.toString(charArray)); // Expected Output: Char array: [H, e, l, l, o,  , J, a, v, a,  , W, o, r, l, d, !]


    }

}
```


2. Reverse string in java. (in four way)   

```java 

public class ReverseString {
    public static void main(String[] args) {

        // using StringBuilder /////////////////////////////////////////////// 
        String original = "Hello, World!";
        String reversed1 = new StringBuilder(original).reverse().toString();
        System.out.println("Reversed string: " + reversed1);
        
        // using a loop ////////////////////////////////////////////////////// 
        String reversed2 = "";
        
        for (int i = original.length() - 1; i >= 0; i--) {
            reversed2 += original.charAt(i);
        }
        System.out.println("Reversed string: " + reversed2);
        
        // using recursion /////////////////////////////////////////////////
        private static String reverse(String str) {
            if (str.isEmpty()) {
                return str;
            }
            return reverse(str.substring(1)) + str.charAt(0);
        }
        String reversed3 = reverse(original);
        System.out.println("Reversed string: " + reversed3);


        // using streams (java 8 and above) /////////////////////////////// 
        String reversed = original.chars()
                                  .mapToObj(c -> (char) c)
                                  .collect(Collectors.toCollection(StringBuilder::new))
                                  .reverse()
                                  .toString();
        System.out.println("Reversed string: " + reversed);
    }
}

```

3. Convert string to array. (in four way)   

```java 
public class StringToArray {
    public static void main(String[] args) {
        String original = "Hello, World!";
        
        // Method 1: Using String.split() ////////////////////////////////////
        String[] splitArray = original.split(", "); // Splitting by ", "
        // Log output: ["Hello", "World!"]
        
        // Print each element in splitArray //////////////////////////////////
        for (String element : splitArray) {
            System.out.println(element); // Output: Hello\nWorld!
        }

        // Method 2: Using String.toCharArray() ///////////////////////////////
        char[] charArray = original.toCharArray();
        // Log output: ['H', 'e', 'l', 'l', 'o', ',', ' ', 'W', 'o', 'r', 'l', 'd', '!']
        
        // Print each character in charArray
        for (char ch : charArray) {
            System.out.println(ch); // Output: H\ne\nl\nl\no\n,\n \nW\no\nr\nl\nd\n!
        }

        // Method 3: Using String.getBytes() //////////////////////////////////
        byte[] byteArray = original.getBytes();
        // Log output: [72, 101, 108, 108, 111, 44, 32, 87, 111, 114, 108, 100, 33]
        
        // Print each byte in byteArray
        for (byte b : byteArray) {
            System.out.println(b); // Output: 72\n101\n108\n108\n111\n44\n32\n87\n111\n114\n108\n100\n33
        }

        // Method 4: Using a Loop /////////////////////////////////////////////
        String[] loopArray = new String[original.length()];
        for (int i = 0; i < original.length(); i++) {
            loopArray[i] = String.valueOf(original.charAt(i)); // Convert each char to String
        }
        // Log output: ["H", "e", "l", "l", "o", ",", " ", "W", "o", "r", "l", "d", "!"]
        
        // Print each element in loopArray
        for (String element : loopArray) {
            System.out.println(element); // Output: H\ne\nl\nl\no\n,\n \nW\no\nr\nl\nd\n!
        }
    }
}
```


