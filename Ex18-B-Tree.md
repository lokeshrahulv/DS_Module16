# EX.NO : 4(C) B-Tree
## DATE:
## AIM:
To write a C function to delete an element in a B Tree.
## Algorithm
1. Start 
2. Try to delete the item from the node using delValFromNode. If not found, print "Not present" and return. 
3. If the node's count is 0 after deletion, set tmp to the current node and update myNode to its first linker child. 
4. Free the tmp node. 
5. Update the global root to the new myNode. 
6. Return after deletion. 
7. End  

## Program:
```
/*
Program to write a C function to delete an element in a B Tree
Developed by: ASHWIN KUMAR S
RegisterNumber: 212222240013
*/
```
```c
struct BTreeNode
{
  int item[MAX+1], count;
  struct BTreeNode*linker[MAX+1];
};

struct BTreeNode*root;*/
voiddelete(int item, struct BTreeNode*myNode)
{
  struct BTreeNode*tmp;
  if(!delValFromNode(item, myNode))
  {
    printf("Not present\n");
    return;
  }
  else
  {
    if(myNode->count ==0)
    {
      tmp = myNode;
      myNode=myNode->linker[0];
      free(tmp);
    }
  }
  root=myNode; return;
}
```
## Output:
![Screenshot 2025-04-25 195018](https://github.com/user-attachments/assets/14f30831-a873-4723-b4d9-6eeeb8206fe0)



## Result:
Thus, the C function to delete an element in a B Tree is implemented successfully.
