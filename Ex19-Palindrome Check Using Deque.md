# Ex19 Palindrome Check Using Deque
## DATE:
## AIM:
To design a program that checks whether a given message is a palindrome by removing all non-alphanumeric characters, converting all characters to lowercase, and using a deque data structure for comparison.

## Algorithm

1. Start the program.
2. Read the message and remove all non-alphanumeric characters.
3. Convert the message into lowercase and insert each character into a deque.
4. Remove and compare characters from the front and rear of the deque.
5. If all characters match, display "Palindrome"; otherwise display "Not Palindrome".
## Program:
```
/*
Program to check whether a given message is a palindrome using Deque.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.*;

class PalindromeDeque {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        Deque<Character> deque = new ArrayDeque<>();

        System.out.print("Enter a message: ");
        String str = sc.nextLine();

        for (char ch : str.toCharArray()) {
            if (Character.isLetterOrDigit(ch)) {
                deque.addLast(Character.toLowerCase(ch));
            }
        }

        boolean palindrome = true;

        while (deque.size() > 1) {
            if (!deque.removeFirst().equals(deque.removeLast())) {
                palindrome = false;
                break;
            }
        }

        if (palindrome)
            System.out.println("The message is a Palindrome.");
        else
            System.out.println("The message is Not a Palindrome.");

        sc.close();
    }
}
```

## Output:
![Uploading image.png…]()



## Result:
The program successfully removes all non-alphanumeric characters, converts the text to lowercase, and uses a deque to efficiently compare characters from both ends. Hence, it determines whether the string is a palindrome.
