# Ex16 Check for Balanced Parentheses Using Stack
## DATE:
## AIM:
To write a Java program that verifies whether the parentheses (brackets) in an input string are balanced — meaning each opening bracket (, {, [ has a corresponding and correctly ordered closing bracket ), }, ].

## Algorithm
1. Start the program.
2. Read the input string containing brackets.
3. Push every opening bracket into a stack.
4. For each closing bracket, check whether it matches the top opening bracket.
5. If all brackets match and the stack is empty, display "Balanced"; otherwise display "Not Balanced".

## Program:
```
/*
Program to verify whether the parentheses in an input string are balanced.
Developed by: HEMALISHA T
RegisterNumber: 212225040123
*/

import java.util.*;

class BalancedParentheses {

    public static void main(String[] args) {

        Scanner sc = new Scanner(System.in);

        Stack<Character> stack = new Stack<>();

        System.out.print("Enter an expression: ");
        String str = sc.nextLine();

        boolean balanced = true;

        for (char ch : str.toCharArray()) {

            if (ch == '(' || ch == '{' || ch == '[') {
                stack.push(ch);
            }

            else if (ch == ')' || ch == '}' || ch == ']') {

                if (stack.isEmpty()) {
                    balanced = false;
                    break;
                }

                char top = stack.pop();

                if ((ch == ')' && top != '(') ||
                    (ch == '}' && top != '{') ||
                    (ch == ']' && top != '[')) {

                    balanced = false;
                    break;
                }
            }
        }

        if (!stack.isEmpty())
            balanced = false;

        if (balanced)
            System.out.println("Parentheses are Balanced.");
        else
            System.out.println("Parentheses are Not Balanced.");

        sc.close();
    }
}
```

## Output:
![Uploading image.png…]()



## Result:
Thus,the program correctly checks whether an input string has balanced parentheses using a stack.
