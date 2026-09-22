# EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
## DATE: 16.08.2026
## AIM:
To write a JAVA program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.

## Algorithm
1. Define a recursive method that takes the sensor readings array and its current size n as inputs.
2. Set the base case: If the size n is equal to 1, return the first element of the array (arr[0]), as it is the only value remaining.
3. Perform the recursive step: Call the method again with a reduced size n - 1 to find the minimum value among the rest of the elements.
4. Compare values: Compare the current element at the index n - 1 with the minimum value returned from the recursive call.
5. Return the smaller value back to the previous function call until the entire array is evaluated.


## Program:
```
/*
Program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
Developed by: MUHAMMAD ASJAD E
RegisterNumber: 212225240091  
*/
```

```
import java.util.Scanner;

public class HealthMonitor {

    // 1. Recursive method taking the array and current size 'n'
    public static int findMin(int[] arr, int n) {
        // 2. Base case: If size n is 1, return the first element
        if (n == 1) {
            return arr[0];
        }

        // 3. Recursive step: Call with a reduced size (n - 1)
        int minOfRest = findMin(arr, n - 1);

        // 4. Compare current element at index (n - 1) with minimum returned
        // 5. Return the smaller value
        if (arr[n - 1] < minOfRest) {
            return arr[n - 1];
        } else {
            return minOfRest;
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("Enter the number of sensor readings: ");
        int n = scanner.nextInt();

        if (n <= 0) {
            System.out.println("Please enter a valid size greater than 0.");
            return;
        }

        int[] readings = new int[n];
        System.out.println("Enter the " + n + " sensor readings (e.g. heartbeats):");
        for (int i = 0; i < n; i++) {
            readings[i] = scanner.nextInt();
        }

        // Execute the recursive calculation
        int minReading = findMin(readings, n);

        System.out.println("\n--- Result ---");
        System.out.println("The lowest heartbeat value is: " + minReading);
        
        scanner.close();
    }
}



```


## Output:

<img width="665" height="371" alt="image" src="https://github.com/user-attachments/assets/6d9c488e-4e02-4241-bc3b-a086470b4acb" />




## Result:
Thus the JAVA prograM ti find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully










# Ex2 Count how many times a number appears in an array recursively.
## DATE: 16.08.2026
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

<img width="1066" height="622" alt="image" src="https://github.com/user-attachments/assets/6bb55b6b-c842-475d-90fa-734723b27f5f" />



## Result:
Thus, the Java program to Count how many times a number appears in an array recursively is implemented successfully.












# EX3 Write a program to count the number of digits in an integer.
## DATE: 16.08.2026
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm

1.Start the program and input the number of disks (\(n\)).
2.Call the recursive function towerOfHanoi(n, source, auxiliary, destination).
3.Check Base Case: If \(n = 1\), move the disk directly from source to destination and return.
4.Perform Recursive Moves:Move top \(n-1\) disks from source to auxiliary using destination.Move the remaining largest disk from source to destination.Move the \(n-1\) disks from auxiliary to destination using source.
5.Stop the execution once all recursive calls are complete.

## Program:
```
/*
Program to to count the number of digits in an integer
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
#include <stdio.h>

// Recursive function to solve Tower of Hanoi
void towerOfHanoi(int n, char from_rod, char aux_rod, char to_rod) {
    // Base case: Only 1 disk to move
    if (n == 1) {
        printf("Move disk 1 from rod %c to rod %c\n", from_rod, to_rod);
        return;
    }
    
    // Move top n-1 disks from source to auxiliary rod
    towerOfHanoi(n - 1, from_rod, to_rod, aux_rod);
    
    // Move the remaining disk from source to destination rod
    printf("Move disk %d from rod %c to rod %c\n", n, from_rod, to_rod);
    
    // Move the n-1 disks from auxiliary to destination rod
    towerOfHanoi(n - 1, aux_rod, from_rod, to_rod);
}

int main() {
    int n;

    printf("Enter the number of disks: ");
    scanf("%d", &n);

    printf("The sequence of moves involved in the Tower of Hanoi are:\n");
    // 'A' = Source, 'B' = Auxiliary, 'C' = Destination
    towerOfHanoi(n, 'A', 'B', 'C'); 
    
    return 0;
}

```

## Output:

<img width="851" height="340" alt="image" src="https://github.com/user-attachments/assets/68529cc3-c538-4ba4-9300-0aff5795294a" />



## Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.
















# Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
## DATE: 16.08.2026
## AIM:
To write a java function to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix.

## Algorithm
1. Start and accept two matrices, Matrix A and Matrix B, along with their row and column dimensions.
2. Verify dimensions and conditions: Ensure both matrices have identical dimensions.
3. Iterate through Matrix A to confirm all elements are odd, and through Matrix B to confirm all elements are even.
4. Perform matrix addition: Loop through each row and column index, adding the corresponding elements (\(C[i][j] = A[i][j] + B[i][j]\)) to generate the resulting matrix.
5. Determine nature and End: Identify that all elements in the resulting matrix are odd, display the result, and terminate the program.


## Program:
```
/*
Program to ind the nature of resultant matrrix.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```

import java.util.Scanner;

public class MatrixAdditionInput {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // 1. Get matrix dimensions from the user
        System.out.print("Enter the number of rows: ");
        int rows = scanner.nextInt();
        System.out.print("Enter the number of columns: ");
        int cols = scanner.nextInt();

        int[][] matrixA = new int[rows][cols];
        int[][] matrixB = new int[rows][cols];
        int[][] resultMatrix = new int[rows][cols];

        boolean allAOdd = true;
        boolean allBEven = true;

        // 2. Input and validate Matrix A
        System.out.println("Enter elements for Matrix A:");
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.printf("Element A[%d][%d]: ", i, j);
                matrixA[i][j] = scanner.nextInt();
                
                // Track if any element is even
                if (matrixA[i][j] % 2 == 0) {
                    allAOdd = false;
                }
            }
        }

        // 3. Input and validate Matrix B
        System.out.println("Enter elements for Matrix B:");
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.printf("Element B[%d][%d]: ", i, j);
                matrixB[i][j] = scanner.nextInt();
                
                // Track if any element is odd
                if (matrixB[i][j] % 2 != 0) {
                    allBEven = false;
                }
            }
        }

        // 4. Perform Addition
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                resultMatrix[i][j] = matrixA[i][j] + matrixB[i][j];
            }
        }

        // 5. Display Evaluation Output
        System.out.println("\n--- Results Evaluation ---");
        System.out.println("Matrix A has all odd numbers? -> " + allAOdd);
        System.out.println("Matrix B has all even numbers? -> " + allBEven);

        if (allAOdd && allBEven) {
            System.out.println("Nature of the resulting matrix: All ODD numbers");
        } else {
            System.out.println("Nature of the resulting matrix: MIXED numbers (Preconditions were not met)");
        }

        // 6. Display Result Matrix
        System.out.println("\nResultant Matrix:");
        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                System.out.print(resultMatrix[i][j] + "\t");
            }
            System.out.println();
        }

        scanner.close();
    }
}

```
## Output:

<img width="497" height="691" alt="image" src="https://github.com/user-attachments/assets/4bcdf5e3-4c30-4954-ade5-f38d2676d2d9" />


<img width="795" height="637" alt="image" src="https://github.com/user-attachments/assets/6bbc0322-3d85-40ae-9883-6bd254973668" />


## Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.



















# Ex5 Count Inversions in an Array
## DATE: 16.08.2026
## AIM:
To write a Java program  to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
1. Divide: Find the midpoint of the array to split it into two halves: a left subarray and a right subarray.
2. Conquer Left: Recursively count the inversions in the left subarray and sort it.
3. Conquer Right: Recursively count the inversions in the right subarray and sort it.
4. Merge and Count Split: Merge the two sorted halves while counting split inversions. If an element in the left half is greater than an element in the right half (arr[i] > arr[j]), then all remaining elements in the left half from index i form inversions with arr[j].
5. Sum Total: Add the inversion counts from the left half, right half, and the merge phase to return the total number of inversions.

## Program:
```
/*
Program toto Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```

import java.util.Arrays;
import java.util.Scanner;

public class InversionCounter {

    // Function to merge two sorted halves and count split inversions
    private static long mergeAndCount(int[] arr, int l, int m, int r) {
        int[] left = Arrays.copyOfRange(arr, l, m + 1);
        int[] right = Arrays.copyOfRange(arr, m + 1, r + 1);

        int i = 0, j = 0, k = l;
        long swaps = 0;

        while (i < left.length && j < right.length) {
            if (left[i] <= right[j]) {
                arr[k++] = left[i++];
            } else {
                arr[k++] = right[j++];
                // Core logic: all remaining elements in the left array form an inversion
                swaps += (left.length - i);
            }
        }

        while (i < left.length) {
            arr[k++] = left[i++];
        }
        while (j < right.length) {
            arr[k++] = right[j++];
        }

        return swaps;
    }

    // Recursive function that implements Merge Sort and counts inversions
    private static long mergeSortAndCount(int[] arr, int l, int r) {
        long count = 0;
        if (l < r) {
            int m = l + (r - l) / 2;

            count += mergeSortAndCount(arr, l, m);
            count += mergeSortAndCount(arr, m + 1, r);
            count += mergeAndCount(arr, l, m, r);
        }
        return count;
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Get the size of the array from the user
        System.out.print("Enter the number of elements in the array: ");
        int n = scanner.nextInt();

        int[] arr = new int[n];

        // Get array elements from the user
        System.out.println("Enter " + n + " integers:");
        for (int i = 0; i < n; i++) {
            arr[i] = scanner.nextInt();
        }

        System.out.println("\nOriginal Array: " + Arrays.toString(arr));
        
        // Calculate inversions
        long inversionCount = mergeSortAndCount(arr, 0, arr.length - 1);
        
        System.out.println("Number of Inversions: " + inversionCount);

        scanner.close();
    }
}

```

## Output:

<img width="527" height="387" alt="image" src="https://github.com/user-attachments/assets/7c29b345-43a6-4219-8d4c-cb8b027470b4" />


## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.
