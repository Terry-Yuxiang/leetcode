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


## Binary Search(二分搜索)
二分搜索再很多题目中都可以应用，以达到减少时间复杂度的目的。有很多题的思路还是比较难想的。
[33. Search in Rotated Sorted Array](https://leetcode.com/problems/search-in-rotated-sorted-array/)   

[81. Search in Rotated Sorted Array II](https://leetcode.com/problems/search-in-rotated-sorted-array-ii/description/)   

这两个题目相当于是基础的二分搜索的进阶版本，很容易想到用binary search做，但是对于81题来说，因为有相同的元素，如何确定取前半段还是后半段还是有一定的难度的。
