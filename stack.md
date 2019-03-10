# Stack
Stack is a linear data structure which follows a particular order in which the operations are performed.
The order may be LIFO(Last In First Out) or FILO(First In Last Out).
###### push
###### pop
###### peek
###### isEmpty
# Application(Basics)
###### Balanced Paranthesis
Algorithm:
1) Declare a character stack S.
2) Now traverse the expression string exp.
    a) If the current character is a starting bracket (‘(‘ or ‘{‘ or ‘[‘) then push it to stack.
    b) If the current character is a closing bracket (‘)’ or ‘}’ or ‘]’) then pop from stack and if the popped character
    is the matching starting bracket then fine else parenthesis are not balanced.
3) After complete traversal, if there is some starting bracket left in stack then “not balanced”

###### Infix to postfix:(beacuse compiler scans from left to right or right to left ) Algorithm:
1. Scan the infix expression from left to right.
2. If the scanned character is an operand, output it.
3. Else,
…..3.1 If the precedence of the scanned operator is greater than the precedence of the operator in the stack(or the stack
is empty or the stack contains a ‘(‘ ), push it.
…..3.2 Else, Pop all the operators from the stack which are greater than or equal to in precedence than that of the 
scanned operator. After doing that Push the scanned operator to the stack. (If you encounter parenthesis while popping
then stop there and push the scanned operator in the stack.)
4. If the scanned character is an ‘(‘, push it to the stack.
5. If the scanned character is an ‘)’, pop the stack and and output it until a ‘(‘ is encountered, and discard both the parenthesis.
6. Repeat steps 2-6 until infix expression is scanned.
7. Print the output
8. Pop and output from the stack until it is not empty.
###### Tower Of Hanoi

// Assuming n-th disk is  
// bottom disk (count down) 

      
static void tower(int n, char sourcePole, 
                  char destinationPole, char auxiliaryPole) 

{ 
    // Base case (termination condition) 
    if (0 == n) 
    return; 
  
    // Move first n-1 disks from source pole 
    // to auxiliary pole using destination as 
    // temporary pole 
    tower(n - 1, sourcePole, auxiliaryPole, 
                          destinationPole); 
  
    // Move the remaining disk from source 
    // pole to destination pole 
    System.out.printf("Move the disk %d from %c to %c\n", 
                         n, sourcePole, destinationPole); 
  
    // Move the n-1 disks from auxiliary (now source) 
    // pole to destination pole using source pole as 
    // temporary (auxiliary) pole 
    tower(n - 1, auxiliaryPole, destinationPole, sourcePole); 
} 
###### Time complexity
The time complexity of TOH can be calculated by formulating number of moves.

We need to move the first N-1 disks from Source to Auxiliary and from Auxiliary to Destination,
i.e. the first N-1 disks requires two moves. One more move of last disk from Source to Destination.
Mathematically it can be defined recursively.

Mn = 2Mn-1 + 1.

We can easily solve the above recursive relation (2^n-1), which is exponential.
