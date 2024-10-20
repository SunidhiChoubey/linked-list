# linked-list
# Aim- To study and learn about linked list
# Theroy- 
A singly linked list is a widely used linear data structure that represents a dynamic collection of elements where each element, known as a node, is connected to the next one via a pointer or reference. This structure is different from arrays, which store elements contiguously in memory. In contrast, in a singly linked list, the elements (nodes) are distributed across memory locations, and each node dynamically connects to the next through a pointer, allowing flexibility in how memory is utilized. This design enables operations like insertion and deletion to be more efficient in certain scenarios compared to arrays, especially when working with large, unpredictable datasets.

Detailed Components of Singly Linked Lists:
Node: The core element of a singly linked list is the node. Each node contains two fields:

Data: This field holds the actual information or value that the node stores. This could be an integer, a string, a complex object, or any other type of data.
Next Pointer: This is a pointer or reference that holds the memory address of the next node in the sequence. This creates the link between nodes. If the node is the last one in the list, this pointer is set to null (or nullptr in C++) to indicate the end of the list.
The fact that each node points to the next node is what gives the structure its "linked" nature. The pointer connects the nodes sequentially, but as these nodes may be scattered in memory, the list does not need contiguous memory allocation.

Head: The head is the entry point or the starting node of the linked list. It is essentially a pointer or reference that holds the address of the first node in the list. If the linked list is empty, the head is set to null. This is crucial because, without the head, the list cannot be accessed or traversed. All operations on a singly linked list, such as inserting or deleting nodes, begin at the head and proceed through the list from node to node.

The head is responsible for providing a direct reference to the first node. If the head is lost or modified improperly, the entire list may become inaccessible, which is why the head must be handled carefully in any operation.

Characteristics of Singly Linked Lists:
Dynamic Size: One of the major advantages of singly linked lists is that they support dynamic sizing. This means that, unlike arrays, the size of the list is not fixed at the time of creation. Nodes can be added or removed at runtime, allowing the list to grow or shrink as needed. This dynamic nature makes singly linked lists especially useful in situations where the number of elements cannot be predetermined, or the size may fluctuate frequently during program execution.

Efficient Insertions and Deletions: In singly linked lists, insertions and deletions can be performed efficiently, especially at the beginning of the list or at any arbitrary location if a reference to the node is already available. In contrast to arrays, where inserting or deleting an element requires shifting all subsequent elements (which takes linear time), singly linked lists only require adjusting the pointers. This makes these operations faster and more flexible, with the time complexity of insertion and deletion typically being O(1) (constant time) at the head of the list, or O(n) if the position is arbitrary and needs to be searched.

For example, adding a new node at the beginning of the list involves creating a new node, setting its pointer to the current head, and updating the head to point to the new node. Similarly, deleting a node only requires changing the pointer of the previous node to skip the deleted node and point to the next one.

No Reverse Traversals: A limitation of singly linked lists is that they do not support reverse traversal, meaning that you can only move in one direction through the list—from the head to the last node. This is because each node only stores a pointer to the next node, and there is no reference to the previous node. If reverse traversal or bidirectional navigation is required, a different data structure, such as a doubly linked list (where each node points both to the next and the previous node), would be more appropriate.

Because of this limitation, certain operations that require backward navigation, such as reversing a list or accessing a node in reverse order, can be less efficient and more complicated in a singly linked list.
# Code-
~~~
#include <iostream>
using namespace std;

struct node 
{
    int data;     
    node* next;
};

node* createnode(int value) 
{
    node* newnode = new node();  
    newnode->data = value;       
    newnode->next = nullptr; 
    return newnode;
}


void insertdata(node*& head, int value) 
{
    node* newnode = createnode(value);

    if (head == nullptr) 
    {
        head = newnode;
    } 
    
    else 
    {
        node* temp = head;
        while (temp->next != nullptr) 
        {
            temp = temp->next;
        }
        temp->next = newnode;
    }
}

void display(node* head) 
{
    node* temp = head;

    while (temp != nullptr) 
    {
        cout << temp->data << " ";
        temp = temp->next;
    }
}


int main() 
{
    node* head = nullptr;

    insertdata(head, 10);
    insertdata(head, 20);
    insertdata(head, 30);
    insertdata(head, 40);

    cout << "Singly Linked List: ";
    display(head);

    return 0;
}
~~~
# Output-
![](https://github.com/SunidhiChoubey/linked-list/blob/main/Screenshot%202024-10-21%20021047.png)
# Conclusion- 
We learnt about singly linked lists in C++ and learnt the use case of singly linked lists in C++.
