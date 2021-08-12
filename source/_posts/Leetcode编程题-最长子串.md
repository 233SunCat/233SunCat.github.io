---
title: 3. 无重复字符的最长子串
date: 2021-03-21 10:30:26
categories: 
- Leetcode编程题
---

给定一个字符串，请你找出其中不含有重复字符的 最长子串 的长度。 

示例 1:
输入: s = "abcabcbb"
输出: 3 
解释: 因为无重复字符的最长子串是 "abc"，所以其长度为 3。

示例 2:
输入: s = "bbbbb"
输出: 1
解释: 因为无重复字符的最长子串是 "b"，所以其长度为 1。

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/longest-substring-without-repeating-characters
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

```go
思路：使用一个栈，字符串压入栈中，返回最新的栈中公共子串
func lengthOfLongestSubstring(s string) int {
	a := []string{}
	max_nums := 0
	if len(s) == 1 {return 1} 
	for _, v := range s {
		a = compare(a, string(v))//返回栈中最新公共无重复子串
		if len(a) > max_nums {max_nums = len(a)}
	}
	return max_nums
}
//使用一个辅助栈,时间复杂度O(N)
func compare(a []string, b string) []string {
	for i, v := range a {
		if v == b {
         	a = append(a, b)
			return a[i+1:]
		}
	}
	a = append(a, b)
	return a
}
```



```go
第二个解题思路：动态规划，分解为子问题，运用状态转移公式
设dp[i]----前i数组的最长公共子串
dp[i] = dp[i-1] + 1 || dp[i] = 1
结果还是要判断子数组是否有重复值
//使用哈希表结合状态
```



```go
暴力破解：起始/结束两指针遍历O(N^2)
改进：1.每次与前面比较的时候可以用哈希表O（1），2.找到重复字符的时候，起始指针可以跳大点
```

