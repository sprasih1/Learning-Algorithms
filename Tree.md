
###### Tree Traversal(I found this good:)
(Inorder,Preorder,Postorder)
Time Complexity: O(n)
Let us see different corner cases.
Complexity function T(n) — for all problem where tree traversal is involved — can be defined as:

T(n) = T(k) + T(n – k – 1) + c

Where k is the number of nodes on one side of root and n-k-1 on the other side.
Let’s do an analysis of boundary conditions

Case 1: Skewed tree (One of the subtrees is empty and other subtree is non-empty )

k is 0 in this case.
T(n) = T(0) + T(n-1) + c

T(n) = 2T(0) + T(n-2) + 2c

T(n) = 3T(0) + T(n-3) + 3c

T(n) = 4T(0) + T(n-4) + 4c

…………………………………………
………………………………………….

T(n) = (n-1)T(0) + T(1) + (n-1)c

T(n) = nT(0) + (n)c

Value of T(0) will be some constant say d. (traversing a empty tree will take some constants time)

T(n) = n(c+d)
T(n) = Θ(n) (Theta of n)

Case 2: Both left and right subtrees have equal number of nodes.

T(n) = 2T(|_n/2_|) + c

This recursive function is in the standard form (T(n) = aT(n/b) + (-)(n) ) for master method .
If we solve it by master method we get (-)(n)

Auxiliary Space : If we don’t consider size of stack for function calls then O(1) otherwise O(n).




Link to bridges in a graph
https://algs4.cs.princeton.edu/41graph/Bridge.java.html
