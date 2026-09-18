# Ex8 Detection of Cycle and Finding the Starting Node in a Linked List
## DATE:
## AIM:
To write a program that detects a cycle in a linked list and returns the node where the cycle begins.
If there is no cycle, the program should return null without modifying the linked list.
## Algorithm

1. Start the program.
2. Create a singly linked list and form a cycle if required.
3. Use slow and fast pointers to detect whether a cycle exists.
4. If a cycle is found, move one pointer to the head and move both pointers one step at a time to find the starting node.
5. Display the starting node of the cycle, or display that no cycle exists.
## Program:
```
/*
Program to detect a cycle and find the starting node in a linked list.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.Scanner;

class CycleDetection {

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

    static Node detectCycle() {

        Node slow = head;
        Node fast = head;

        while (fast != null && fast.next != null) {

            slow = slow.next;
            fast = fast.next.next;

            if (slow == fast) {

                slow = head;

                while (slow != fast) {
                    slow = slow.next;
                    fast = fast.next;
                }

                return slow;
            }
        }

        return null;
    }

    static void createCycle(int position) {

        if (position < 1)
            return;

        Node cycleNode = null;
        Node temp = head;
        int count = 1;

        while (temp.next != null) {

            if (count == position)
                cycleNode = temp;

            temp = temp.next;
            count++;
        }

        if (count == position)
            cycleNode = temp;

        if (cycleNode != null)
            temp.next = cycleNode;
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of nodes: ");
        int n = sc.nextInt();

        System.out.println("Enter elements:");

        for (int i = 0; i < n; i++) {
            insert(sc.nextInt());
        }

        System.out.print("Enter position to create cycle (0 for no cycle): ");
        int position = sc.nextInt();

        createCycle(position);

        Node result = detectCycle();

        if (result != null)
            System.out.println("Cycle starts at node: " + result.data);
        else
            System.out.println("No cycle exists.");

        sc.close();
    }
}
```

## Output:



<img width="448" height="246" alt="image" src="https://github.com/user-attachments/assets/49f84414-f4c8-4dd5-b843-c036ff4b6bc7" />


## Result:
The program successfully detects whether a cycle exists in the linked list.
If a cycle is present, it correctly identifies and returns the node where the cycle begins.
