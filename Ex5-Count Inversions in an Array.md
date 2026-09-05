# Ex5 Count Inversions in an Array
## DATE:
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

<img width="711" height="560" alt="image" src="https://github.com/user-attachments/assets/7cdbeb56-0c02-491b-84d2-698b1054de68" />


## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.
