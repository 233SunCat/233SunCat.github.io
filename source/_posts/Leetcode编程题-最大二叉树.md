---
title: 最大二叉树
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
给定一个不含重复元素的整数数组 nums 。一个以此数组直接递归构建的 最大二叉树 定义如下：

    二叉树的根是数组 nums 中的最大元素。
    左子树是通过数组中 最大值左边部分 递归构造出的最大二叉树。
    右子树是通过数组中 最大值右边部分 递归构造出的最大二叉树。

返回有给定数组 nums 构建的 最大二叉树 。
题目：654最大二叉树
伪代码：
{% codeblock  %}
func constructMaximumBinaryTree(nums []int) *TreeNode {
    if len(nums)==0{
        return nil
    }
    max := -1
    index := -1
    for i,v := range nums{//第一步从数组找出最大元素
        if v > max{
            max = v
            index = i
        }
    }
    root := new(TreeNode)
    root.Val = max
    root.Left = constructMaximumBinaryTree(nums[:index])//第二步分割数组
    root.Right = constructMaximumBinaryTree(nums[index+1:])
    return root
}
{% endcodeblock %}
