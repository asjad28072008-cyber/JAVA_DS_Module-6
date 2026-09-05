# EX3 Write a program to count the number of digits in an integer.
## DATE:
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

<img width="832" height="485" alt="image" src="https://github.com/user-attachments/assets/13f3b8cf-9ee6-4bbb-8f8f-29adeec2ef12" />


## Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.
