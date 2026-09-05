# Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
## DATE:
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

<img width="902" height="627" alt="image" src="https://github.com/user-attachments/assets/718a9781-c5a1-42e8-bb12-7aa39c22b55c" />


<img width="795" height="637" alt="image" src="https://github.com/user-attachments/assets/6bbc0322-3d85-40ae-9883-6bd254973668" />


## Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.
