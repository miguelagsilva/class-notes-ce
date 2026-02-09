## Intro to Mooshak and Data Structures

Mooshak used for delivering projects, 1 a week (every tuesday in the afternoon), time to deliver 2 weeks. 2 Group project to deliver.

Login is student number and password sent to the institutional email. The outcome of delivering the code comes up as a 0 or 1 grade.

### Supported programming languages:``
- C11 (GCC 8.5.0)
  - gcc -std=c11 -O2 "$file" -lm
- C++17 (GCC 8.5.0)
  - g++ -std=c++17 -O2 "$file" -lm
- Java 11 (OpenJDK 11.00)
- Python 3.10

C or C++ is recommended for the projects (python and java lead to TLE due to language overhed), the weekly deliverables can be in any language. There is code to improve reading/writing time in python and java in the slides.

*Mooshak runs like this*
```bash
./a.out < inputFile.txt > outputFile.txt
```

## Arrays
 In general: O(1) for lookups and O(n) for insertions and deletions.
 However, insertions and deletions at the end can have O(1).
 **Contiguous memory is cache friendly.**
**Dont make programs multi-threaded in this course.**

Builtin sorting functions in the supported programming languages:
• C: qsort from <stdlib.h> 
• C++: sort from \<algorithm> 
• Java: Collections.sort from java.util 
• Python: list.sort() or sorted

Code to read list of numbers until EOF: 
• C: https://git.dei.uc.pt/snippets/28 
• C++: https://git.dei.uc.pt/snippets/27 
• Java: https://git.dei.uc.pt/snippets/29 
• Python: https://git.dei.uc.pt/snippets/30

## Deque
An array of arrays that can have O(1) insertion and deletion at the beggining as well with a small cost in terms of random access and insertion/deletion at the end when compared to dynamically sized arrays.

## Linked Lists
O(1) for insertions but O(n) for lookup
Useful whenever there are many insertions or deletions in the middle or at the beginning.

## Stacks and Queues
LIFO and FIFO respectively.

## Binary trees
Set is a already implemented tree in C++. AVL, Red black trees can also be used in this course.

We can use map (non repeated elements), multiset (repeated elements) and multimap (repeated elements).

## Heap priority Queue
First value is the maximum or minimum number, insertions put the element in the place according to the value of it. The minimum (or maximum) element can be accessed in O(1), but its removal and insertions are O(log n). priority_queue in C++

## Hash tables
A hash table takes O(1) for insertion, deletion and lookup, when there are no hash collisions But it may take O(n) if there are many hash collisions 
As such a good hashing function is very important

unordered_set in C++, it automatically manages the hashing and the hashes associated with each value. However, unordered_map can be used if we want to set our own hashed and hashing algorithm.
## Summary - Usage guidelines
###### Use static size arrays when: 
• You want a fixed number of items 
• You want a stack-allocated array (when supported by the programming language) 

###### Use dynamic size arrays when: 
• You want a re-sizable array 
• You want an heap-allocated array 
• You will mostly be inserting and removing from the end (or near the end)

###### Use deques when:
• You want a dynamic size array, but 
• You want to insert/remove from both ends of the array (or near them) 

###### Use linked lists when: 
• You need to constantly insert and remove from the middle of array in known locations 
• You don’t need random access by index

###### Use priority queues when: 
• You only ever need the "largest" or "smallest" element of the collection 

###### Use self-balancing binary trees when: 
• You want to keep elements sorted 
• You need to find if elements exists or not in a list 
• You need to find the elements that are closest to another 

###### Use hash tables when: 
• You need to see if elements exist or not in a list and you do not care about order


The right choice for a data structure depends on how many insertions, deletions an lookup have to be performed and in which way 
There may be several theoretically good choices for the problem at hand, so testing may be needed to filter out the worse options 
There are many more data structures we did not discuss here but these cover many cases 
https://en.wikipedia.org/wiki/List_of_data_structures

## Evaluation
16 points for final exam
4 for projects and deliverables