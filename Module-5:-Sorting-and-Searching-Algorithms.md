## Table of Contents
- [Sorting Algorithms](#sorting-algorithms)
  + [Bubble Sort](#bubble-sort)
  + [Insertion Sort](#insertion-sort)
  + [Merge Sort](#merge-sort)
  + [Quick Sort](#quick-sort)
- [Searching Algorithms](#searching-algorithms)
  + [Linear Search](#linear-search)
  + [Binary Search](#binary-search)
- [Exercises](#exercises)

***

# Sorting Algorithms

## Bubble Sort

The **Bubble Sort** algorithm is a sorting process that gradually moves to the right position, that's why it's called Bubble. This algorithm will sort data from largest to smallest (**ascending**) or vice versa (**descending**).

In simple terms, **the Bubble Sort algorithm sorts by continuously exchanging data with adjacent data until there are no more changes**. Bubble Sort is a simple sorting method, but it is an inefficient sorting method because when sorting very large data the processing could be very slow.

The properties of the Bubble Sort algorithm are as follows:
1. The number of iterations is equal to the number of numbers minus 1.
2. In each iteration, the number of exchanges is equal to the number of numbers.
3. In the Bubble Sort algorithm, even though the number sequence is already sorted, the sorting process will still be carried out.
4. There is no significant difference between ascending and descending Bubble Sort algorithms.

![bubble](https://github.com/AlproITS/DasarPemrograman/blob/master/img/bubblesort.PNG)

**Bubble Sort implementation**:
```c
void swap(int *xp, int *yp) {
   int temp = *xp;
   *xp = *yp;
   *yp = temp;
}

void bubbleSort(int arr[], int n) {
   int i, j, swapped;        // optimized with bool `swapped`:
   for (i = 0; i < n-1; i++) {
      swapped = 0;
      for (j = 0; j < n-i-1; j++) {
         if (arr[j] > arr[j+1]) {
            swap(&arr[j], &arr[j+1]);
            swapped = 1;
         }
      }
      if (swapped == 0)
         break;
   }
}
```

## Insertion Sort

**Insertion Sort** is a type of sort that is similar to when you sort playing cards in hand. This algorithm compares the first two data elements, sorts them, then checks the next data elements one by one and compares them with the sorted data elements. The basic idea of this algorithm is to find the "right" place for each element of the array.

In general, the Insertion Sort algorithm steps are as follows.
1. Get elements from the ith array.
2. Put in the previous sequence (arr [… i-1]) that has been sorted in the appropriate place.

![insertion](https://github.com/AlproITS/DasarPemrograman/blob/master/img/insertionsort.PNG)

**Insertion Sort implementation**:
```c
void insertionSort(int arr[]. int n) {
   int i, key, j;
   for (i = 1; i < n; i++) {
      key = arr[i];
      j = i-1;
    
      while (j >= 0 && arr[j] > key) {
         arr[j+1] = arr[j];
         j = j-1;
      }
      arr[j+1] = key;
   }
}
```

## Merge Sort

**Merge Sort** is a sorting algorithm which is done recursively by dividing an array into 2 parts, merging the two parts, then merging the two arrays.

Formally, the merge sort process can be written as follows:
```
Sort(L,R):

If(R > L):

  1. M = (L + R) / 2
  2. Sort(L,M)
  3. Sort(M + 1,R)
  4. Merge(L,R)
```

**More detailed explanation and implementation**: [https://www.interviewbit.com/tutorial/merge-sort-algorithm/](https://www.interviewbit.com/tutorial/merge-sort-algorithm/)

Example of a recursion flow for Merge Sort on an 8-element array:

![merge](https://github.com/AlproITS/DasarPemrograman/blob/master/img/mergesort.PNG)

At each stage, a merge process will be carried out. The merge process is done by sorting naively by taking advantage of the fact that the two partitioned arrays are already sorted.

Because every time the array size is halved, the maximum recursion depth is **log2 (N)**.

Because at each stage of recursion there are N total of merge processes, the total complexity of ordering using Merge Sort is **N log2 (N)**.

## Quick Sort

Similar to Merge Sort, **Quick Sort** is a sorting algorithm that is performed recursively and uses the Divide and Conquer principle.

Formally, the Quick Sort process can be written as follows:
```
Sort(L,R)

If (R > L):

  1. M = Partisi(L,R). //M adalah index yang posisinya sudah fix.
  2. Sort(L,M - 1)
  3. Sort(M + 1,R)
```

As for the partitions, it can be written as follows:
```
Partition(L,R):

  1. Pivot = arr[L]
  2. storeIndex = L + 1
  3. Iteration from L + 1 to R, if arr[i] < pivot, continue to Step 4.
  4. swap(arr[i],arr[storeIndex])
  5. storeIndex = storeIndex + 1
  6. If i is still less than or equal to R, go back to Step 3. Otherwise, continue to Step 7
  7. swap(arr[L],arr[storeIndex - 1])
  8. Return storeIndex - 1
```

Regarding the partitioning process, there are various ways of selecting pivots. It is possible to use leftmost data (as demonstrated above), rightmost data, or random data, depending on the implementation you think is best.

**More detailed explanation and implementation**: [https://www.interviewbit.com/tutorial/quicksort-algorithm/](https://www.interviewbit.com/tutorial/quicksort-algorithm/)

---

On average, the total complexity of Quick Sort is **O (N log2 (N))**. Even so, the worst complexity of Quick Sort is **O (N2)**. The partitioning process by selecting a random index as the pivot proved to be quite efficient to make **Quick Sort** done in complexity **O (N log2 (N))**.

Merge Sort and Quick Sort are the most commonly used sorting algorithms because they have very good efficiency even though there are more efficient algorithms such as Radix Sort. Meanwhile, Bubble Sort and Insertion Sort are almost never used. The algorithm should only be studied for knowledge only.

Between Merge Sort and Quick Sort, the use of Quick Sort is often preferred because Quick Sort is an **in-place sorting algorithm**, which means that it does not require additional memory in its implementation, unlike Merge Sort which requires additional memory with a size that is linear to the array that will be sorted.

# Algoritma Searching

## Linear Search

The easiest searching algorithm to understand and implement is **Linear Search** or also known as **Sequential Search**. Linear Search works by checking all existing elements.

Broadly speaking, how Linear Search works is:
1. Check items one by one.
2. If found, then "found".
3. If the end has not been found, then the item you are looking for is not there.

**Linear Search implementation**
```c
int linearSearch(int arr[], int n, int item) {
   int i;
   for(i = 0; i < n; ++i) {
      if(item == arr[i])
         return 1;
   }
   return -1;
}
```

## Binary Search

**Binary Search** is a searching technique in which for each iteration we divide the search space into only half the initial search space until we find what we are looking for.

In order to apply this technique, we have to make sure that our data has a monotonous up or down property ([https://en.wikipedia.org/wiki/Monotonic_function](https://en.wikipedia.org/wiki/Monotonic_function)).

![functions](https://github.com/AlproITS/DasarPemrograman/blob/master/img/functions.PNG)

> Gambar kiri dan tengah memiliki properti monoton serta gambar kanan tidak.

### Contoh 1

There is an array of size N (N <= 10 ^ 5), the elements can be up to 10 ^ 9, the array is sorted by _ascending _. \
There is a Q query (Q <= 10 ^ 5). Each query is given the number K, answer if K is in the array or not.

**Solution**\
![meme](https://github.com/AlproITS/DasarPemrograman/blob/master/img/meme-linser1.PNG)
![meme](https://github.com/AlproITS/DasarPemrograman/blob/master/img/meme-linser2.PNG)
![meme](https://github.com/AlproITS/DasarPemrograman/blob/master/img/meme-linser3.PNG)

Keyword: **Sorted**\
Since the array is sorted, it means that it has a monotonous property.

**Example**\
[2,3,8,10,13,17,28,35]

It's pretty clear that the array is monotonous. Now how to do the Binary Search?

Suppose we want to check whether the number 13 is in the array or not. (i.e .: target = 13)

1. Our search space is index[1,8].
2. Now we divide the array into 2 parts, index[1,4] and index[5,8]. To know our target is in the first or second array, we just need to check the middle value of our current search space which is index **(1 + 8) / 2 = 4**.
   > It is rounded down because there is no index 4.5 🧐
3. Array in index 4 is 10. Since we know that the array is _sorted_ in _ascending_, it means **index of element 13 must be on the right**.
4. Now the space of our search is index[5,8].
5. Divide the array into 2 more parts, [5,6] and [7,8]. Then check the middle again, namely in index **(5 + 8) / 2 = 6**.
6. The array on index 6 is 17. Since we know that the array is _sorted_ in _ascending_, it means the **index of element 13 must be on its left**.
7. Now the space of our search is index[5,5].
8. Since there is only 1 index left, **we only need to check whether index 5 is 13 or not**.

**Visualization and implementation**: [https://csacademy.com/lesson/binary_search](https://csacademy.com/lesson/binary_search)

Note that in the search process, we always divide our search space in half. Therefore, in the worst case, iteration will be performed **log2 (N)** times.

### Contoh 2

There are N squares of size a x b. The rectangle cannot be rotated. Determine the size of the largest square that can contain all of the rectangles.

**Solution**

The optimal filling of the rectangle is as follows.

![solusi](https://github.com/AlproITS/DasarPemrograman/blob/master/img/binser.PNG)

That way, we can create a function as follows:

<a href="https://www.codecogs.com/eqnedit.php?latex=f(x)&space;=&space;1,&space;jika&space;\frac{x}{a}&space;\times&space;\frac{x}{b}&space;\geq&space;n" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f(x)&space;=&space;1,&space;if&space;\frac{x}{a}&space;\times&space;\frac{x}{b}&space;\geq&space;n" title="f(x) = 1, if \frac{x}{a} \times \frac{x}{b} \geq n" /></a>

<a href="https://www.codecogs.com/eqnedit.php?latex=f(x)&space;=&space;0,&space;if&space;\&space;otherwise" target="_blank"><img src="https://latex.codecogs.com/gif.latex?f(x)&space;=&space;0,&space;if&space;\&space;otherwise" title="f(x) = 0, jika \ sebaliknya" /></a>

It can be seen that if for a K, the value of **f(K) = 1**, then the value of the next element is **f(K + 1) = 1**, Which means that the function has a **monotonous** property.

Now, we just need to find the smallest value for K so that the value **f(K) = 1**.

**Sample implementation**
```c
bool f(int k, int a, int b, int n) {
   return ((k/a) * (b/a) >= n);
}

int binser(int a, int b, int n) {
   int l = 1;
   int r = 100000;
   while (r - l > 1) {
      int mid = (l + r) >> 1;
      bool can = f(mid);
      if(can)
         r = mid;
      else
         l = mid + 1;
   }
   if (can(l))
      return l;
   else
      return r;
}
```

# Exercises

### Exercise 1: [Binary Search - Sorted](https://tlx.toki.id/problems/impl-search/B) (Straight Forward)

### Exercise 2: [Binary Search](https://tlx.toki.id/problems/impl-search/C) (Straight Forward)

### Exercise 3: [Lower Upper Bound](https://tlx.toki.id/problems/impl-search/D) (Straight Forward)

### Exercise 4: [Hamburgers](https://codeforces.com/problemset/problem/371/C)
> Similar to [Example 2] (#example-2), just adjust the function

### Exercise 5: [Vasya and String](https://codeforces.com/problemset/problem/676/C)
> Hint: Subarray is S [L..R], try to fix L / R, find the maximum pair using binser

### Exercise 6: [Penentuan Permainan](https://www.hackerrank.com/contests/quadrathlon-competitive-programming/challenges/penentuan-permainan)
> You can use formulas, but if you can use calculations, why should you? ☺