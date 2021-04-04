Complexity is the measure of performance. Performance is measured on resource consumption and in real world code can consume multiple resources. 
Complexity is also a measure on how resource requirements change as size of the problem increases(Example: larger inputs). Higher the complexity of the problem, lower the performance. 

``Performance improvement might involve tradoffs``

### Important Measures of Performance
- Time (Number of operations/ Amount of processing)
- Space (Memory to store run time information and the disk space for persistent storage)
- Network (Bandwidth used by different machines/clients)

### Big-O-Notation

Allows to express complexity as a measure of input size. Tells us how the algorithm performs when the input size increases.
- O(1): Constant time complexity. Complexity does not change with the input size. 
- O(N): Time increases linearly with input. 
- O(N^2): Time taken increases quadrtically based on input size.

``O(1) < O(log N) < O(N) < O(NlogN) < O(N^2) < O(2^N)``

Example 1:

```
calculateComplexity(int N, int M) {
    for (int i = 0; i < N; i++ {
    do something;
    } 
    for (int i = 0; i < M; i++ {
    do something;
    }
 }
 ```

O(N+M) 

*NOTE:* Complexity is additive

Example 2:

```
calculateComplexity(int N, int M) {
    for (int i = 0; i < N; i++ {
      for (int i = 0; i < M; i++ {
      do something;
    }
 }
 ```

O(N*M) 

*NOTE:* Complexity is Multiplicative

Example 3:

```
calculateComplexity(int N) {
    for (int i = 1; i < N;) {
      do something;
      i = i*2;
    }
 }
 ```
 O(logN)
 
*NOTE:* Any time if we half the input(Example: Binary Search) or go twice as fast at every step of input the complexity is logN. 
