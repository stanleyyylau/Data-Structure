# Learning about stacks
Just think about a stack of books on your table, you have to follow the ``Last-In-First-Out`` principle.

## Operations
+ ``pop()`` remove item from the top of the stack
+ ``push()`` put new item on the top of the stack

## Implimentation

```
function Stack() {
    collection = [];
    this.print = function() {
        console.log(collection)
    }
    this.push = function(element) {
        collection.push(element);
    };
    this.pop = function() {
        return collection.pop();
    };
    this.peek = function() {
        return collection[collection.length - 1];
    };
    this.isEmpty = function() {
        return (collection.length === 0);
    };
    this.clear = function(){
        collection = [];
    };
}
```
