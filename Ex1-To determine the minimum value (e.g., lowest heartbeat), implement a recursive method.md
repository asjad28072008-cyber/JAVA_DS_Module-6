# EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
## DATE:
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

<img width="708" height="542" alt="image" src="https://github.com/user-attachments/assets/b6bc27a0-daea-460e-990e-cd4992cbe2f3" />




## Result:
Thus the JAVA prograM ti find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully
