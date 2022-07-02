# Trees

A tree is a data structure consisting of a set of linked nodes that represent a hierarchical tree structure. Each node is linked to others via parent-children relationship. The first node in the tree is the root, whereas nodes without any children are the leaves.   


![pic](https://adrianmejia.com/images/tree-parts.jpg)    

## **properties of trees:**

The top-most node is called root.    
A node without children is called leaf node or terminal node.  
Height (h) of the tree is the distance (edge count) between the farthest leaf to the root.   

A has a height of 3    
I has a height of 0

Depth or level of a node is the distance between the root and the node in question.   
H has a depth of 2   
B has a depth of 1

## **Common Terminology**  
**Node** - A Tree node is a component which may contain its own values, and references to other nodes   
**Root** - The root is the node at the beginning of the tree   
**K - A** number that specifies the maximum number of children any node may have in a k-ary tree. In a binary tree, k = 2.    
**Left** - A reference to one child node, in a binary tree   
**Right** - A reference to the other child node, in a binary tree    
**Edge** - The edge in a tree is the link between a parent and child    
**Leaf** - A leaf is a node that does not have any children   
**Height** - The height of a tree is the number of edges from the root to the furthest leaf   

# Implementing a simple tree data structure

tree node:
```
class TreeNode {
  constructor(value) {
    this.value = value;
    this.descendants = [];
  }
}
```
We can create a tree with 3 descendants as follows:
```
// create nodes with values
const abe = new TreeNode('Abe');
const homer = new TreeNode('Homer');
const bart = new TreeNode('Bart');
const lisa = new TreeNode('Lisa');
const maggie = new TreeNode('Maggie');

// associate root with is descendants
abe.descendants.push(homer);
homer.descendants.push(bart, lisa, maggie);
```
That’s all; we have a tree data structure!

![oic](https://adrianmejia.com/images/simpson2-tree.jpg)

# Binary Trees
Trees nodes can have zero or more children. However, when a tree has at the most two children, then it’s called binary tree.   
 
 Depending on how nodes are arranged in a binary tree, it can be full, complete and perfect:

**Full binary tree:** each node has exactly 0 or 2 children (but never 1).     
**Complete binary tree**: when all levels except the last one are full with nodes.     
**Perfect binary tree:** when all the levels (including the last one) are full of nodes.      

![pi](https://adrianmejia.com/images/full-complete-perfect-binary-tree.jpg)
# Summary
  

The tree is a data structure where a node has 0 or more descendants/children.     
Tree nodes don’t have cycles (acyclic). If it has cycles, it is a Graph data structure instead.     
Trees with two children or less are called: Binary Tree
When a Binary Tree is sorted so that the left value is less than the parent and the right children is higher, then and only then we have a Binary Search Tree. 
You can visit a tree in a pre/post/in-order fashion.    
An unbalanced has a time complexity of O(n). 🤦🏻‍    
A balanced has a time complexity of O(log n). 🎉    


