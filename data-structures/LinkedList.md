## Linked List
- Linked List is an implementation of List data structure
- Each element is linked to/reference its next element
- In a *singly linked list* we have forward refernce where each element has a reference to its next element
- Linked List is accessed via the very first element in the list called *Head*
- Last element in a Linked List points to null
- Each element in a linked list has a data/element and a pointer/reference to the next element (i.e, A single node in a linked list consists of data and a reference as in the below diagram

![LinkedList](images/linkedlist.png)

- In Java Node is implemented as a Generic class so that it can hold any data type
- The Data should implement comparable for equality checks for example to find the index of a particular element
- Java LinkedList maintains insertion order and implements List and Deque interface

```
public class Node<T extend Comparable<T>> {

  private T data;
  private Node<T> next;
  
  public Node(T data) {
    this.data = data;
    setNext(null);
  }

  public Node<T> getNext() {
    return next;
  }
  
  public void setNext(Node<T> next) {
    this.next = next;
  }
  
  public T getData() {
    return data;
  }
}
```

- For Linked list traversal, we traverse till a null is encountered

![LinkedListTraversal](images/LinkedListTraversal.png)

```
Node<String> current = head;
while(current != null) {
    current = current.getNext();
}
```

### Complexity

Operation | Complexity|
--- | --- | 
add (to end)| O(N) |
add (to start)| O(1) |
contains | O(N) |
delete (first element) | O(1) |
delete (any element) | O(N) |

### Problems

#### Count Nodes
Count the total number of Nodes in a Linked List

```
public int countNodes(Node<T> head) {

  if(head == null) {
    return 0;
  } 
  
  Node<T> current = head;
  int count = 0;
  
  while(current != null) {
    current = current.getNext();
    count++;
    }
    
  return count;
}
```

#### Add a Node
Add a new node to the end of Linked List

```
public void addNode(T data) {

  if(head == null) {
      head = new Node(data);
  }
  Node current = head;
  
  while(current.getNext() != null) {
    current = current.getNext();
  }
  
  current.setNext(new Node(data));
}
```


#### Pop and return first element
Return first element in a list 

```
public T getNode() {

  if(head == null) {
      return null;
  }
  
  T data = head.getData();
  head = head.getNext();
  
  return data;
}
```

## LinkedList vs Array
LinkedList | Array|
--- | --- | 
List Size are unlimited and can grow dynamically | Need to know the size in advance and cannot increase later|
Insertion is easy and just need to know the location pointer | Arrays are located in contigupus memory locations and inorder to insert an element, the elements in the right needs to be moved | 
Deletion is easy and similar to insertion | Array elements needs to be moved in case of deletion as well |
Random access based on index not possible. Need to traverse through the entire list to find the element | Fast lookup for an element in a particular index as they are in contiguous memory locations we know where exactly in memory the lement resides|
Every element requires additional space to store pointer to next element|No extra space required than the ones for the actual elements of the array|
Cannot take advantage of spacial locality(for caching) when accessing the elements (As each element can live anywhere in the memory and can be pointed to) | Arrays takes advantage of spacial locality in cache |
**Used:** <ul><li> When large number of insertions and deletions</li> <li>When we do not know the size of list in advance (dynamic resizing)</li></ul>| **Used:** <ul><li> When we require random access/li><li> When we need faster read operations</li></ul>|
