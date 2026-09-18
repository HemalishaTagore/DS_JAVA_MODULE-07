# Ex7 Removal of Nodes with a Specific Value from a Linked List
## DATE:
## AIM:
To write a java  program that removes all nodes from a linked list whose value matches a given integer (val) and returns the new head of the modified linked list.

## Algorithm
1. Start the program.
2. Create a singly linked list and insert the elements.
3. Read the value to be removed from the linked list.
4. Traverse the list and remove all nodes whose value matches the given value.
5. Display the modified linked list and stop the program.

## Program:
```
/*
Program to remove all nodes with a specific value from a linked list.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.Scanner;

class RemoveNodes {

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

    static void removeValue(int val) {

        while (head != null && head.data == val) {
            head = head.next;
        }

        Node temp = head;

        while (temp != null && temp.next != null) {
            if (temp.next.data == val) {
                temp.next = temp.next.next;
            } else {
                temp = temp.next;
            }
        }
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

        System.out.print("Enter value to remove: ");
        int val = sc.nextInt();

        removeValue(val);

        System.out.println("Linked list after removal:");
        display();

        sc.close();
    }
}
```

## Output:

<img width="292" height="284" alt="image" src="https://github.com/user-attachments/assets/a76f0620-a414-4dd6-8ea7-5727de642f3b" />


## Result:
The java program successfully removes all nodes with the specified value (val) from the linked list and returns the new head.
