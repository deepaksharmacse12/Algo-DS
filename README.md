#GeeksforGeeks

## Arrays
1. [Given an array of 2n elements of which n are similar and n are different.](http://stackoverflow.com/questions/6655536/given-an-array-of-2n-elements-of-which-n-are-similar-and-n-are-different) => Majority element (Using Moore’s Voting Algorithm)
2. [Search an element in a sorted and rotated array](http://www.geeksforgeeks.org/search-an-element-in-a-sorted-and-pivoted-array/) : 
  * [finding the pivot](http://www.geeksforgeeks.org/find-minimum-element-in-a-sorted-and-rotated-array/): Pattern => The minimum element is the only element whose previous element is greater than it. If there is no such element, then there is no rotation and first element is the minimum element.
  * Most of the solution are when elements are **distinct**, separate solution for **repeating elements**.

## Binary Trees
1. [How to determine if a binary tree is height-balanced?](http://www.geeksforgeeks.org/how-to-determine-if-a-binary-tree-is-balanced/):First go directly and then go for the optimized approach by **passing the pointers** so as to **calculate the height**.
```
// h is the height of tree rooted at node root
bool checkBalancedTree(node * root, int *h){
	if(root == null){*h = 0; return false;}
}
```

## Bit Magic
1. Some of the common tricks involved in all the quetions are **getBit**, **setBit**, **flipBit**:
```
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

## Writing reursive functions
Always write base case first. Some of the common base cases are:
```
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
