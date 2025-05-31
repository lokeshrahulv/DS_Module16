# DS_Module16
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
Program to insert the elements in an AVL Tree
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
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
# EX.NO : 4(B) AVL Tree – Rotation
## DATE:
## AIM:
To write a C function to perform right rotation in an AVL Tree.

## Algorithm
1. Start 
2. Set y to the left child of x. 
3. Set the left child of x to be the right child of y. 
4. Set the right child of y to be x. 
5. Update the height of x and y. 
6. Return y as the new root after rotation. 
7. End  

## Program:
```
Program to perform right rotation in AVL Tree
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
/*
typedefstruct node
{
  int data;
  struct node*left,*right; int ht;
}node;
node *insert(node*,int);
//node*Delete(node*,int);
void preorder(node*);
//void inorder(node*);
int height( node *);
node*rotateright(node*);
node*rotateleft(node*);
node *RR(node *);
node *LL(node *);
node *LR(node *);
node*RL(node*);
*/
node * rotateright(node *x)
{
  node *y; y=x->left;
  x->left=y->right; y->right=x;
  x->ht=height(x); y->ht=height(y); return(y);
}
```
## Output:
![image](https://github.com/user-attachments/assets/d260c260-c664-48fa-b021-1217e2392df2)



## Result:
Thus, the function to perform right rotation in an AVL Tree is implemented successfully.
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
Program to write a C function to delete an element in a B Tree
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
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
Program to traverse the elements in a B+ Tree.
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
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
# EX.NO : 4(E) AVL Tree - Deletion
## DATE:
## AIM:
To write a C function to delete an element from an AVL Tree.
## Algorithm
1. Search for the node to delete starting from the root. 
2. Delete the node using standard BST rules. 
3. Update the height of the affected nodes. 
4. Calculate the balance factor of each updated node. 
5. Perform rotations if the node is unbalanced. 
6. Continue until the tree is balanced again.    

## Program:
```
Program to find and display the priority of the operator in the given Postfix expression
Developed by: LOKESH RAHUL V V
RegisterNumber: 212222100024
```
```
node * Delete(node *T,int x)
{
  node *p;
  if(T==NULL)
  {
    return NULL;
  }
  else if(x > T->data) // insert in right subtree
  {
    T->right=Delete(T->right,x);
    if(BF(T)==2)
    {
      if(BF(T->left)>=0)
        T=LL(T);
      else
        T=LR(T);
    }
  }
  else if(x<T->data)
  {
    T->left=Delete(T->left,x);
    if(BF(T)==-2) //Rebalance during windup
    {
      if(BF(T->right)<=0)
        T=RR(T);
      else
        T=RL(T);
    }
  }
  else
  {
  //data to be deleted is found
    if(T->right!=NULL)
    {
      //delete its inorder succesor p=T->right;
      while(p->left!= NULL)
      p=p->left;
      T->data=p->data;
      T->right=Delete(T->right,p->data);
      if(BF(T)==2) //Rebalance during windup
      {
        if(BF(T->left)>=0)
          T=LL(T);
        else
          T=LR(T);
      }
    }
    else
      return(T->left);
  }
  T->ht=height(T); return(T);
}
```
## Output:
![Screenshot 2025-04-25 195845](https://github.com/user-attachments/assets/d8e2d944-ed11-44f9-b301-d01cba4c1543)


## Result:
Thus, the C program to delete an element from an AVL Tree is implemented successfully.
