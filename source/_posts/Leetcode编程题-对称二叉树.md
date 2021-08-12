---
title: 对称二叉树/二叉树的最大深度/完全二叉树的节点数
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
验证对称二叉树：
思路：递归+双指针，前序遍历，每读取一个节点就把它的左右孩子放入辅助队列
题目：101对称二叉树
伪代码：
{% codeblock  %}
func isSymmetric(root *TreeNode) bool {
    if root == nil{
        return true
    }
    return Minlist(root,root)
}
func Minlist(r1 *TreeNode,r2 *TreeNode) bool{
    if r1 == nil && r2 == nil{
        return true
    }
    if (r1 == nil && r2 != nil)||(r2 == nil && r1 != nil){
        return false
    }
    if r1.Val == r2.Val && Minlist(r1.Left,r2.Right) && Minlist(r1.Right,r2.Left){//递归
        return true
    }else{
        return false
    }
}
{% endcodeblock %}
二叉树最大深度
思路：递归
题目：104二叉树的最大深度
伪代码：
{% codeblock  %}
func maxDepth(root *TreeNode) int {
    if root == nil {
        return 0
    }
	a := maxDepth(root.Left)//左子树深度
	b := maxDepth(root.Right)//右子树深度
	if a  > b{
		return  a+1
	}else{
		return  b+1
	}
}
{% endcodeblock %}
完全二叉树的节点数
思路：前序遍历
伪代码：
{% codeblock  %}
func countNodes(root *TreeNode) int {
    if root == nil{
        return 0
    }
    return countNodes(root.Left)+countNodes(root.Right)+1//左子树+右子树+根节点
}
{% endcodeblock %}