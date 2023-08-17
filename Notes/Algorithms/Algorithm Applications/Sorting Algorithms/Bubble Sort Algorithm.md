Bubble Sort is one of the simplest sorting algorithms. It gets its name from the way smaller elements "bubble" to the top of the list as they're repeatedly swapped with adjacent larger elements. Although not the most efficient sorting method, Bubble Sort is easy to understand and implement, making it a great starting point for learning about sorting algorithms.

**How Bubble Sort Works:**
Imagine you have a list of numbers that you want to sort in ascending order. Here's how Bubble Sort works:
1. Start from the beginning of the list.
2. Compare the first two elements. If the first element is larger than the second, swap them.
3. Move to the next pair of elements and repeat the comparison and swapping process.
4. Continue this process for the entire list, repeatedly comparing and swapping adjacent elements.
5. After one pass through the list, the largest element will have "bubbled up" to the end.
6. Repeat the process, but this time excluding the last element since it's already in the correct position.
7. Keep repeating the process, excluding one more element from the end each time, until the entire list is sorted.

**Step-by-Step Example:**
Let's say you have an unsorted list: `[5, 2, 9, 3, 4]`.
1. **Iteration 1:** `[2, 5, 3, 4, 9]` (largest element 9 is in the correct position).
2. **Iteration 2:** `[2, 3, 4, 5, 9]` (largest elements 9 and 5 are in the correct positions).
3. **Iteration 3:** `[2, 3, 4, 5, 9]` (no swaps needed, list is sorted).

**Time Complexity:**
Bubble Sort has a time complexity of $O(n^2)$, where $n$ is the number of elements in the list. This means that the time it takes to sort the list increases rapidly as the number of elements increases.

**When to Use Bubble Sort:**
Bubble Sort is primarily used for educational purposes and small lists due to its inefficiency. It's not suitable for sorting large datasets where more efficient algorithms like [[Merge Sort Algorithm|Merge Sort]] or [[Quick Sort Algorithm|Quick Sort]] are better choices.

>[!Summary]
>Bubble Sort is a simple sorting algorithm that involves repeatedly swapping adjacent elements until the list is sorted. While it's not the most efficient sorting method for large datasets, understanding how it works is a great introduction to sorting algorithms. As you explore other algorithms, you'll discover more efficient ways to sort data with better performance.