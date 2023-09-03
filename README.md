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


## 位运算
[191. Number of 1 Bits](https://leetcode.com/problems/number-of-1-bits/description/)  

由于Java中没有unisigned int，所以他用2's complement notation来表示，所以不能用logn来计算位数。  
第一种解法思路是，用mask为1，然后一直左移做"and"运算。
```
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
    int bits = 0;
    int mask = 1;
    for (int i = 0; i < 32; i++) {
        if ((n & mask) != 0) {
            bits++;
        }
        mask = mask << 1;
    }
    return bits;
}
}
```

因为到某一位以后就后面就都是0，可以不用比较了，所以直接用n&(n - 1)来做运算，比较过之后直接把后面的1置于0，每次十进制减去1都会把二进制的最后一个为1的bit置于0。
```
public class Solution {
    // you need to treat n as an unsigned value
    public int hammingWeight(int n) {
        int sum = 0;
        while (n != 0) {
            sum++;
            n &= (n - 1);
        }
        return sum;
    }   
}
```

[338. Counting Bits](https://leetcode.com/problems/counting-bits/description/)  
这个题用O(nlogn)的时间是很好做出来的，但是用dp可以在O(n)时间中做出来。
```
//P(x+b)=P(x)+1,b=2^m>x
public class Solution {
    public int[] countBits(int n) {
        int[] ans = new int[n + 1];
        int x = 0;
        int b = 1;
    
        // [0, b) is calculated
        while (b <= n) {
            // generate [b, 2b) or [b, n) from [0, b)
            while (x < b && x + b <= n) {
                ans[x + b] = ans[x] + 1;
                ++x;
            }                         
            x = 0; // reset x
            b <<= 1; // b = 2b
        }
                  
        return ans;
    }
}
```

## 字符串问题
[139. Word Break](https://leetcode.com/problems/word-break/)  
```

```


[2707. Extra Characters in a String](https://leetcode.com/problems/extra-characters-in-a-string/description/?envType=daily-question&envId=2023-09-02)
```

```


