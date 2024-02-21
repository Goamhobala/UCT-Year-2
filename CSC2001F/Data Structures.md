### Content 
[[#Empirical Analysis]]
[[#Analysis of Algorithms (more formal)]]
<<>><''''''''''''
### Empirical Analysis
* Implement first
* Types of data to use
* Scaling test for practicality
* Identify the key parts that influence performance

### Analysis of Algorithms (more formal)
* Abstraction over implementation details
* Count the abstract operations
* Asymptotic analysis:  Identify the bound resource needed as the size of input data increases
* Time complexity: 
	* Best case
	* Worst case: Most useful, to provide some guarantee 
	* Average case: Also useful, but must be cautious that it has a wide range of meaning. (e.g. extremely fast and extremely slow or average with a few outliers)
	
* Primary parameter: N Affecting run time (e.g. input data size)
	* Most primitive operations take constant time
	* counting all operations isn't possible, so use basic operations to approximate time
* 
```java
int count = 0;
for (int i = 0; i < N; i++){
	if (a[i] == 0){
		count++;}
}
```

* The above code needs N operations

```java
int count = 0;
for (int i = 0; i < N; i++){
	for (int j = i + 1; j < N; j++){
		if (a[i] + a P[j] == 0){
			count ++;}
	}
}
```

XXXXO
XXXOO
XXOOO
XOOOO
OOOOO
* The number of operations for the second for loop
$$ 
0 + 1 + 2 + .... + (N - 1) = \frac{1}{2}N^{2}+ \frac{1}{2} N
$$

### Dominant terms
* Running time as a function of input size N
* Ignore lower order terms
e.g.
$$ \frac{1}{5}N^{2}+ N + 3 \approx \frac{1}{5}N^2$$
### Asymptotic analysis
* Big-O notation: relate two functions that are similar in a similar way
$$ f(x)==O(g(x))$$
* Basically saying that "The running time grows at most this much, but could be slower"
* Where f(x) is bounded by a multiple of g(x), as x -> infinity
* More formally: For a given function $g(x)$, we say that $f(x)$ is $O(g(x))$ if there exist positive constants C and k such that, for all sufficiently large values of x, the inequality $∣f(x)∣≤C⋅∣g(x)∣$ holds.
* **Note:** Using this definition, it is true that $x^2 = O(x^3)$ even though nobody ever writes it like this

* Common growth functions:

| Order | Name | Typical code framework |
| ---- | ---- | ---- |
| 1 | constant | a = b  + c |
| log N | logarithmic | while (N > 1) {N = N/2} |
| N | Linear | for |
| NlogN | Linearithmic | megasort |
| N^2 | quadratic | nested for loop |
| N^3 | cubic | nested nested for loop |
| 2^N | exponential | combinatorial search |
![[Pasted image 20240216094449.png]]	

* Proof: $f(x) = x + 3 = O(x)$
TODO: Check Amathuba to finish th proof
$$\begin{align}
f(x) &= x+3\\
g(x) &= x\\\\
\exists M, x_{0}\space\space s.t. \space |x+3| &\leq M_{x}\space \space \forall x_{f} \geq x_0\\



\end{align}
$$


### What is Data Structure
* Efficient way to store data and provide access operations
* In memory or in disk

![[Pasted image 20240219093758.png]]

### Maps 
* A map is a key-value pair abstract data type 
	* Insert a new item with a specified key
	* Given a key, return the value associated with the key
* AKA symbol table, dictionary, associated arrays
* e.g.
	1. Contact this with key:name value:number
	2. Dictionary: Key: word. Value: Definition
	3. Bank account: Key account number. Value: List of transactions 
* A generalisaiton of arrays (keys are indices)
	* The values can themselves be data structures
	* Keys are comparable, i.e. can be ordered

* Map operations
	* Create: Initialise an empty table
	* Insert: Add a key value pair to the table
	* Delete: Delete a key value pair from the table
	* Search: Find value paired with a given key
	* Traverse: Iterate through all the keys in the table
	* Sort
	* Select:
	* Join
	* isEmpty
	* Size

### Keys
* Must be of a comparable data type
* Use immutable types

### Map Implementations
* Ensure that the data structures are time and space efficient
* Array: integer keys are the indicies
	* Linear time
	* But only up to N keys, space inefficient if number of items exceeds N

* Case study: singly linked list:
	![[Pasted image 20240220092209.png]]
	* Search: linear: Worst case: N, but N/2 on average
	* Search + Insert: Linear (Scan till match found (to check if the key is there already), if no match, add)
		* Worst: N; Average: N
* ![[Pasted image 20240220092444.png]]
* For doubly linked list: Delete is a constant operation throughout.

### Recursion
* Solves a problem by solving one or more smaller instances of the same problem
* Recursive method: A method that calls itself
* **Recurrence**: 
	* Recursive function with a non-negative integer as the parameter
	* Each recursive call has a smaller argument, until an initial value is returned
* Most recursive programs could be converted to an equivalent non-recursive one
* Recursion can also express any computation involving loops

