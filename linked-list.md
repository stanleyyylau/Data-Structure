# linked list

## Nodes in linked list
Another common data structure is the linked list. In a linked list, elements are stored in a node. The node contains two key pieces of information: the element itself, and a reference to the next node.

Imagine that you are in a conga line. You have your hands on the next person in the line, and the person behind you has their hands on you. You can see the person straight ahead of you, but they are blocking the view of the other people ahead in line. A node is just like a person in a conga line, they know who they are and they can only see the next person in line, but they are not aware of the other people ahead or behind them.

## Operations
+ ``element`` itself
+ ``reference`` to the next element
+  ``head`` is the first node of a linked list
+  ``length`` is the length of the linked list

## Implimentation

```
function LinkedList() {
  var length = 0;
  var head = null;

  var Node = function(element){
    this.element = element;
    this.next = null;
  };

  this.size = function(){
    return length;
  };

  this.head = function(){
    return head;
  };

  this.add = function(element){
    // Only change code below this line
    var node = new Node(element);
    if(head === null){
        head = node;
    } else {
        currentNode = head;

        while(currentNode.next){
            currentNode  = currentNode.next;
        }

        currentNode.next = node;
    }

    length++;
    // Only change code above this line
  };
}
```


## Removing elements from a linked list

```
function LinkedList() {
  var length = 0;
  var head = null;

  var Node = function(element){
    this.element = element;
    this.next = null;
  };

  this.length = function(){
    return length;
  };

  this.head = function(){
    return head;
  };

  this.add = function(element){
    var node = new Node(element);
    if(head === null){
        head = node;
    } else {
        currentNode = head;

        while(currentNode.next){
            currentNode  = currentNode.next;
        }

        currentNode.next = node;
    }

    length++;
  };

  this.remove = function(element){
    // Only change code below this line
    var currentNode = head;
    var previousNode;
    if(currentNode.element === element){
        head = currentNode.next;
    } else {
        while(currentNode.element !== element) {
            previousNode = currentNode;
            currentNode = currentNode.next;
        }

        previousNode.next = currentNode.next;
    }

    length --;
    // Only change code above this line
  };
}
```
