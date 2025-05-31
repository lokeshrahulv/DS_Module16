# EX.NO : 4(A) AVL Tree - Insertion
## DATE:
## AIM:
To write a C function to insert the elements in an AVL Tree.

## Algorithm
1. Start 
2. If the node is NULL, create a new node with value x. 
3. Insert x recursively into the left or right subtree based on comparison. 
4. Calculate the balance factor (BF) after insertion. 
5. If BF is -2 or 2, perform appropriate rotations (RR, RL, LL, or LR). 
6. Update the height of the current node. 
7. Return the new root after insertion and balancing.. 
8. End   

## Program:
```
/*
Program to insert the elements in an AVL Tree
Developed by: ASHWIN KUMAR S
RegisterNumber: 212222240013
*/
```
```c
node * insert(node *T,int x) 
{ 
  if(T==NULL) 
  { 
    T=(node*)malloc(sizeof(node)); 
    T->data=x; 
    T->left=NULL; 
    T->right=NULL; 
  } 
  else if(x > T->data) 
  { 
    T->right=insert(T->right,x); 
    if(BF(T)==-2) 
    { 
      if(x>T->right->data) 
        T=RR(T); 
      else 
        T=RL(T); 
    } 
  } 
  else if(x < T->data) 
  {
    T->left=insert(T->left,x); 
    if(BF(T)==2) 
    { 
      if(x < T->left->data) 
        T=LL(T); 
      else 
        T=LR(T); 
    } 
  } 
  T->ht=height(T); 
  return(T); 
}  
```
## Output:

![image](https://github.com/user-attachments/assets/e7c41de7-53a0-4fd0-8d94-86eb723cbc11)




## Result:
Thus, the function to insert the elements in an AVL Tree is implemented successfully in C programming language.
