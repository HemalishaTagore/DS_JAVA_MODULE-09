# Ex17 Reversing a String Using Stack Data Structure
## DATE: 27/08/2026
## AIM:
To write a Java program that reverses an input string using a stack, without using built-in reverse functions.

## Algorithm
 1. Start the program.
2. Read the input string from the user.
3. Push each character of the string into a stack.
4. Pop each character from the stack and form the reversed string.
5. Display the reversed string and stop the program.

## Program:
```
/*
Program to reverse an input string using a stack.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.*;

class ReverseStringStack {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        Stack<Character> stack = new Stack<>();

        System.out.print("Enter a string: ");
        String str = sc.nextLine();

        for (int i = 0; i < str.length(); i++) {
            stack.push(str.charAt(i));
        }

        System.out.print("Reversed string: ");

        while (!stack.isEmpty()) {
            System.out.print(stack.pop());
        }

        sc.close();
    }
}
```

## Output:

<img width="381" height="285" alt="image" src="https://github.com/user-attachments/assets/c1d6d664-b32d-45cc-a2b8-fa4e777a0b75" />


## Result:
Thus, the program successfully reverses the given string using a stack without relying on built-in reverse functions.
