##  🔶Day0 [1442. Count Triplets That Can Form Two Arrays of Equal XOR](https://leetcode.com/problems/count-triplets-that-can-form-two-arrays-of-equal-xor/)

找所有相邻且异或和相等的串对。

trick是，a和b异或相等，那么从a中减掉一个数加给b，异或和依旧相等。也就是说，对于异或和为0的区间[ a,b ]，就可以找到b-a个符合题意的串对。

然后加上前缀和，n^2 查找就ok了。

## 🔶Day1 [260. Single Number III](https://leetcode.com/problems/single-number-iii/)

这个题超级有意思！

数组里的数都成对出现，但是有两个数只出现一次，需要找到这两个数。

相信这道题的基础版本大家都会，一个数的话，直接异或即可。但是两个数呢？全部异或我们只能找到两个数的异或，然后是很难将它们分离的。

特别巧妙的思路：这两个数一定不同，所以至少有一位不一样，即异或时对于某一位，一个是0，另一个是1。那么我们可以根据此，将所有数分成两部分，**相同的数一定会被分到同一部分**，两个数分开之后，问题一下子就简单了。

巧妙！

## 【水题】Day2  [3110. Score of a String](https://leetcode.com/problems/score-of-a-string/)

## 【水题】Day3 [344. Reverse String](https://leetcode.com/problems/reverse-string/)
## 【水题】Day4 [2486. Append Characters to String to Make Subsequence](https://leetcode.com/problems/append-characters-to-string-to-make-subsequence/)

## 【水题】Day5 [409. Longest Palindrome](https://leetcode.com/problems/longest-palindrome/)

## 【水题】Day6 [1002. Find Common Characters](https://leetcode.com/problems/find-common-characters/)
代码量有点大
## 【水题】Day7 [846. Hand of Straights](https://leetcode.com/problems/hand-of-straights/)
## Day8 [648. Replace Words](https://leetcode.com/problems/replace-words/)
字典树，代码量略微有些大
## 【水题】Day9 [523. Continuous Subarray Sum](https://leetcode.com/problems/continuous-subarray-sum/)

## 【水题】Day10 [974. Subarray Sums Divisible by K](https://leetcode.com/problems/subarray-sums-divisible-by-k/)
和前一道题的区别是，数据范围更小，可以直接桶存储不用map。