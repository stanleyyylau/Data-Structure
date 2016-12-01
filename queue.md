# Queue

Like stacks but it follows the FIFO (First-In First-Out) principle.

## Operations
+ ``enqueue``
+ ``dequeue``

## Implimentation

```
function Queue () {
    collection = [];
    this.print() = function(){
        console.log(collection);
    }
    this.enqueue = function(element) {
        collection.push(element);
    };
    this.dequeue = function() {
        return collection.shift();
    };
    this.front = function() {
        return collection[0];
    };
    this.size = function() {
        return collection.length;
    };
    this.isEmpty = function(){
        return (this.size === 0);
    };
}
```
