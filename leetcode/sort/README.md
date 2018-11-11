## Sort 知识点
---
### Insertion Sort
1. 原理就像你在打扑克牌抓牌⼀样。
2. 如果是Single Linked List的实现⽅式，就要⽤从前到后扫描。LeetCode147. Insertion Sort List
3. 在找插⼊位置的时候可以使⽤binary search，但是不能把时间复杂度降低， 为什么？LeetCode35.
Search Insert Position
4. Sort a stack
5. 在⼩范围的⾥⾯速度要⽐merge sort快。
---
### Merge Sort
1. 是⼀种divide and conquer的思想
2. 在⼩范围的数字⾥⾯可以使⽤insertion sort，使⽤的阈值是K = 10 - 50。具体需要跑实验。
3. ⽤LinkedList去sort可以不⽤额外的空间，但是需要call stack。LeetCode148. Sort List。
4. Buttom Up Merge Sort.
5. 可以衍⽣出reverse pair的思想。LeetCode493. Reverse Pairs
---
### Heap Sort
1. ⼀种独特的array结构，从1开始。可以通过index去找到parent和children。
2. ⼀种理论上很好⽤的⽅式，worst-case O(NlogN)，best-case O(N)。同时也是inplace的。
3. 可以做min-heap和max-heap。当你需要维护⼀个数据结构储存极值的时候，可以考虑⽤priority
queue。LeetCode23. Merge k Sorted Lists
---
### Quick Sort
1. 选取pivot的时候是可以随机的。有⼀种⽅法叫做median of the 3
2. Quick Select相关知识。LeetCode215. Kth Largest Element in an Array
3. worst-case是O(N )。但是在现实⽣活中是最好的sort⽅式。
4. 处理duplication的⽅式可以采⽤three-way quick sort。LeetCode75. Sort Colors。
---
### Linear Sort
1. Count sort会记录每个element的数量，然后进⾏排序。可以做[LeetCode75. Sort Colors](https://github.com/qw924/python_basic/blob/master/leetcode/sort/75.%20Sort%20Colors.md)的follow-up。
2. Bucket Sort假设数据符合uniformly distributed over [0-1]。 分割成⼏段，然后根据这⼏段进⾏排序。
3. Radix Sort是按照数字digit排序的⽅法。反直觉地从最后⼀个位数看起。
