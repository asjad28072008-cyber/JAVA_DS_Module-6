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
public class HealthMonitor {

    // Recursive method to find the minimum value in an array
    public static int findMinimum(int[] arr, int n) {
        // Base case: if the array has only one element, return it
        if (n == 1) {
            return arr[0];
        }
        
        // Recursive call to find the minimum in the first n-1 elements
        int minOfRest = findMinimum(arr, n - 1);
        
        // Return the smaller value between the current element and the minimum of the rest
        if (arr[n - 1] < minOfRest) {
            return arr[n - 1];
        } else {
            return minOfRest;
        }
    }

    public static void main(String[] args) {
        // Sample heartbeat sensor readings
        int[] heartbeatReadings = {72, 68, 85, 58, 90, 64};
        
        System.out.println("Analyzing sensor data...");
        
        // Execute the recursive method
        int lowestHeartbeat = findMinimum(heartbeatReadings, heartbeatReadings.length);
        
        // Print the result
        System.out.println("Lowest heartbeat recorded: " + lowestHeartbeat + " bpm");
    }
}

```


## Output:

<img width="695" height="207" alt="image" src="https://github.com/user-attachments/assets/c3b71606-ae60-4d20-a9e7-c9124acadded" />


## Result:
Thus the JAVA prograM ti find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully
