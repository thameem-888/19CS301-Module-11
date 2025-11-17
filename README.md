# 19CS301-Module-11

EXP.No: 11.1 Singly Linked List (Traversal, Search and Delete)

### AIM: 

To write a function to traverse a linked list and display its elements.


### ALGORITHM:
Step 1: Start

Step 2: Define a Node class with attributes:
   
Step 3: Define a LinkedList class with a head pointer initialized to None

Step 4: Define a method traverse() to print the linked list nodes:
 
Step 5: Stop



### PROGRAM:
```
class Node:
    def __init__(self, data):
       self.data = data
       self.next = None
 
class SinglyLinkedList:
    def __init__(self):
        self.head = None
        self.tail = None
 
#Creating addNode() to add newly created nodes.
    def addNode(self, data):
        if self.tail is None:
            self.head = Node(data)
            self.tail = self.head
        else:
            self.tail.next = Node(data)
            self.tail = self.tail.next

 #Creating display() to print newly created nodes via traversing.
    def display(self):
        current = self.head
        while current is not None:
            print(current.data,end = ' ')
            current = current.next
s = SinglyLinkedList()
n = int(input())
for i in range(n):
    data = input()
    s.addNode(data)
s.display()
```
### OUTPUT:
![image](https://github.com/user-attachments/assets/0d7d0023-6a02-45b6-8f70-f407f1ebb39d)



### RESULT: 

The program successfully traverses and displays the linked list elements in the format: data1 -> data2 -> data3 -> None.

EXP.No: 11.2 Singly Linked List (Insertion and all operation)

### AIM: 

To Insert a new element at the beginning of a singly linked list.

###ALGORITHM:
Step 1: Start

Step 2: Create a Node class with attributes:

Step 3: Create a LinkedList class with a head pointer initialized to None

Step 4: Define a method insert_at_start(data) in the LinkedList class:
   
Step 5: Define a method to traverse and display the linked list nodes to verify the insertion:
  
Step 6: Stop

### PROGRAM:
```
class Node:    
  def __init__(self,data):    
    self.data = data   
    self.next = None   
     
class CreateList:    
  def __init__(self):    
    self.head = None   
     
        
  def addAtStart(self,data): 
      newNode = Node(data)
      if self.head is None:
          newNode.next = self.head
          self.head = newNode
      else:
          temp = self.head;
          newNode.next = temp
          self.head = newNode
     
     
  def display(self):    
    current = self.head    
    if self.head is None:    
      print("List is empty")  
      return
    else:    
        print("Adding nodes to the start of the list: ")   
        print(current.data) 
        while(current.next != None):    
            current = current.next  
            print(current.data)   
        
cl = CreateList()  
      
cl.addAtStart(1)    
cl.display()    
     
cl.addAtStart(2)    
cl.display()    
     
cl.addAtStart(3)    
cl.display()    
      
cl.addAtStart(4)    
cl.display()    
```
###OUTPUT:


![image](https://github.com/user-attachments/assets/6cbc961e-a53a-4f1f-aa25-86bc41fd084a)




###RESULT: 

Thus, the program has been successfully executed.


EX: 11.3 Doubly Linked List (Traversal, Search and Delete)

### AIM: 

To Print elements of a doubly linked list in forward and reverse order.

### ALGORITHM:

Algorithm:
Step 1: Define a Node class with attributes:
 
Step 2: Define a DoublyLinkedList class with a head pointer initialized to None

Step 3: Create a method append(data) to add nodes at the end of the list:
    

Step 4: Create a method print_forward() to print nodes from head to end:
   
Step 5: Create a method print_reverse() to print nodes from end to head:
   



### PROGRAM:


```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
  
class DoublyLinkedList:
    def __init__(self):
        self.head = None
  
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        if self.head is not None:
            self.head.prev = new_node
        self.head = new_node
        
    def append(self, new_data):
        new_node = Node(new_data)
        if self.head is None:
            self.head = new_node
            return
        last = self.head
        while last.next:
            last = last.next
        last.next = new_node
        new_node.prev = last
        return
  
    def printList(self, node):
        print("\nTraversal in forward direction")
        while node:
          
            print(node.data)
            last = node
            node = node.next
        print("\nTraversal in reverse direction")
        while last:
           
            print(last.data)
            last = last.prev
  
llist = DoublyLinkedList()
  
llist.append(6)
llist.push(7)
llist.push(1)
llist.append(4)
print ("Created DLL is: ")
llist.printList(llist.head)
```
### OUTPUT:

![image](https://github.com/user-attachments/assets/b6beaadb-b921-4cf7-9646-bb9483f40ab5)



### RESULT: 

Thus, the program has been successfully executed.

EXP.No: 11.4 Doubly Linked List (Insertion and all operation)


### AIM:

To write a Python program using a doubly linked list to insert words at the beginning and display the sentence in both forward and reverse direction.

###ALGORITHM: 

Step 1: Start

Step 2: Define a Node class with attributes:
   

Step 3: Define a Sentence class with a head pointer initialized to None

Step 4: Define insert_at_start(word) method:
    

Step 5: Define display_forward() method:
  

Step 6: Define display_reverse() method:
    

Step 7: Read number of words and insert them using insert_at_start()

Step 8: Call display_forward() and display_reverse()

Step 9: Stop

###PROGRAM:
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None
        self.prev = None
  
class DoublyLinkedList:
    def __init__(self):
        self.head = None
  
    def push(self, new_data):
        new_node = Node(new_data)
        new_node.next = self.head
        if self.head is not None:
            self.head.prev = new_node
        self.head = new_node
        
    def printList(self, node):
        print("\nTraversal in forward direction")
        while node:
          
            print(node.data, end=" ")
            last = node
            node = node.next
        print("\nTraversal in reverse direction")
        while last:
           
            print(last.data, end=" ")
            last = last.prev
            
llist = DoublyLinkedList()
  
x = int(input("Enter the number of words to display.\n"))
for i in range(x):
    a = input("Enter the data to push\n")
    llist.push(a)

llist.printList(llist.head)
```
### OUTPUT:
 
![image](https://github.com/user-attachments/assets/a4b2989e-d922-4ab7-80b0-e8accff08238)

 

### RESULT: 

Thus, the program has been successfully executed


EXP.No: 11.5    ENCAPSULATION


### AIM:

To write a Python program to insert an element at a specified position in a singly linked list.


###ALGORITHM: 

Step 1: Start

Step 2: Define a Node class with:

Step 3: Define a LinkedList class with:

Step 4: Define insert_at_position(data, position) method:

Step 5: Define a display() method to print list elements

Step 6: Create object, take user input, insert at given position and display list

Step 7: Stop

###PROGRAM:
```
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

class LinkedList:
    def __init__(self):
        self.head = None

    def insert_at_position(self, data, position):
        new_node = Node(data)
        if position == 0:
            new_node.next = self.head
            self.head = new_node
            return
        temp = self.head
        for _ in range(position - 1):
            if temp is None:
                print("Position out of range")
                return
            temp = temp.next
        new_node.next = temp.next
        temp.next = new_node

    def display(self):
        temp = self.head
        print("Linked List:")
        while temp:
            print(temp.data, end=" -> ")
            temp = temp.next
        print("None")

# Example usage
ll = LinkedList()
# Inserting initial nodes
ll.insert_at_position(10, 0)
ll.insert_at_position(20, 1)
ll.insert_at_position(30, 2)
ll.insert_at_position(25, 2)  # Insert 25 at position 2
ll.display()

```
### OUTPUT:
 
![image](https://github.com/user-attachments/assets/26a68510-6313-4773-9bab-1495bd025f90)


### RESULT: 

The program successfully inserts an element at the specified position in a singly linked list and displays the updated list in one line.
