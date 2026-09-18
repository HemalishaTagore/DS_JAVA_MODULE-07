# Ex9 Finding the Longest Length of Nested Set in a Permutation Array
## DATE:
## AIM:
To write a program that finds the length of the longest set s[k] defined as s[k] = { nums[k], nums[nums[k]], nums[nums[nums[k]]], … },where the iteration stops before a duplicate element occurs.

The task is to return the maximum size among all such sets.
## Algorithm
1. Start the program.
2. Read the permutation array.
3. For each index, follow the elements using nums[k] until a duplicate element occurs.
4. Count the number of elements visited and find the maximum count.
5. Display the longest nested set length and stop the program.

## Program:
```
/*
Program to find the Longest Length of Nested Set in a Permutation Array
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.Scanner;

class LongestNestedSet {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();

        int nums[] = new int[n];

        System.out.println("Enter permutation elements:");
        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        int maxLength = 0;

        for (int i = 0; i < n; i++) {

            boolean visited[] = new boolean[n];
            int current = i;
            int length = 0;

            while (!visited[current]) {
                visited[current] = true;
                length++;
                current = nums[current];
            }

            if (length > maxLength)
                maxLength = length;
        }

        System.out.println("Longest nested set length: " + maxLength);

        sc.close();
    }
}
```

## Output:
<img width="277" height="230" alt="image" src="https://github.com/user-attachments/assets/13e4f1ef-4ffc-41fe-8781-57bb2402a5e7" />



## Result:
The program successfully computes the longest length of the nested set s[k] for the given permutation array.
