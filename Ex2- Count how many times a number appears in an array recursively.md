# Ex2 Count how many times a number appears in an array recursively.
## DATE:
## AIM:
To write a Java program to Count how many times a number appears in an array recursively.

## Algorithm
1. Start the program and initialize an array, a target number, and a counter variable.
2. Define a recursive function that accepts the array, target number, and the current tracking index as parameters.
3. Check the base case: If the current index is equal to the length of the array, return 0 to stop recursion.
4. Perform the recursive step: If the element at the current index matches the target, return 1 plus the result of the recursive call for the next index; otherwise, return 0 plus the result for the next index.
5. Print the final count returned by the function and Stop the execution.

## Program:
```
/*
Program Count how many times a number appears in an array recursively.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;

public class ArrayOccurrenceCounter {
    
    // Recursive function to count occurrences of a number in an array
    public static int countOccurrences(int[] arr, int target, int index) {
        // Base case: if index reaches the end of the array, return 0
        if (index == arr.length) {
            return 0;
        }
        
        // Check if the current element matches the target value
        int match = (arr[index] == target) ? 1 : 0;
        
        // Recursive call moving to the next index
        return match + countOccurrences(arr, target, index + 1);
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        
        // 1. Get the size of the array from the user
        System.out.print("Enter the number of elements in the array: ");
        int size = scanner.nextInt();
        
        int[] array = new int[size];
        
        // 2. Get the array elements from the user
        System.out.println("Enter " + size + " integers:");
        for (int i = 0; i < size; i++) {
            System.out.print("Element " + (i + 1) + ": ");
            array[i] = scanner.nextInt();
        }
        
        // 3. Get the target number to search for
        System.out.print("Enter the target number to count: ");
        int targetNumber = scanner.nextInt();
        
        // 4. Invoke the recursive method starting from index 0
        int count = countOccurrences(array, targetNumber, 0);
        
        // 5. Display the output
        System.out.println("\nThe number " + targetNumber + " appears " + count + " times in the array.");
        
        scanner.close();
    }
}

```

## Output:

<img width="782" height="437" alt="image" src="https://github.com/user-attachments/assets/be8ec27d-dbb4-486f-a414-7417b33ca94b" />


## Result:
Thus, the Java program to Count how many times a number appears in an array recursively is implemented successfully.
