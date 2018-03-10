# Lec-2 10.03.2018

## Dynamic connectivity problem

> Component - one or more elements are connected to each other

### Union-find algorithm

Represent elements and connections between them in array
where index is element number (name) and value is a component to which it belongs

```
 1 2 3 4 5   <= elements indexes
[1,1,3,5,5]  <= component name
```
Here we have three components
* 1 and 2
* 3
* 4 and 5

Union-find (uf) should support methods:

* `.connect(a,  d)` should connect two elements in one component
* `.isConnected(a,  d)` should return (boolean) answer are two elements connected (in the same component / is there path from `a` to `b`)
* `.count()` should return number of components
* `.component(a)` should return component name or `undefined` if element not exist

### Examples

```javascript
uf.connect(1, 2); // elements => [undefined, 2, 2]
uf.isConnected(1,2); // true
uf.count(); // 1
uf.component(1); // 2

uf.connect(2, 3); // elements => [undefined, 3, 3, 3]
uf.isConnected(1,3); // true
uf.count(); // 1

uf.connect(0, 4); // elements => [4, 3, 3, 3, 4]
uf.connect(5, 0); // elements => [4, 3, 3, 3, 4, 4]
uf.isConnected(1,3); // true
uf.count(); // 2

uf.connect(7, 0); // elements => [4, 3, 3, 3, 4, 4, undefined, 4]
uf.isConnected(1,7); // false
uf.isConnected(7,6); // false
uf.count(); // 2

uf.connect(8, 9); // elements => [4, 3, 3, 3, 4, 4, undefined, 4, 9, 9]
uf.count(); // 3

uf.component(4); // 4
uf.component(1); // 3
uf.component(10); // undefined
```


### QuickUnion

* element name === index of element in array
* value of element point to parent element
* root element is point to itself
  * if index of element === value of element this element is root
* each root element represent a component

#### Example
```javascript
//  1,2,3,4,5
// [ , , , , ]

uf.connect(3,5)

//  1,2,3,4,5
// [ , ,5, ,5]

uf.connect(3,1)

//  1,2,3,4,5
// [1, ,5, ,1]

uf.connect(4,2)

//  1,2,3,4,5
// [1,2,5,2,1]

uf.connect(5,4)

//  1,2,3,4,5
// [2,2,5,2,1]


```
### QuickUnion with weighted

To optimise finding of root element, create one more array, and store there number of elements in component, during `connect` operation always connect smaller component to bigger

### QuickUnion with weighted and pathCompression

for each operation `isConnected` we can optimise path from elements to their roots, bind each element with its root

# Home work
 - Implement Union-find algorithm
 - Implement quickUnion with weighted

### Implement quickUnion with weighted

### URLS
 - [slides](https://docs.google.com/presentation/d/1jho6Lhz9pWsqed6INyOZ0KtPkQu5Oo_Gh6bwRn7-4R4/edit?usp=sharing)
