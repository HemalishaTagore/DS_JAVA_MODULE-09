# Ex18 Simulation of a Ticket Counter Using Queue (Linked List Implementation)
## DATE: 27/08/2026
## AIM:
To simulate the functioning of a ticket counter that operates on a First-In-First-Out (FIFO) basis using a queue implemented via a linked list in Java.
## Algorithm
1. Start the program.
2. Create a queue using a linked list with front and rear pointers.
3. Add customers to the rear of the queue.
4. Remove customers from the front of the queue and serve them in FIFO order.
5. Display the queue and served customers, then stop the program.

## Program:
```
/*
Program to simulate a ticket counter using a FIFO queue.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.Scanner;

class TicketQueue {

    static class Node {
        String name;
        Node next;

        Node(String name) {
            this.name = name;
            this.next = null;
        }
    }

    static Node front = null;
    static Node rear = null;

    static void enqueue(String name) {
        Node newNode = new Node(name);

        if (rear == null) {
            front = rear = newNode;
        } else {
            rear.next = newNode;
            rear = newNode;
        }
    }

    static void dequeue() {
        if (front == null) {
            System.out.println("Queue is empty.");
            return;
        }

        System.out.println("Serving customer: " + front.name);
        front = front.next;

        if (front == null)
            rear = null;
    }

    static void display() {
        Node temp = front;

        System.out.println("Customers in queue:");

        while (temp != null) {
            System.out.print(temp.name + " ");
            temp = temp.next;
        }

        System.out.println();
    }

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        System.out.print("Enter number of customers: ");
        int n = sc.nextInt();
        sc.nextLine();

        System.out.println("Enter customer names:");

        for (int i = 0; i < n; i++) {
            enqueue(sc.nextLine());
        }

        display();

        System.out.println("Ticket Counter:");

        while (front != null) {
            dequeue();
        }

        sc.close();
    }
}
```

## Output:

<img width="1104" height="808" alt="image" src="https://github.com/user-attachments/assets/8e5094ff-9cb6-4921-a1dc-12c42fd9adfc" />



## Result:
Thus, the program successfully simulates a ticket counter queue where customers are served in FIFO order using a linked list-based queue implementation.
