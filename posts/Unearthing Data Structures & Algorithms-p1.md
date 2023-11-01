---
title: Unearthing Data Structures & Algorithms - The Essentials Guide. P1
image: 22.gif
description: DSA
---

Data structures are the backbone of problem-solving and acing programming interviews. If you're new to the world of computer science, don't worry! Understanding data structures might seem daunting at first, but with a little guidance, it can be simplified.

## Choosing the Right Data Structure

Before we dive into the nitty-gritty of data structures, let's understand the importance of choosing the right one. Each data structure has its strengths and weaknesses, and selecting the appropriate one can significantly impact the performance of your code. We often use Big O notation to measure their efficiency.

### Three Key Data Structures You Should Know

To build a solid foundation in data structures, focus on three key ones: arrays, linked lists, and hash tables.

Arrays are fixed in size, making adding elements inefficient at times. However, they excel at retrieving items quickly by computing the item's location inside the array.

Linked lists which consist of nodes with values and pointers are perfect for scenarios where you need to add or remove elements efficiently. However, accessing elements might be a bit slower compared to arrays.

Hash tables, on the other hand, allow for efficient retrieval of values based on keys. They use a hashing function to determine the memory location, making them incredibly fast for data retrieval. While hash tables are powerful, they can suffer from collisions, where two keys hash to the same memory location. But fear not! There are various methods to resolve these collisions and ensure your hash table works flawlessly.

### Embracing Data Structures and Algorithms

Data structures and algorithms are the heart and soul of computer science. For instance, the depth-first search is a vital algorithm that's used extensively. Additionally, queues and stacks are efficient data structures employed in breadth-first search and other limited use cases.

Graphs and trees also play a crucial role in computer science. They share similarities with linked lists, where nodes point to other nodes, creating a complex but organized network.

### The Power of Binary Search Trees

When it comes to searching efficiently, Binary Search Trees (BSTs) take the crown. With specific rules governing node relationships, traversing a BST allows for quick element location, making it a popular choice in various applications.

### Building Your Skills

If you're a beginner looking to improve your skills in data structures and algorithms, practice is key. As you start your search, you'll likely come across platforms like Code Wars and LeetCode, which are excellent for honing your problem-solving abilities. LeetCode, in particular, offers real-world programming interview questions from tech companies.

However, there are even better platforms that use those resources to streamline the learning process. CodeTrack is one such platform, specializing in Code Wars problems. It's managed by a dedicated professor who hosts workshops most Fridays throughout the year, making it a great choice for learning.

Another valuable resource with a focus on LeetCode is Grind75 Tech, "The Interview Handbook. Despite its LeetCode focus, the site provides valuable insights for developers at any skill level.

## The Big Picture

Now that we got the base essentials out of the way. We can look further into the horizon and take a peek at some of the most important Algorithms there are. The main goal of an algorithm is to take in input, process it and provide an output that is expected. Algorithms can be classified based on the time and space complexity, the technique used for solving the problem, and the type of problem it solves. Examples of algorithms are sorting, searching, graph traversals, string manipulations, mathematical operations, and many more.

Algorithms we will be going over in this first part of the article

1. Sorting algorithms: Sorting is a fundamental operation in computer science and there are several efficient algorithms for it, such as quicksort, merge sort and heap sort.

2. Search algorithms: Searching for an element in a large dataset is a common task and there are several efficient algorithms for it, such as binary search and hash tables.
3. Graph algorithms: Graph algorithms are used to solve problems related to graphs, such as finding the shortest path between two nodes or determining if a graph is connected.

These algorithms are widely used in various applications and a programmer needs to have a strong understanding of them. So I will try my best to explain them.

## Sorting algorithms

### Quicksort

Quicksort is a divide-and-conquer algorithm that chooses a “pivot” element from the array and partitions the other elements into two sub-arrays, according to whether they are less than or greater than the pivot. The sub-arrays are then sorted recursively.

# ![code](https://i.imgur.com/CwVKsYp.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Quicksort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function quicksort(arr) {  // Define a function called 'quicksort' that takes an array 'arr' as input.
  if (arr.length <= 1) {  // Check if the array has one element or is empty.
    return arr;  // If so, return the array as it's already sorted.
  }
  const pivot = arr[Math.floor(arr.length / 2)];  // Choose the pivot element as the middle element of the array.
  const left = [];  // Create an empty array 'left' to store elements smaller than the pivot.
  const middle = [];  // Create an empty array 'middle' to store elements equal to the pivot.
  const right = [];  // Create an empty array 'right' to store elements greater than the pivot.
  for (let i = 0; i < arr.length; i++) {  // Iterate through the array.
    if (arr[i] < pivot) {  // If the element is smaller than the pivot, add it to the 'left' array.
      left.push(arr[i]);
    } else if (arr[i] === pivot) {  // If the element is equal to the pivot, add it to the 'middle' array.
      middle.push(arr[i]);
    } else {  // If the element is greater than the pivot, add it to the 'right' array.
      right.push(arr[i]);
    }
  }
  // Recursively sort the 'left' and 'right' arrays and concatenate them with 'middle' to get the final sorted array.
  return quicksort(left).concat(middle).concat(quicksort(right));
}
console.log(quicksort([3, 6, 8, 10, 1, 2, 1]));  // Call 'quicksort' with an example array and print the result.
</code></pre>
</details>

</br>

### Merge Sort

The merge sort algorithm is a divide-and-conquer algorithm that divides an array in two, sorts the two halves, and then merges them back together.

# ![Merge Sort code](https://i.imgur.com/NOJFsRt.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Merge Sort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
// Merge Sort Implementation (Recursive)
function mergeSort(unsortedArray) {  // Define a function called 'mergeSort' that takes an unsorted array as input.
  if (unsortedArray.length <= 1) {  // Check if the array has one element or is empty.
    return unsortedArray;  // If so, return the array as it's already sorted.
  }
  const middle = Math.floor(unsortedArray.length / 2);  // Find the middle index of the array.
  const left = unsortedArray.slice(0, middle);  // Create a left subarray by slicing from the start to the middle.
  const right = unsortedArray.slice(middle);  // Create a right subarray by slicing from the middle to the end.
  // Using recursion to combine the left and right
  return merge(
    mergeSort(left),  // Recursively call 'mergeSort' on the left subarray.
    mergeSort(right)  // Recursively call 'mergeSort' on the right subarray.
  );
}
function merge(left, right) {  // Define a function called 'merge' that merges two sorted arrays 'left' and 'right'.
  let resultArray = [];  // Create an empty array to store the merged result.
  let leftIndex = 0;  // Initialize a variable 'leftIndex' to track the index in the 'left' array.
  let rightIndex = 0;  // Initialize a variable 'rightIndex' to track the index in the 'right' array.
 while (leftIndex < left.length && rightIndex < right.length) {  // Continue while there are elements in both 'left' and 'right'.
    if (left[leftIndex] < right[rightIndex]) {  // If the element in 'left' is smaller, add it to the 'resultArray'.
      resultArray.push(left[leftIndex]);
      leftIndex++;
    } else {  // If the element in 'right' is smaller, add it to the 'resultArray'.
      resultArray.push(right[rightIndex]);
      rightIndex++;
    }
  }
  return resultArray
          .concat(left.slice(leftIndex))  // Concatenate any remaining elements from 'left'.
          .concat(right.slice(rightIndex));  // Concatenate any remaining elements from 'right'.
}
</code>
</pre>
</details>

### Heap Sort

The heap sort algorithm is a comparison-based sorting algorithm that builds a heap from the input elements and then repeatedly extracts the maximum element from the heap and places it at the end of the sorted output array.

 ![Heap Sort code](https://i.imgur.com/fkqO329.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Heap Sort Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
// JavaScript program for implementation
// of Heap Sort
// Define a function called 'sort' that takes an array 'arr' as input.
function sort(arr) {
  // Get the length of the array.
  const N = arr.length;
  // Build heap (rearrange array)
  // Start from the middle and move towards the beginning to create a max heap.
  for (let i = Math.floor(N / 2) - 1; i >= 0; i--) {
    heapify(arr, N, i);
  }
  // One by one, extract an element from the heap
  for (let i = N - 1; i > 0; i--) {
    // Swap the current root (maximum value) with the last element.
    [arr[0], arr[i]] = [arr[i], arr[0]];
    // Call max heapify on the reduced heap
    heapify(arr, i, 0);
  }
}
// Define a function called 'heapify' for max heapifying a subtree.
// This function takes an array 'arr', the size of the heap 'N', and an index 'i'.
function heapify(arr, N, i) {
  let largest = i;  // Initialize 'largest' as the root node.
  const l = 2 *i + 1;  // Calculate the index of the left child.
  const r = 2* i + 2;  // Calculate the index of the right child.
  // If the left child is larger than the root, update 'largest'.
  if (l < N && arr[l] > arr[largest])
    largest = l;
  // If the right child is larger than the largest so far, update 'largest'.
  if (r < N && arr[r] > arr[largest])
    largest = r;
  // If 'largest' is not the root, swap them and recursively heapify the subtree.
  if (largest !== i) {
    [arr[i], arr[largest]] = [arr[largest], arr[i]];
    heapify(arr, N, largest);
  }
}
// Define a utility function to print the elements of an array.
function printArray(arr) {
  const N = arr.length;
  for (let i = 0; i < N; ++i) {
    console.log(arr[i] + " ");
  }
}
// Create an array to be sorted.
const arr = [12, 11, 13, 5, 6, 7];
const N = arr.length;
// Call the 'sort' function to sort the array.
sort(arr);
console.log("Sorted array is");
// Print the sorted array elements.
printArray(arr);
// This code is contributed by SoumikMondal
</code>
</pre>
</details>

</br>

## Search algorithms

### Binary Search

Binary search is an efficient algorithm for finding an item from a sorted list of items. It works by repeatedly dividing in half the portion of the array being searched until the target value is found.

![Binary search code](https://i.imgur.com/LdmwRQn.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Binary search Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function binarySearch(arr, target) {
  let left = 0;
  let right = arr.length - 1;
  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) {
      return mid; // Found the target, return its index
    } else if (arr[mid] < target) {
      left = mid + 1; // Target is in the right half of the current range
    } else {
      right = mid - 1; // Target is in the left half of the current range
    }
  }
  return -1; // Target not found in the array
}
// Example usage:
const sortedArray = [1, 3, 5, 7, 9, 11, 13, 15, 17];
const targetValue = 9;
const resultIndex = binarySearch(sortedArray, targetValue);
if (resultIndex !== -1) {
  console.log(`Target ${targetValue} found at index ${resultIndex}.`);
} else {
  console.log(`Target ${targetValue} not found in the array.`);
}
</code>
</pre>
</details>

In this implementation, the binarySearch function takes a sorted array (arr) and a target value (target) as inputs. It sets two pointers, left and right, initially pointing to the first and last elements of the array, respectively.

It then enters a loop that continues as long as the left is less than or equal to the right. In each iteration, it calculates the middle index (mid) of the current range. If the element at the middle index is equal to the target value, the function returns the index. If the target value is less than the element at mid, it updates right to search in the left half of the current range; otherwise, it updates left to search in the right half.

If the loop exits without finding the target value, the function returns -1 to indicate that the target value is not present in the array.

The example usage demonstrates searching for the target value 9 in the sorted array. If the target value is found, it prints the index where it was found; otherwise, it indicates that the target value is not present in the array.

Hash Tables

A hash table is a fundamental data structure that plays a crucial role in many aspects of programming. To gain a deeper understanding of how it works and its practical applications, I highly recommend watching this informative [video](https://www.youtube.com/watch?v=LPzN8jgbnvA).

# ![Hash Tables code](https://i.imgur.com/DZrlIgL.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Hash Tables Code</summary>
   <pre style="padding: 1em 0em ">
  <code class="language-javascript">
// In this example, the chaining method, also known as closed addressing,
// was used to deal with collisions.
class HashTable {
    constructor() {
        this.table = new Array(127);  // Create an array with a length of 127 (to represent ASCII symbols).
        this.size = 0;  // Initialize the size of the hash table to 0.
    }
    _hash(key) {  // Define a hash function to compute the index for a given key.
        let hash = 0;
        key = key.toString();
        for (let i = 0; i < key.length; i++) {
            hash += key[i].charCodeAt();  // Calculate the sum of character codes in the key.
        }
        return hash % this.table.length;  // Return the hash value within the table's length.
    }
    loadFactor() {  // Calculate the load factor (size / table length).
        return (this.size / this.table.length).toFixed(3);  // Return a fixed decimal representation of the load factor.
    }
    display() {  // Display the contents of the hash table.
        this.table.forEach((value, index) => {
            console.log(index, ':', (value.length > 1) ? value : value[0]);  // Output each index and its associated values.
        });
    }
    insert(key, value) {  // Insert a key-value pair into the hash table.
        const index = this._hash(key);  // Calculate the index for the key.
        if (this.table[index]) {  // If the index already contains data (collision handling).
            for (let i = 0; i < this.table[index].length; i++) {
                if (this.table[index][i][0] === key) {  // If the key already exists, update its value.
                    this.table[index][i][1] = value;
                    return;
                }
            }
            this.table[index].push([key, value]);  // If not, add a new key-value pair to the index.
        } else {
            this.table[index] = [];  // If the index is empty, create a new array.
            this.table[index].push([key, value]);  // Add the key-value pair to the new array.
        }
        this.size++;  // Increase the size of the hash table.
    }
    retrieve(key) {  // Retrieve a value by its key.
        const entry = this._hash(key);
        if (this.table[entry]) {  // If the index exists and contains data.
            for (let i = 0; i < this.table[entry].length; i++) {
                if (this.table[entry][i][0] === key) {  // Find and return the value associated with the key.
                    return this.table[entry][i][1];
                }
            }
        }
        return undefined;  // Return undefined if the key is not found.
    }
    delete(key) {  // Delete a key-value pair by key.
        const index = this._hash(key);
        if (this.table[index] && this.table[index].length) {  // If the index exists and is not empty.
            for (let i = 0; i < this.table[index].length; i++) {
                if (this.table[index][i][0] === key) {  // Find and remove the key-value pair.
                    this.table[index].splice(i, 1);
                    this.size--;  // Decrease the size of the hash table.
                    return true;  // Return true to indicate success.
                }
            }
        } else {
            return false;  // Return false to indicate that the key was not found.
        }
    }
}
const ht = new HashTable();  // Create an instance of the HashTable class.
ht.insert('Ford', 250);  // Insert key-value pairs.
ht.insert('Audi', 320);
ht.insert('Bugatti', 457);
ht.insert('U', 100);  // This will collide with 'Bugatti'.
ht.display();  // Display the contents of the hash table.
// Output:
// 6 :  [ 'Audi', 320 ]
// 14 : [ 'Ford', 250 ]
// 85 : [ [ 'Bugatti', 457 ], [ 'U', 100 ] ]
console.log(ht.loadFactor());  // Output the load factor (0.031).
console.log('\nretrieved: ', ht.retrieve('Ford'));  // Retrieve and print values by keys.
console.log('retrieved: ', ht.retrieve('Audi'));
console.log('retrieved: ', ht.retrieve('Bugatti'));
console.log('retrieved: ', ht.retrieve('U'));
console.log('\n' + ht.delete('U'));  // Delete a key-value pair and output true if successful.
ht.display();  // Display the updated contents of the hash table.
// Output:
// 6:  [ 'Audi', 320 ]
// 14: [ 'Ford', 250 ]
// 85: [ 'Bugatti', 457 ]
</code></pre>
</details>

</br>

## Graph Algorithm

### Dijkstra’s shortest path algorithm

Dijkstra's shortest path algorithm is a method for determining the most efficient route between two nodes in a graph by considering the associated costs or weights on the edges. It's widely used in applications like GPS navigation, network routing, and logistics optimization.

 ![Dijkstra’s code](https://i.imgur.com/QTvBbb0.gif)

  <details style="background-color: #f1f3f5;
  font-family: courier, monospace;
  color: #0a0a0a;
  ">
  <summary >Dijkstra’s Code</summary>
  <pre style="padding: 1em 0em ">
  <code class="language-javascript">
function dijkstra(graph, source) {
  // Initialize the distance array.
  let distance = new Array(graph.length).fill(Infinity);
  distance[source] = 0;
  // Initialize the visited array.
  let visited = new Array(graph.length).fill(false);
  // Create a priority queue.
  let priorityQueue = new PriorityQueue();
  priorityQueue.add(source, 0);
  // While the priority queue is not empty:
  while (!priorityQueue.isEmpty()) {
    // Get the vertex with the minimum distance.
    let currentVertex = priorityQueue.remove();
    // Mark the vertex as visited.
    visited[currentVertex] = true;
    // For each neighbor of the current vertex:
    for (let neighbor of graph[currentVertex]) {
      // If the neighbor has not been visited:
      if (!visited[neighbor]) {
        // Calculate the new distance to the neighbor.
        let newDistance = distance[currentVertex] + graph[currentVertex][neighbor];
        // If the new distance is shorter than the current distance:
        if (newDistance < distance[neighbor]) {
          // Update the distance to the neighbor.
          distance[neighbor] = newDistance;
          // Add the neighbor to the priority queue.
          priorityQueue.add(neighbor, newDistance);
        }
      }
    }
  }
  // Return the distance array.
  return distance;
}
</code></pre>
</details>

</br>

## Conclusion

Wrapping up the initial segment of this three-part blog series, it's essential to understand that data structures serve as the fundamental pillars of efficient algorithms and problem-solving in the realm of computer science. Though they may seem intricate at first glance, with consistent practice and the proper guidance, you'll soon discover their prowess and be able to harness it for crafting elegant and efficient solutions.

Thank you for joining us in this exploration. I appreciate your readership. Be sure to stay tuned for the next two parts of this series, where we'll delve deeper into the fascinating world of data structures and algorithms. Happy coding!

## Acknowledgements

Sites used for visualizations:

- [Visualgo](https://visualgo.net/en) - Visualgo website
- [Heap Visualization by Ben Frederickson](https://www.benfrederickson.com/heap-visualization/) - Heap Visualization by Ben Frederickson
- [Pathfinding Visualizer by Clement Mihailescu](https://clementmihailescu.github.io/Pathfinding-Visualizer/#) - Pathfinding Visualizer by Clement Mihailescu
- [CSVISTool](https://csvistool.com/) - CSVISTool website
- [Algorithms Visualization by cs.usfca.edu](https://www.cs.usfca.edu/~galles/visualization/Algorithms.html) - Algorithms Visualization by cs.usfca.edu
- [**A* (A-Star) Pathfinding Algorithm Visualization on a Real Map**](https://www.youtube.com/watch?v=CgW0HPHqFE8) - A* (A-Star) Pathfinding Algorithm Visualization on a Real Map by ones and zeros
