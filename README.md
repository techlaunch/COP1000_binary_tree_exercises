# COP1000_binary_tree_exercises
Practice how to create Binary Trees and populate them with different types of data

## 1. Given the following sequence of numbers, create a binary search tree by inserting the above numbers from left to right
11, 6, 8, 19, 4, 10, 5, 17, 43, 49, 31

## 2. Given a sequence of letters, create a binary search tree by inserting the above letters from left to right
E A S Y Q U E S T I O N

## 3. Suppose we have int values between 1 and 1000 in a BST and search for 363. Which of the following cannot be the sequence of keys examined. 
(a) 2 252 401 398 330 363  
(b) 399 387 219 266 382 381 278 363  
(c) 3 923 220 911 244 898 258 362 363  
(d) 4 924 278 347 621 299 392 358 363  
(e) 5 925 202 910 245 363  

# Help
## How to create a Binary Tree
```javascript
class BinarySearchTree{
	constructor(val) {
	this.value = val;
	this.right = null;
	this.left = null;
	}

	insert(passedValue) {
		let subtree = passedValue < this.value ? 'left' : 'right';
		if (this[subtree]) {
	       this[subtree].insert(passedValue);
		} else {
	       this[subtree] = new BinarySearchTree(passedValue);
		}
	}

	getMax() {
	if (this.right)
		return this.right.getMax();
	else
		return this.value;
	}

	getMin() {
		if (this.left)
			return this.left.getMin();
		else
			return this.value;
	}

	contains(value) {
		if (this.value === value)
			return true;
		let subtree = value < this.value ? "left" : "right";
		if(this[subtree]) {
			return this[subtree].contains(value);
		} else {
			return false;
		}
	}
}
```

## How to add elements
```javascript
var newTree = new BinarySearchTree(11);
newTree.insert(6);
newTree.insert(8);
newTree.insert(19);
newTree.insert(4);
newTree.insert(10);
newTree.insert(5);
newTree.insert(17);
newTree.insert(43);
newTree.insert(49);
newTree.insert(31);
console.log(newTree.getMax());
console.log(newTree.getMin());
```
