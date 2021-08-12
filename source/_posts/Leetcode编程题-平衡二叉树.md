---
title: 平衡二叉树
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
什么是平衡二叉树？
一个二叉树每个节点 的左右两个子树的高度差的绝对值不超过 1 。
题目：110判断平衡二叉树
思路：递归
伪代码：
(重点)
{% codeblock  %}
func isBalanced(root *TreeNode) bool {//如果有返回值，则下面有return 
    if root == nil{
        return true
    }
    if Abs(height(root.Left) - height(root.Right)) <= 1 && isBalanced(root.Left) && isBalanced(root.Right){
        return true
    }else{
        return false
    }
}
{% endcodeblock %}
{% codeblock  %}
//返回节点的高度
func height(root *TreeNode)int{
    if root == nil{
        return 0
    }
    return Max(height(root.Left) , height(root.Right)) + 1
}
//取最大值
func Max(x int , y int)int{
    if x > y{
        return x
    }else{
        return y
    }
}
//取绝对值
func Abs(x int)int{
    if x < 0{
        return 0-x
    }else{
        return x
    }
}
{% endcodeblock %}
