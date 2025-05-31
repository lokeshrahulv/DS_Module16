# EX.NO : 4(D) B+ Tree
## DATE:
## AIM:
To write a C function to traverse the elements in a B+ Tree.

## Algorithm
1. Start 
2. Iterate through each element in the node's data array. 
3. If the node is not a leaf, recursively call traverse on the current child pointer. 
4. Print the current data element. 
5. After the loop, if the node is not a leaf, traverse the last child pointer. 
6. Return after completing the traversal. 
7. End 

## Program:
```
/*
Program to traverse the elements in a B+ Tree.
Developed by: ASHWIN KUMAR S
RegisterNumber: 212222240013
*/
```
```c
/*
struct B_TreeNode
{
  int*data;
  structB_TreeNode**child_ptr; int leaf;
  int n;
};
struct B_TreeNode*root =NULL, *np=NULL, *x =NULL;
*/

voidtraverse(struct B_TreeNode*p)
{
  int i;
  for(i=0;i<p->n;i++)
  {
    if(p->leaf==0)
    {
      traverse(p->child_ptr[i]);
    }
    printf("%d",p->data[i]);
  }
  if(p->leaf==0)
  {
    traverse(p->child_ptr[i]);
  }
}
```
## Output:

![Screenshot 2025-04-25 195257](https://github.com/user-attachments/assets/c90fc149-727e-40b7-ab34-c067ba92f34c)


## Result:
Thus, the function to traverse the elements in a B+ Tree is implemented successfully.
