---
title: 二叉树的所有的路径
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
思路：返回所有二叉树根节点到叶子节点的路径
题目：257二叉树的所有路径
{% codeblock  %}
func binaryTreePaths(root *TreeNode) []string {
    if root == nil{
        return nil
    }
    if root.Left==nil && root.Right==nil{
        return []string{root.val}
    }
    var gender func(root *TreeNode,str string)
    var result []string
    gender = func(root *TreeNode,str string){
        if root != nil{
            str += strconv.Itoa(root.Val)
        }else{
            return 
        }
        if root.Left==nil && root.Right==nil{//到达叶子节点
            //将路径放入
            result = append(result , str)
            return 
        }
        gender(root.Left,str)//前序遍历
        gender(root.Right,str)
    }
    gender(root , "")
    return result
}
{% endcodeblock %}
