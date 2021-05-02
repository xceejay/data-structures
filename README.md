# Data Structures Concepts

## Amoako Joel Kofi Amoako

## 219IT01090003

Data Structures Concepts Implemented in Java

- You must have Java installed on your system
- To run the files compile them first eg: javac Queues.java and then run java Queues.java to run the file
- PS - Switch the branch to master to view files

## Singly Linked List

Singly linked list can be defined as the collection of ordered set of elements. The number of elements may vary according to need of the program. A node in the singly linked list consist of two parts: data part and link part. Data part of the node stores actual information that is to be represented by the node while the link part of the node stores the address of its immediate successor.

One way chain or singly linked list can be traversed only in one direction. In other words, we can say that each node contains only next pointer, therefore we can not traverse the list in the reverse direction.

#### How to add node

```
  //addNode() will add a new node to the list
    public void addNode(int data) {
        //Create a new node
        Node newNode = new Node(data);

        //Checks if the list is empty
        if(head == null) {
            //If list is empty, both head and tail will point to new node
            head = newNode;
            tail = newNode;
        }
        else {
            //newNode will be added after tail such that tail's next will point to newNode
            tail.next = newNode;
            //newNode will become new tail of the list
            tail = newNode;
        }
    }
```

#### How to display node

```
 //display() will display all the nodes present in the list
  public void display() {
      //Node current will point to head
      Node current = head;

      if(head == null) {
          System.out.println("List is empty");
          return;
      }
      System.out.println("Nodes of singly linked list: ");
      while(current != null) {
          //Prints each node by incrementing pointer
          System.out.print(current.data + " ");
          current = current.next;
      }
      System.out.println();
  }
```

---

## Doubly Linked List

Doubly linked list is a type of linked list in which each node apart from storing its data has two links. The first link points to the previous node in the list and the second link points to the next node in the list. The first node of the list has its previous link pointing to NULL similarly the last node of the list has its next node pointing to NULL.
The two links help us to traverse the list in both backward and forward direction. But storing an extra link requires some extra space.

#### How to add node

```
  //addNode() will add a node to the list
    public void addNode(int data) {
        //Create a new node
        Node newNode = new Node(data);

        //If list is empty
        if(head == null) {
            //Both head and tail will point to newNode
            head = tail = newNode;
            //head's previous will point to null
            head.previous = null;
            //tail's next will point to null, as it is the last node of the list
            tail.next = null;
        }
        else {
            //newNode will be added after tail such that tail's next will point to newNode
            tail.next = newNode;
            //newNode's previous will point to tail
            newNode.previous = tail;
            //newNode will become new tail
            tail = newNode;
            //As it is last node, tail's next will point to null
            tail.next = null;
        }
    }
```

#### How to display node

```
 //display() will print out the nodes of the list
    public void display() {
        //Node current will point to head
        Node current = head;
        if(head == null) {
            System.out.println("List is empty");
            return;
        }
        System.out.println("Nodes of doubly linked list: ");
        while(current != null) {
            //Prints each node by incrementing the pointer.

            System.out.print(current.data + " ");
            current = current.next;
        }
    }

```

---

## Stacks

A stack is an Abstract Data Type (ADT), commonly used in most programming languages. It is named stack as it behaves like a real-world stack, for example – a deck of cards or a pile of plates, etc.A real-world stack allows operations at one end only. For example, we can place or remove a card or plate from the top of the stack only. Likewise, Stack ADT allows all data operations at one end only. At any given time, we can only access the top element of a stack.

This feature makes it LIFO data structure. LIFO stands for Last-in-first-out. Here, the element which is placed (inserted or added) last, is accessed first. In stack terminology, insertion operation is called PUSH operation and removal operation is called POP operation.

#### How to push

```
 public void push(int pushedElement) {
        if (!isFull()) {
            top++;
            arr[top] = pushedElement;
            System.out.println("Pushed element:" + pushedElement);
        } else {
            System.out.println("Stack is full !");
        }
    }

```

#### How to pop

```
  public int pop() {
        if (!isEmpty()) {
            int returnedTop = top;
            top--;
            System.out.println("Popped element :" + arr[returnedTop]);
            return arr[returnedTop];

        } else {
            System.out.println("Stack is empty !");
            return -1;
        }
    }
```

#### How to Peek

```
  public int peek() {
      if(!this.isEmpty())
                      return arr[top];
              else
              {
                      System.out.println("Stack is Empty");
                      return -1;
              }
  }
```

---

## Queues

A Queue is a linear structure which follows a particular order in which the operations are performed. The order is First In First Out (FIFO). A good example of a queue is any queue of consumers for a resource where the consumer that came first is served first. The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added.

#### How to enQueue

```{
 // insert elements to the queue
 void enQueue(int element) {

   // if queue is full
   if (isFull()) {
     System.out.println("Queue is full");
   }
   else {
     if (front == -1) {
       // mark front denote first element of queue
       front = 0;
     }

     rear++;
     // insert element at the rear
     items[rear] = element;
     System.out.println("Insert " + element);
   }
 }
```

#### How to deQueue

```// delete element from the queue
 int deQueue() {
   int element;

   // if queue is empty
   if (isEmpty()) {
     System.out.println("Queue is empty");
     return (-1);
   }
   else {
     // remove element from the front of queue
     element = items[front];

     // if the queue has only one element
     if (front >= rear) {
       front = -1;
       rear = -1;
     }
     else {
       // mark next element as the front
       front++;
     }
     System.out.println( element + " Deleted");
     return (element);
   }
 }
```

#### How to display element of queue

```
 // display element of the queue
  void display() {
    int i;
    if (isEmpty()) {
      System.out.println("Empty Queue");
    }
    else {
      // display the front of the queue
      System.out.println("\nFront index-> " + front);

      // display element of the queue
      System.out.println("Items -> ");
      for (i = front; i <= rear; i++)
        System.out.print(items[i] + "  ");

      // display the rear of the queue
      System.out.println("\nRear index-> " + rear);
    }
  }
```
