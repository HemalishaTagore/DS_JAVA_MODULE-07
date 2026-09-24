# Ex6 Right Rotation LinkedList
## DATE: 14/08/2026
## AIM:
To write a Java  program to:
Create a singly linked list.
Rotate the linked list to the right by k positions.
Display the rotated linked list.
## Algorithm
1. Start the program.
2. Create a singly linked list and insert the elements.
3. Read the value of k for right rotation.
4. Move the last k nodes to the beginning of the linked list.
5. Display the rotated linked list and stop the program.

## Program:
```
/*
Program to perform Right Rotation on LinkedList
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.Scanner;

class RightRotationLinkedList {

    static class Node {
        int data;
        Node next;

        Node(int data) {
            this.data = data;
            this.next = null;
        }
    }

    static Node head = null;

    static void insert(int data) {
        Node newNode = new Node(data);

        if (head == null) {
            head = newNode;
            return;
        }

        Node temp = head;
        while (temp.next != null) {
            temp = temp.next;
        }

        temp.next = newNode;
    }

    static void rotateRight(int k) {
        if (head == null || head.next == null || k == 0)
            return;

        int length = 1;
        Node temp = head;

        while (temp.next != null) {
            temp = temp.next;
            length++;
        }

        k = k % length;

        if (k == 0)
            return;

        temp.next = head;

        int steps = length - k;
        temp = head;

        for (int i = 1; i < steps; i++) {
            temp = temp.next;
        }

        head = temp.next;
        temp.next = null;
    }

    static void display() {
        Node temp = head;

        while (temp != null) {
            System.out.print(temp.data + " ");
            temp = temp.next;
        }
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of nodes: ");
        int n = sc.nextInt();

        System.out.println("Enter elements:");
        for (int i = 0; i < n; i++) {
            insert(sc.nextInt());
        }

        System.out.print("Enter k: ");
        int k = sc.nextInt();

        rotateRight(k);

        System.out.println("Rotated linked list:");
        display();

        sc.close();
    }
}
```

## Output:

<img width="793" height="196" alt="image" src="https://github.com/user-attachments/assets/d3d898cb-98b4-49f3-bb27-821d6d82808b" />


## Result:
Thus, the C program to perfom right rotation on linked list is implemented successfully.
