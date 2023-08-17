Insertion Sort is a simple and intuitive sorting algorithm that works by building a sorted list one item at a time. It's like sorting a hand of playing cards in your hand as you receive them. While it might not be the most efficient algorithm for large lists, it's easy to understand and works well for smaller datasets.

**How Insertion Sort Works:**
1. **Initial State:** Imagine you have a list of unsorted numbers, and you want to sort them in ascending order.
2. **Build the Sorted List:** Start with the first element. It's already considered "sorted" since there's nothing before it.
3. **Insertion Process:** For each subsequent element in the unsorted portion of the list, compare it to the elements in the sorted portion. Move the current element to its correct position in the sorted portion by shifting larger elements to the right.
4. **Repeat:** Repeat this process until you've gone through all elements in the unsorted portion.

**Step-by-Step Example:**
Let's say you have the unsorted list `[5, 2, 9, 1, 5, 6]`.
1. **Iteration 1:** `[5]` (Already sorted)
2. **Iteration 2:** `[2, 5]` (Insert 2 in the correct position)
3. **Iteration 3:** `[2, 5, 9]` (Insert 9 in the correct position)
4. **Iteration 4:** `[1, 2, 5, 9]` (Insert 1 in the correct position)
5. **Iteration 5:** `[1, 2, 5, 5, 9]` (Insert 5 in the correct position)
6. **Iteration 6:** `[1, 2, 5, 5, 6, 9]` (Insert 6 in the correct position)

**Algorithm Complexity:**
- **Time Complexity:** In the worst-case scenario, when the list is in reverse order, Insertion Sort takes approximately $O(n^2)$ comparisons and swaps.
- **Best Case:** When the list is already sorted, Insertion Sort runs in $O(n)$ time, making it efficient.
- **Space Complexity:** Insertion Sort only requires a small amount of additional memory for the swapping and comparison operations, so it has a space complexity of $O(1)$.

**Pros and Cons:**

**Pros:**
- Simple to implement and understand.
- Efficient for small lists or nearly sorted lists.
- Performs well when the list is already partially sorted.

**Cons:**
- Inefficient for larger lists compared to more advanced algorithms like [[Merge Sort Algorithm|Merge Sort]] or [[Quick Sort Algorithm|Quick Sort]].
- The [[Time Complexity|time complexity]] can be problematic for larger datasets.

>[!Summary]
>Insertion Sort is like arranging cards in your hand one by one, finding the right spot for each new card. While not the fastest sorting algorithm for large lists, it's a great way to introduce the concept of sorting algorithms and their basic principles. Understanding Insertion Sort can provide insights into more complex sorting algorithms and the concept of sorting in general.