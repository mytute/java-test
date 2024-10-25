# 6 Arrays and Collections Basics     

Arrays are used to store multiple values in a single variable, instead of declaring separate variables for each value.  

To declare an array, define the variable type with square brackets:   

```java  
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
int[] myNum = {10, 20, 30, 40};
```
You can access an array element by referring to the index number.  
```java 
String[] cars = {"Volvo", "BMW", "Ford", "Mazda"};
System.out.println(cars[0]);
// Outputs Volvo
```

1. Summing Elements of a Array.   
**TODO**  

  1. write a program to find the **sum** and **average** of the elements in an array.   

```java 
public class ArraySum {
    public static void main(String[] args) {
        int[] numbers = {5, 10, 15, 20, 25};
        int sum = 0;
        for (int num : numbers) {
            sum += num;
        }
        System.out.println("Sum: " + sum);
        System.out.println("Average: " + (sum / (double) numbers.length));
    }
}
```
  output:  
  ```bash 
    Sum: 75  
    Average: 15.0
  ```

2. finding maximum and minimum values in an Array.    
**TODO**

  1. write a progran to find the **largest** and **samllest** elements in an array.    
  Hint: Use **Math.min()** and **Math.max()** in a loop or compare manully.   

```java 
public class MaxMinInArray {
    public static void main(String[] args) {
        int[] numbers = {34, 7, 23, 32, 5, 62};
        int max = numbers[0];
        int min = numbers[0];

        for (int num : numbers) {
            if (num > max) max = num;
            if (num < min) min = num;
        }

        System.out.println("Maximum: " + max);
        System.out.println("Minimum: " + min);
    }
}
```

  output:    
  ```bash 
    Maximum: 62  
    Minimum: 5
  ```

3. Using **java.util.Arryays** for operations.    
**TODO**

  1. write a program to sort an array and search for an element using **Arrys** class.   

```java 
import java.util.Arrays;

public class ArraysClassExample {
    public static void main(String[] args) {
        int[] numbers = {42, 12, 56, 34, 7};

        // Sorting the array
        Arrays.sort(numbers);
        System.out.println("Sorted Array: " + Arrays.toString(numbers)); // Sorted Array: [7, 12, 34, 42, 56]

        // Searching for an element
        int index = Arrays.binarySearch(numbers, 34);
        if (index >= 0) {
            System.out.println("Element 34 found at index: " + index); // Element 34 found at index: 2
        } else {
            System.out.println("Element not found.");
        }
    }
}
```

4. Copy an Array.    
**TODO**

  1. write a program to **copy elements** from one array to another.    
```java 
import java.util.Arrays;

public class ArrayCopy {
    public static void main(String[] args) {
        int[] original = {1, 2, 3, 4, 5};
        int[] copied = Arrays.copyOf(original, original.length);
        
        copid[1] = 9; // to show not an referring. 

        System.out.println("Original Array: " + Arrays.toString(original)); // Original Array: [1, 2, 3, 4, 5]  
        System.out.println("Copied Array: " + Arrays.toString(copied)); // Copied Array: [1, 9, 3, 4, 5]
    }
}
```

5. Reversing an Array.   
**TODO**

  1. write a program to **reverse** the elements of an array.   

```java 
public class ArrayReverse {
    public static void main(String[] args) {
        int[] numbers = {1, 2, 3, 4, 5};

        System.out.print("Reversed Array: ");
        for (int i = numbers.length - 1; i >= 0; i--) {
            System.out.print(numbers[i] + " ");
        }
    }
}

  // output : Reversed Array: 5 4 3 2 1
```

6. Understanding the Difference Between equals() and deepEquals().   

  **equals():**
    Checks if two arrays are equal in terms of content for 1D arrays.  
    For 2D arrays, it only checks the reference equality of the inner arrays, not their content.  

  **deepEquals():**
    Compares the content of nested arrays recursively, making it suitable for 2D or multidimensional arrays.  

**TODO**

  1. Write a program that creates two 2D arrays with identical content and compares them using both equals() and deepEquals() methods from the java.util.Arrays class. Observe the difference in results.    
  2. make new array from the one of above array and Oberse the result.    

```java 
import java.util.Arrays;

public class EqualsVsDeepEquals {
    public static void main(String[] args) {
        // Case 1: Two different 2D arrays with identical content
        int[][] array1 = {{1, 2}, {3, 4}};
        int[][] array2 = {{1, 2}, {3, 4}};

        // Comparing array1 and array2 using equals() and deepEquals()
        System.out.println("Using equals() for different 2D arrays: " + Arrays.equals(array1, array2));
        // Using equals() for different 2D arrays: false
        System.out.println("Using deepEquals() for different 2D arrays: " + Arrays.deepEquals(array1, array2));
        // Using deepEquals() for different 2D arrays: true

        // Case 2: Making array3 a reference to array1
        int[][] array3 = array1;  // Both variables point to the same array in memory

        // Comparing array1 and array3 using equals() and deepEquals()
        System.out.println("Using equals() for identical references: " + Arrays.equals(array1, array3));
        // Using equals() for identical references: true
        System.out.println("Using deepEquals() for identical references: " + Arrays.deepEquals(array1, array3));
        // Using deepEquals() for identical references: true
    }
}
```

7. Understanding **compare()** and **mismatch()** methods.  

  **compare():**  
    Compares two arrays lexicographically (like comparing words).  
    Returns 0 if arrays are identical, a positive value if the first mismatch in the first array is greater, and a negative value otherwise.  

  **mismatch():**
    Returns the index of the first mismatch between two arrays.  
    If the arrays are identical, it returns -1.  

```java   
import java.util.Arrays;

public class CompareMismatchDemo {
    public static void main(String[] args) {
        // Case 1: Identical arrays
        int[] array1 = {1, 2, 3};
        int[] array2 = {1, 2, 3};

        printComparisonResults(array1, array2); 
        // compare() result: 0
        // mismatch() result: -1

        // Case 2: Arrays with a mismatch at the end
        int[] array3 = {1, 2, 4};

        printComparisonResults(array1, array3);
        // compare() result: -1
        // mismatch() result: 2

        // Case 3: Arrays of different lengths
        int[] array4 = {1, 2};

        printComparisonResults(array1, array4);
        // compare() result: 1
        // mismatch() result: 2
    }

    private static void printComparisonResults(int[] arr1, int[] arr2) {
        
        // Compare the two arrays lexicographically
        int compareResult = Arrays.compare(arr1, arr2);
        System.out.println("compare() result: " + compareResult);

        // Find the first mismatch index
        int mismatchIndex = Arrays.mismatch(arr1, arr2);
        System.out.println("mismatch() result: " + mismatchIndex);
    }
}
```

8. Understanding the Behavior of fill()    

```java 
    // Case 1: Fill entire array with the same value
    int[] array1 = new int[5];
    Arrays.fill(array1, 7);
    System.out.println("Case 1: Fill entire array with 7 -> " + Arrays.toString(array1));
    // Output: [7, 7, 7, 7, 7]

    // Case 2: Fill only part of the array
    int[] array2 = {1, 2, 3, 4, 5};
    Arrays.fill(array2, 1, 4, 9); // Fill from index 1 to 3 (exclusive of 4)
    System.out.println("Case 2: Fill part of array from index 1 to 3 with 9 -> " + Arrays.toString(array2));
    // Output: [1, 9, 9, 9, 5]

    // Case 3: Fill multidimensional array
    int[][] multiArray = new int[2][3];
    for (int[] row : multiArray) {
        Arrays.fill(row, 5);
    }
    System.out.println("Case 3: Fill each row of multidimensional array with 5 -> ");
    print2DArray(multiArray);
    // Output:
    // [5, 5, 5]
    // [5, 5, 5]

    // Case 4: Fill array of strings
    String[] stringArray = new String[4];
    Arrays.fill(stringArray, "Java");
    System.out.println("Case 4: Fill string array with 'Java' -> " + Arrays.toString(stringArray));
    // Output: [Java, Java, Java, Java]

    // Case 5: Attempting to fill with null in a non-primitive array
    String[] names = {"Alice", "Bob", "Charlie"};
    Arrays.fill(names, 1, 3, null); // Replace from index 1 to 2 with null
    System.out.println("Case 5: Replace part of array with null -> " + Arrays.toString(names));
    // Output: [Alice, null, null]
```

9. ArrayList    

```java 
import java.util.ArrayList;
import java.util.Collections;
import java.util.Iterator;

public class ArrayListDemo {
    public static void main(String[] args) {
        // 1. Create an ArrayList of Strings
        ArrayList<String> fruits = new ArrayList<>();
        fruits.add("Apple");
        fruits.add("Banana");
        fruits.add("Orange");
        fruits.add("Mango");
        System.out.println("Initial ArrayList: " + fruits);
        // Output: [Apple, Banana, Orange, Mango]

        // 2. Add an element at a specific index
        fruits.add(2, "Grapes");
        System.out.println("After adding 'Grapes' at index 2: " + fruits);
        // Output: [Apple, Banana, Grapes, Orange, Mango]

        // 3. Add a collection of items to the ArrayList
        ArrayList<String> moreFruits = new ArrayList<>();
        moreFruits.add("Pineapple");
        moreFruits.add("Kiwi");
        fruits.addAll(moreFruits);
        System.out.println("After adding more fruits: " + fruits);
        // Output: [Apple, Banana, Grapes, Orange, Mango, Pineapple, Kiwi]

        // 4. Get an element from a specific index
        String fruitAtIndex3 = fruits.get(3);
        System.out.println("Element at index 3: " + fruitAtIndex3);
        // Output: Orange

        // 5. Update an element at a specific index
        fruits.set(1, "Blueberry");
        System.out.println("After updating index 1 to 'Blueberry': " + fruits);
        // Output: [Apple, Blueberry, Grapes, Orange, Mango, Pineapple, Kiwi]

        // 6. Remove an element by value and by index
        fruits.remove("Grapes");
        System.out.println("After removing 'Grapes': " + fruits);
        // Output: [Apple, Blueberry, Orange, Mango, Pineapple, Kiwi]

        fruits.remove(0);
        System.out.println("After removing element at index 0: " + fruits);
        // Output: [Blueberry, Orange, Mango, Pineapple, Kiwi]

        // 7. Check if the ArrayList contains a specific element
        boolean hasMango = fruits.contains("Mango");
        System.out.println("Does the list contain 'Mango'? " + hasMango);
        // Output: true

        // 8. Get the size of the ArrayList
        int size = fruits.size();
        System.out.println("Size of the ArrayList: " + size);
        // Output: 5

        // 9. Iterate over the ArrayList using a for-each loop
        System.out.println("Iterating using for-each loop:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
        // Output:
        // Blueberry
        // Orange
        // Mango
        // Pineapple
        // Kiwi

        // 10. Iterate over the ArrayList using an Iterator
        System.out.println("Iterating using Iterator:");
        Iterator<String> iterator = fruits.iterator();
        while (iterator.hasNext()) {
            System.out.println(iterator.next());
        }
        // Output:
        // Blueberry
        // Orange
        // Mango
        // Pineapple
        // Kiwi

        // 11. Sort the ArrayList
        Collections.sort(fruits);
        System.out.println("After sorting: " + fruits);
        // Output: [Blueberry, Kiwi, Mango, Orange, Pineapple]

        // 12. Clear the ArrayList
        fruits.clear();
        System.out.println("After clearing the ArrayList: " + fruits);
        // Output: []

        // 13. Check if the ArrayList is empty
        boolean isEmpty = fruits.isEmpty();
        System.out.println("Is the ArrayList empty? " + isEmpty);
        // Output: true

        // 14. Add items back to the list
        fruits.add("Mango");
        fruits.add("Apple");
        fruits.add("Banana");

        // 15. Clone the ArrayList
        ArrayList<String> clonedFruits = (ArrayList<String>) fruits.clone();
        System.out.println("Cloned ArrayList: " + clonedFruits);
        // Output: [Mango, Apple, Banana]

        // 16. Use indexOf() to find the position of an item
        int indexOfBanana = fruits.indexOf("Banana");
        System.out.println("Index of 'Banana': " + indexOfBanana);
        // Output: 2

        // 17. Use lastIndexOf() to find the last occurrence of an item
        fruits.add("Apple"); // Adding Apple again
        int lastIndexOfApple = fruits.lastIndexOf("Apple");
        System.out.println("Last index of 'Apple': " + lastIndexOfApple);
        // Output: 3

        // 18. Use forEach to print all items
        System.out.println("Using forEach to print fruits:");
        fruits.forEach(fruit -> System.out.println(fruit));
        // Output:
        // Mango
        // Apple
        // Banana
        // Apple

        // 19. Ensure capacity of the ArrayList
        fruits.ensureCapacity(10);
        // The ensureCapacity(10) method is called to ensure that the ArrayList can hold at least 10 elements without reallocating memory.
        // It's important to note that this method doesn't change the current size but ensures that enough space is available.
        System.out.println("Capacity ensured for 10 items.");

        // 20. Trim the ArrayList to size
        fruits.trimToSize();
        // After adding several elements, trimToSize() is called to reduce the internal capacity of the ArrayList to match its current size.
        // This helps optimize memory usage by freeing up any unused capacity.
        System.out.println("Trimmed ArrayList to size.");
    }
}
```

10. LinkedList   

```java 
import java.util.LinkedList;

public class LinkedListExample {
    public static void main(String[] args) {
        // 1. Create a LinkedList
        LinkedList<String> fruits = new LinkedList<>();

        // 2. Add elements to the LinkedList
        fruits.add("Apple");       // Add at the end
        fruits.add("Banana");
        fruits.addFirst("Cherry"); // Add to the beginning
        fruits.addLast("Date");    // Add to the end
        System.out.println("LinkedList after additions: " + fruits);
        // Output: LinkedList after additions: [Cherry, Apple, Banana, Date]

        // 3. Check if the LinkedList contains an item
        System.out.println("Does the list contain Banana? " + fruits.contains("Banana")); 
        // Output: Does the list contain Banana? true

        // 4. Get the first and last items
        System.out.println("First fruit: " + fruits.getFirst()); // Cherry
        System.out.println("Last fruit: " + fruits.getLast());   // Date

        // 5. Remove the first and last items
        fruits.removeFirst(); // Removes Cherry
        fruits.removeLast();  // Removes Date
        System.out.println("LinkedList after removing first and last: " + fruits);
        // Output: LinkedList after removing first and last: [Apple, Banana]

        // 6. Check size of the LinkedList
        System.out.println("Size of LinkedList: " + fruits.size());
        // Output: Size of LinkedList: 2

        // 7. Iterate over the LinkedList
        System.out.println("Iterating through the LinkedList:");
        for (String fruit : fruits) {
            System.out.println(fruit);
        }
        // Output: Apple
        //         Banana

        // 8. Add a collection of items to the LinkedList
        LinkedList<String> moreFruits = new LinkedList<>();
        moreFruits.add("Elderberry");
        moreFruits.add("Fig");
        fruits.addAll(moreFruits);
        System.out.println("LinkedList after adding more fruits: " + fruits);
        // Output: LinkedList after adding more fruits: [Apple, Banana, Elderberry, Fig]

        // 9. Clear the LinkedList
        fruits.clear();
        System.out.println("LinkedList after clearing: " + fruits);
        // Output: LinkedList after clearing: []

        // 10. Check if the LinkedList is empty
        System.out.println("Is the LinkedList empty? " + fruits.isEmpty());
        // Output: Is the LinkedList empty? true
    }
}
```

11. HashMap  

A HashMap in Java stores data in the form of key-value pairs, making it easy to access values using keys. Unlike lists, which require numerical indexes, HashMap keys can be of any object type, like a String.   

``` 
import java.util.HashMap;
import java.util.Set;
import java.util.Collection;

public class HashMapExample {
    public static void main(String[] args) {
        // 1. Create a HashMap
        HashMap<String, Integer> scores = new HashMap<>();

        // 2. Add elements using put()
        scores.put("Alice", 90);
        scores.put("Bob", 85);
        scores.put("Charlie", 88);
        System.out.println("Initial HashMap: " + scores);
        // Output: {Alice=90, Bob=85, Charlie=88}

        // 3. Get a value by key using get()
        System.out.println("Alice's score: " + scores.get("Alice"));
        // Output: Alice's score: 90

        // 4. Remove an entry using remove()
        scores.remove("Bob");
        System.out.println("After removing Bob: " + scores);
        // Output: {Alice=90, Charlie=88}

        // 5. Get the size of the HashMap using size()
        System.out.println("Size of HashMap: " + scores.size());
        // Output: Size of HashMap: 2

        // 6. Get all keys using keySet()
        Set<String> keys = scores.keySet();
        System.out.println("Keys: " + keys);
        // Output: Keys: [Alice, Charlie]

        // 7. Get all values using values()
        Collection<Integer> values = scores.values();
        System.out.println("Values: " + values);
        // Output: Values: [90, 88]

        // 8. Check if a key exists using containsKey()
        System.out.println("Is Alice present? " + scores.containsKey("Alice"));
        // Output: Is Alice present? true

        // 9. Clear all entries using clear()
        scores.clear();
        System.out.println("HashMap after clear: " + scores);
        // Output: HashMap after clear: {}

        // 10. Check if the HashMap is empty using isEmpty()
        System.out.println("Is HashMap empty? " + scores.isEmpty());
        // Output: Is HashMap empty? true
    }
}
```

12. Jave HashSet.   

A HashSet in Java is a collection that stores unique elements, meaning it does not allow duplicates.   

```java 
import java.util.HashSet;

public class HashSetExample {
    public static void main(String[] args) {
        // 1. Create a HashSet
        HashSet<String> names = new HashSet<>();

        // 2. Add elements using add()
        names.add("Alice");
        names.add("Bob");
        names.add("Charlie");
        System.out.println("Initial HashSet: " + names);
        // Output: [Alice, Bob, Charlie] (Order may vary)

        // 3. Add a duplicate element (ignored)
        names.add("Alice");
        System.out.println("After adding duplicate: " + names);
        // Output: [Alice, Bob, Charlie] (No duplicate added)

        // 4. Check if an element exists using contains()
        System.out.println("Is Bob in the set? " + names.contains("Bob"));
        // Output: Is Bob in the set? true

        // 5. Remove an element using remove()
        names.remove("Charlie");
        System.out.println("After removing Charlie: " + names);
        // Output: [Alice, Bob]

        // 6. Get the size of the HashSet using size()
        System.out.println("Size of HashSet: " + names.size());
        // Output: Size of HashSet: 2

        // 7. Iterate over elements using forEach()
        System.out.print("HashSet elements: ");
        names.forEach(name -> System.out.print(name + " "));
        // Output: Alice Bob (Order may vary)

        // 8. Remove all elements using clear()
        names.clear();
        System.out.println("\nHashSet after clear: " + names);
        // Output: HashSet after clear: []

        // 9. Check if the HashSet is empty using isEmpty()
        System.out.println("Is HashSet empty? " + names.isEmpty());
        // Output: Is HashSet empty? true
    }
}
```

13. Conslusion    


1. Java Arrays(Use when the size of your collection is fixed or when you need to store primitive data types efficiently.)   

Pros:  

    **Fast access:** O(1) time for accessing elements by index.  
    **Memory-efficient:** Stores data in contiguous memory locations, especially for primitives.  
    **Simple to use:** Ideal for fixed-size collections where you know the number of elements in advance.  

Cons:  

   **Fixed size:** The size cannot be changed once declared.  
   **Manual resizing:** If the array needs to grow, you must create a new array and copy elements manually.  
   **No advanced features:** Lacks built-in methods for operations like searching or sorting.  

2. Java ArrayList(Use when you need a dynamically resizable array to store a sequence of elements.)   

Pros:  

   **Dynamic resizing:** Automatically grows or shrinks as elements are added or removed.  
   **Random access:** Provides O(1) access to elements by index, just like arrays.  
   **Built-in methods:** Supports methods like add(), remove(), and contains() for easier operations.  

Cons:  

   **Performance degradation:** Adding elements in the middle or removing them can be slow (O(n)) due to shifting elements.  
   **Not synchronized:** It is not thread-safe unless explicitly synchronized, which could lead to concurrency issues.  

3. Java LinkedList(Use when you need frequent insertions and deletions at both ends or in the middle of the list.)    

Pros:  

   **Efficient insertion/deletion:** O(1) insertion or deletion at both ends or in the middle.  
   **Doubly linked:** Can traverse both forwards and backwards.  
   **Useful for queues:** Works well for queue-like operations where elements are frequently added and removed.

Cons:  

   **Slower access:** O(n) time to access elements, since traversal is required.  
   **More memory:** Uses extra memory for storing node pointers (next and previous references).  

4. Java HashMap(Use when you need to map keys to values for quick lookups.)   

Pros:  

   **Fast lookups:** O(1) time complexity for getting and putting elements by key.  
   **Flexible key types:** Can use any non-null object as a key.  
   **No duplicate keys:** Ensures each key maps to a unique value.  

Cons:  

   **No ordering:** Does not maintain insertion or natural order of keys.  
   **Thread safety:** Not synchronized, so needs external synchronization for concurrent use.  
   **Handling collisions:** Poor hash function choice can degrade performance.  

5. Java HashSet(Use when you need to store unique elements without any duplicates.)     

Pros:  

   **Unique elements:** Automatically removes duplicates.  
   **Fast operations:** O(1) average time complexity for add(), remove(), and contains().  
   **Efficient for lookups:** Ideal for situations requiring frequent membership checks.  

Cons:  

   **No ordering: Elements are not stored in any specific order.  
   **No duplicate values: If duplicates are needed, use other collections (like List).  
   **Thread safety: Not synchronized, so needs external synchronization for concurrent usage.  


