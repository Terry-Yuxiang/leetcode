# leetcode Problems
This is the notation for leetcode problems


## 图
### 树类问题
[1245. Tree Diameter](https://leetcode.com/problems/tree-diameter/)   
简化一下题目要求，就是求图中两个node的最远距离是多少。  
思路：  
1.先从root开始，找到最远的点。  

2.再以最远的点为root，找到距离这个点最远的点。   

3.找到的距离就是图中的最远距离。  


[1522. Diameter of N-Ary Tree](https://leetcode.com/problems/diameter-of-n-ary-tree/)  
这个题跟上一个题其实很像，甚至可以把数据结构转换过去用上一个方法直接解决。  
但因为这个题给的是TreeNode类型的数据，实用上一个题的方法不方便。  
我们可以一个node的子节点的最大高度，那么到这个节点的最大直径就是 distance1Max + distance2Max + 2。 用dfs求每个节点的最大直径就可以解决这个问题。


[501. Find Mode in Binary Search Tree](https://leetcode.com/problems/find-mode-in-binary-search-tree/)   
这题如果是普通的树，用一个map计数，然后遍历两遍总共花费2n的时间就可以。  
但题目给了，这是一个Binary Search Tree，那么我们就要充分利用他的性质。BST的中序遍历是一个有序的数组，所以我们可以使用中序遍历直接统计一个数字的个数，这样有大count的时候前面的数字将被舍弃，不仅不需要额外的map的空间，也只要花费n的遍历时间。


## Binary Search(二分搜索)
二分搜索再很多题目中都可以应用，以达到减少时间复杂度的目的。有很多题的思路还是比较难想的。
[33. Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)   

[81. Search in Rotated Sorted Array II](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/description/)   

这两个题目相当于是基础的二分搜索的进阶版本，很容易想到用binary search做，但是对于81题来说，因为有相同的元素，如何确定取前半段还是后半段还是有一定的难度的。
