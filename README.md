
# Prefix Expression Evaluation in Python

## Aim
To evaluate a mathematical expression written in prefix notation using a stack in Python.

## Procedure
1. Define a set of valid operators.
2. Traverse the given prefix expression from right to left.
3. If a character is an operand, convert it to an integer and push it onto the stack.
4. If a character is an operator:
   - Pop two operands from the stack.
   - Perform the operation with the two operands in the correct order.
   - Push the result back onto the stack.
5. After traversing the entire expression, the final result will be on top of the stack.

## Program

```python
OPERATORS = set(['*', '-', '+', '%', '/', '**']) 

def evaluate(expression):
    stack = []
    
    for c in expression[::-1]:  # Read from right to left
        if c not in OPERATORS:
            stack.append(int(c))  # Push operand
        else:
            o1 = stack.pop()
            o2 = stack.pop()

            if c == '+':
                stack.append(o1 + o2)
            elif c == '-':
                stack.append(o1 - o2)
            elif c == '*':
                stack.append(o1 * o2)
            elif c == '/':
                stack.append(o1 / o2)
            elif c == '%':
                stack.append(o1 % o2)
            elif c == '**':
                stack.append(o1 ** o2)
    
    return stack.pop()

# Input and output
test_expression = input()
print("Prefix Expression :", test_expression)
print("Evaluation result :", evaluate(test_expression))
```

## output
![Screenshot 2025-04-20 212924](https://github.com/user-attachments/assets/ea380428-aa63-4953-ace7-6c304218855d)

## Result
The program successfully evaluates a prefix expression using stack operations.
