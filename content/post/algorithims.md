+++
title="Prepping for a Google Interview"
date="2014-03-13T21:43:07"
+++


These are a bunch of notes I took when I was reading through _Cracking the Coding Interview_ in prep  for a Google Interview

- spelling algorithms correctly is important

peaks

- insertion sort always O(N^2) because going through and moving
- binary sort can assist it to be O(log(n)n) for insertions but still N^2 for swaps
- merge sort two arrays, sort, then merge, then split and repeat. O(log(n)n) complexity
- priority queue -
       - maxheap, nodes are always larger than or equal to their children (max heap property)
       - minheap, nodes are always smaller than or equal to their children (min heap property)
- heap sort -- heap on a tree, (breadth first view,)
     int array[7]; indexies
     1
    /\
   2  3
  /\  /\
 4  5 6 7
-AVL trees
   - traverse = n
   - insert nlog(n)
   - delete min
   - find next min and max and next smaller and next min
   - log(n),

Comparison Model
   -Searching: (lng)
   -Sorting nln(n)
   -All input items are blackboxes
In reality

Linear time sorting for not large - O(n sqrt(lnln(n))
-Prehashing = alpha = n/m
time, orderone = theta(1+alpha)
(a*k)mod(2^w) >> 2^(r-w) where m = 2^r
also k mod m - hash the function and modulus

Hash table properties
- make use of all info provided by key  (Key:Value)
- uniformly distrutes output across table
- maps similar keys to very different hash values
- uses only very fast operations to minimize run time.

TODO
- Binary Tree / n-tree / AVL Tree / tr-tree
   - Their Traversals
   - Insert/delete/search
- Make Graph / Search / Edges/Vertices
- Quick/MergeSort
