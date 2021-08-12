---
title: 原地移除元素
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
## 快慢指针使用

k给你一个数组 nums 和一个值 val，你需要 原地 移除所有数值等于 val 的元素，并返回移除后数组的新长度。
不要使用额外的数组空间，你必须仅使用 O(1) 额外空间并 原地 修改输入数组。
题目：27原地移除元素
{% codeblock  %}
func removeElement(nums []int, val int) int {
    slowindex := 0
    for fastindex:=0;fastindex<len(nums);fastindex++{
        if val!=nums[fastindex]{
            nums[slowindex] = nums[fastindex]
            slowindex++
        }
    }
    return slowindex
}
{% endcodeblock  %}


