# Lec-4 11.03.2018

## Basic data structure

### Array

Random access memory, it requires single, not fragmented sequence of memory cells, variable with array point to the first element with index 0.
Each element goes one after another in memory, so it possible to calculate the address of any index in the array if we know the address of 0th element.

In case when element 0 should be deleted or new element should be inserted at the bigining you need to shift all elements

In case with dynamic length array, under the hood created array with defined length and every time when there is no free space in the array, it should find new place in memory to copy current elements + new one.

https://en.wikipedia.org/wiki/Array_data_structure

### Linked list

Each element of linked list have value and link to next element in the list.
When new element adding to list, it finds place in memory to save one value plus link to the next element and change the link of the previous element to point to the new one.

Pay attention to complexity of basics operations with linked list and array in wikipedia

https://en.wikipedia.org/wiki/Linked_list

### Stack and Queue

Collections of elements have two method `insert` nad `get`

in the stack, insertion and getting elements should be the same no matter at the start of the collection or at the end

in queue insert a new element to the beginning and get an element from the end


https://en.wikipedia.org/wiki/Stack_(abstract_data_type)

https://en.wikipedia.org/wiki/Queue_(abstract_data_type)

# Home work

1. Implement linked list
2. Implement Stack and Queue base on linked list