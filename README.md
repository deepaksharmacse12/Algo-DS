#GeeksforGeeks

## Arrays
1. [Given an array of 2n elements of which n are similar and n are different.](http://stackoverflow.com/questions/6655536/given-an-array-of-2n-elements-of-which-n-are-similar-and-n-are-different) => Majority element (Using Moore’s Voting Algorithm)
2. [Search an element in a sorted and rotated array](http://www.geeksforgeeks.org/search-an-element-in-a-sorted-and-pivoted-array/) : 
  * [finding the pivot](http://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/): Pattern => The minimum element is the only element whose previous element is greater than it. If there is no such element, then there is no rotation and first element is the minimum element.
  * Most of the solution are when elements are __distinct__, separate solution for __repeating elements__.

## Binary Trees
1. [How to determine if a binary tree is height-balanced?](http://www.geeksforgeeks.org/how-to-determine-if-a-binary-tree-is-balanced/):First go directly and then go for the optimized approach by **passing the pointers** so as to **calculate the height**.
```C
// h is the height of tree rooted at node root
bool checkBalancedTree(node * root, int *h){
	if(root == null){*h = 0; return false;}
}
```

## Bit Magic
#### 1. Some of the common tricks involved in all the quetions are **getBit**, **setBit**, **flipBit**:
```C
bool getBit(int n int index){
	return ((n & (1 << index)) > 0);
}
// bool b used for setting bit to 0 or 1
int setBit(int n, int index, bool b){
	if(b){
		return (n | (1 << index));
	}
	else{
		int mask = ~(1 << index);
		return n & mask;
	}
}
int toggleBit(int n, int index){
	return (n ^ (1 << index));
}
```

#### 2. Clearing more than one bits:
```C
//clear all bits from MSB through i (inclusive)
int clearBitsMSBthroughI(int num, int i){
	int mask = (1 << i) - 1;
	return num & mask;
}
// clear all bits from i through 0 (inclusive)
int clearBitsIthrough0(int num, int i){
	int mask = ~((1 << (i+1)) - 1);
	return num & mask;
}
```

### 3. Counting number of 1s in number:

```C
int countOne(int n){
	int count = 0;
	for(int c = n; c != 0; c >> 1)
		count += c&1;
	return count;
}
```

## Recursive functions
Always write base case first. Some of the common base cases are:
```C
int getHeight(node * root){
	if (root == null) return 0;
	------------
	------------
}
void binarySearch(int a[], int low, int high, int key){
	if(low>high) return;
	------------
	------------
}
```

# Cracking the Coding Interview

## 1. Arrays and Strings:
1. Most of the questions are easy to solve using hash map. 
2. Consinder using vectors (cpp STL) and strings (cpp STL), while solving the questions.
3. Hash Map for charachters will depend upon the size of the char we are using, normally 1 byte will take
```C
	bool char_set[256]; 
```
   We can also decrease the size by a factor of 8 using a bit vector for mapping, suppose string only uses the lower case letters a through z, we can use a long of 4 byte (32 bits).
```C
	int checker = 0, val;
	// mapping done in checker
	for (int i=0; i < str.length(); i++)
	{
		val = str[i];
		if (checker & (1 << val) == 0)
			checker |= 1 << val;
	}
```
4. The only "gotcha" in easy peroblems is to do it __inplace__
