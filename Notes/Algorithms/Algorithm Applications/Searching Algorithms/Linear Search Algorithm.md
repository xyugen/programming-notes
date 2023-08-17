The Linear Search algorithm is one of the simplest searching algorithms. It's like flipping through a book page by page until you find what you're looking for. Similarly, in programming, you go through each item in a list one by one until you find the item you're searching for.

**Steps of Linear Search:**
1. **Start at the Beginning:** Begin at the first item in the list.
2. **Check Each Item:** Check each item in the list, starting from the beginning, until you find the item you're looking for.
3. **If Found, Stop:** If the item is found, stop the search and note its position.
4. **If Not Found:** If you've checked all items and haven't found the item, you can conclude that it's not in the list.

**Example: Searching for a Number in a List:**
Let's say you have a list of numbers: [5, 12, 8, 3, 20, 10, 6]. You want to find if the number 20 is in the list.
1. Start at the beginning (index 0): 5.
2. Move to the next item (index 1): 12.
3. Continue checking: 8, 3, 20 (found!).
4. Since you found the number 20, you stop the search.

**Advantages and Disadvantages:**

**Advantages:**
- Simple and easy to understand.
- Works for both sorted and unsorted lists.

**Disadvantages:**
- Can be slow for large lists, as you might have to check every item.
- Efficiency is proportional to the size of the list ([[Time Complexity#^375891|O(n) time complexity]]), where $n$ is the number of items in the list.

**Use Cases:**
Linear Search is best suited for small lists or situations where the list isn't sorted. It's often used as a simple fallback option when more complex search algorithms like [[Binary Search Algorithm|Binary Search]] or [[Hashing Algorithm|Hashing]] aren't feasible.

>[!Summary]
>The Linear Search algorithm is like scanning through a list to find an item. It's a straightforward approach and works for various types of lists. However, it might not be the most efficient choice for large lists. Understanding Linear Search helps you appreciate the foundational concepts of searching algorithms and their applications in various programming tasks.