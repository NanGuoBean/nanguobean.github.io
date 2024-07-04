---
title: 2024年6月leetcode
date: 2024-06-01 13:00:00
tags: 刷题
categories: 面试
---
# 小结：
通过率：87%（26/30）
对于数列部分的题目，技巧掌握还不够，很多做出来的代码也不够简洁，需要多读别人的学习，滑动窗口相关的技巧需要多多训练。
图部分最后一题，蛮难；
##  🔶Day-1 [1442. Count Triplets That Can Form Two Arrays of Equal XOR](https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/)

找所有相邻且异或和相等的串对。

trick是，a和b异或相等，那么从a中减掉一个数加给b，异或和依旧相等。也就是说，对于异或和为0的区间[ a,b ]，就可以找到b-a个符合题意的串对。

然后加上前缀和，n^2 查找就ok了。

## 🔶Day0 [260. Single Number III](https://leetcode.com/problems/single-number-iii/)

这个题超级有意思！

数组里的数都成对出现，但是有两个数只出现一次，需要找到这两个数。

相信这道题的基础版本大家都会，一个数的话，直接异或即可。但是两个数呢？全部异或我们只能找到两个数的异或，然后是很难将它们分离的。

特别巧妙的思路：这两个数一定不同，所以至少有一位不一样，即异或时对于某一位，一个是0，另一个是1。那么我们可以根据此，将所有数分成两部分，**相同的数一定会被分到同一部分**，两个数分开之后，问题一下子就简单了。

巧妙！

## Day12 [75. Sort Colors](https://leetcode.com/problems/sort-colors/)

只包含0、1、2的数组排序。

O（1）空间的话，可以两个指针记录当前0和2的位置，然后进行交换

## Day13 [2037. Minimum Number of Moves to Seat Everyone](https://leetcode.com/problems/minimum-number-of-moves-to-seat-everyone/)

若干椅子和若干人随机分布在数轴上，需要计算人最少的移动距离，使每个人和椅子一一对应。

最简单肯定是贪心了，每个人肯定是匹配最近的椅子，当然，也可以用椅子匹配最近的人。

排序可以做，但有一个更好的方法：是把椅子当成-1把人当成+1（反着也可）都放在一起，然后计算某个位置的前缀和。如果为0说明匹配，否则就说明有一者多出来。多出来的就得往后“挪”或者“走”。所以加上这个多出来的绝对值与距离的乘积即可。

# 🔶Day22 [1248. Count Number of Nice Subarrays](https://leetcode.com/problems/count-number-of-nice-subarrays/)

找数组里，刚好包含k个奇数的所有子串。

有两种方式；

第一种是"笨笨"的办法：滑动窗口刚好框住k个奇数，然后往两边扩展到不能为止，乘起来。 我是额外记录每个的“下一个”奇数，实在太不优美。可以在双指针每次移动的时候记录移动距离，然后乘起来会好些。

第二种方法很通用： **f(x=k) = f(x<=k) - f(x<k)**。这个时候只需要计算一端就好了：右端点不动，只计算最大的左端点就好。

对于这种子串问题，固定一段就简单很多了。

# 🔶Day23 [1438. Longest Continuous Subarray With Absolute Diff Less Than or Equal to Limit](https://leetcode.com/problems/longest-continuous-subarray-with-absolute-diff-less-than-or-equal-to-limit/)

需要比堆更快一些。

**如何用O(1)时间维护滑动窗口最大值？双端队列。**

保证整个队列是递减的，最大值就是第一个。入队加在后面；出队只用检查第一个元素。 为什么这样可以？ 考虑某个元素a，要么被后面一个比它大的b直接踢走，要么等到窗口滑过从前面离开，因为没有被T走，所以它一定是最大的一个在最前面。

# 🔶Day29 [2192. All Ancestors of a Node in a Directed Acyclic Graph](https://leetcode.com/problems/all-ancestors-of-a-node-in-a-directed-acyclic-graph/)
我的拓扑序方法明明很巧妙！可惜数据结构太多，没办法跑出速度……

# 🔶Day30 [1579. Remove Max Number of Edges to Keep Graph Fully Traversable](https://leetcode.com/problems/remove-max-number-of-edges-to-keep-graph-fully-traversable/)

最小生成树。从0开始构建，然后只优先使用两个人都可以走的边，缺少证明。