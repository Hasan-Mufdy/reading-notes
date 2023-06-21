## Linked Lists

### What is a linked list?

A linked list consists of a data element known as a node. And each node consists of two fields: one field has data, and in the second field, the node has an address that keeps a reference to the next node.
There are two types of Linked List - Singly and Doubly. We will be implementing a Singly Linked List in this implementation.

### Big P notation

Big O(oh) notation is used to describe the efficiency of an algorithm or function. This efficiency is evaluated based on 2 factors:

1. Running time.
2. Memory space.
   Big O’s role in algorithm efficiency is to describe the Worst Case of efficiency an algorithm can have in performing its job. It specifically looks at the factors mentioned above, which we often refer to as Space and Time.

### Big O and linked lists

The Big O of time for Includes would be O(n). This is because, at its worst case, the node we are looking for will be the very last node in the linked list. n represents the number of nodes in the linked list.
The Big O of space for Includes would be O(1). This is because there is no additional space being used than what is already given to us with the linked list input.

### Linked lists memory management

The biggest differentiator between arrays and linked lists is the way that they use memory in our machines. Those of us who work with dynamically typed languages like Ruby, JavaScript, or Python don’t have to think about how much memory an array uses when we write our code on a day to day basis because there are several layers of abstraction that end up with us not having to worry about memory allocation at all.

### What is the difference between arrays and linked lists?

The fundamental difference between arrays and linked lists is that arrays are static data structures, while linked lists are dynamic data structures. A static data structure needs all of its resources to be allocated when the structure is created; this means that even if the structure was to grow or shrink in size and elements were to be added or removed, it still always needs a given size and amount of memory. If more elements needed to be added to a static data structure and it didn’t have enough memory, you’d need to copy the data of that array, for example, and recreate it with more memory, so that you could add elements to it.
