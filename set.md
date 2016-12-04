# set

## Operations
+ add
+ size
+ union
+ intersection
+ remove
+ difference
+ subset

## implimentation in ES5
```
function Set() {
    // The var collection will hold the set.
    var collection = [];

    //this.has will return true if there is an existing element. Else it will return false.
    this.has = function(element) {
        return (collection.indexOf(element) !== -1);
    };

    //this.values will return the collection
    this.values = function() {
        return collection;
    };
    //this.add will add an element to the set.
    this.add = function(element) {
        if(!this.has(element)){
            collection.push(element);
            return true;
        }
        return false;
    };

    //this.remove will remove an element from a set
    this.remove = function(element) {
        if(this.has(element)){
            index = collection.indexOf(element);
            collection.splice(index,1);
            return true;
        }
        return false;
    };

    //this.size will return the size of a collection
    this.size = function() {
        return collection.length;
    };

    //this.union will combine 2 sets of data
    this.union = function(otherSet) {
        var unionSet = new Set();

        var firstSet = this.values();
        var secondSet = otherSet.values();

        firstSet.forEach(function(e){
            unionSet.add(e);
        });

        secondSet.forEach(function(e){
            unionSet.add(e);
        });

        return unionSet;
    };

    //this.intersection will return the results were 2 sets are similar
    this.intersection = function(otherSet) {
        var intersectionSet = new Set();

        var firstSet = this.values();

        firstSet.forEach(function(e){
            if(otherSet.has(e)){
                intersectionSet.add(e);
            }
        });

        return intersectionSet;
    };

    //this.difference will return the values from the first set not contained in the second set.
    this.difference = function(otherSet) {
        var differenceSet = new Set();

        var firstSet = this.values();

        firstSet.forEach(function(e){
            if(!otherSet.has(e)){
                differenceSet.add(e);
            }
        });

        return differenceSet;
    };


    //Add your function below this line

    this.subset = function(otherSet) {
        var firstSet = this.values();
        var isSubset = true;

        firstSet.forEach(function(e){
            if(!otherSet.has(e)){
                isSubset = false;
                return;
            }
        });

        return isSubset;
    };


    //Stop adding code
  }

  var setA = new Set();
  var setB = new Set();
  setA.add("a");
  setB.add("b");
  setB.add("c");
  setB.add("a");
  setB.add("d");
  var subSetSetAB = setA.subset(setB);

  console.log(subSetSetAB)//should be true;
```

## ES6 has build in set
+ you can use ``...set`` it will return the set in array format
