---
title: 哈希表242字母异位，349数组交集，202快乐数，1两数之和
date: 2021-03-12 22:58:40
categories: 
- Leetcode编程题
---
t题目：242字母异位，349数组交集，202快乐数，1两数之和

巧妙的使用哈希表，对于哈希表不容易想到，要经常用用

202快乐数：

「快乐数」定义为：

    对于一个正整数，每一次将该数替换为它每个位置上的数字的平方和。
    然后重复这个过程直到这个数变为 1，也可能是 无限循环 但始终变不到 1。
    如果 可以变为  1，那么这个数就是快乐数。

如果 n 是快乐数就返回 true ；不是，则返回 false 。

输入：19
输出：true
解释：
12 + 92 = 82
82 + 22 = 68
62 + 82 = 100
12 + 02 + 02 = 1

来源：力扣（LeetCode）
链接：https://leetcode-cn.com/problems/happy-number
著作权归领扣网络所有。商业转载请联系官方授权，非商业转载请注明出处。

```golang
func  isHappy(n int) bool {
  //单数操作
  sum := n
  m := map[int]bool{}
  for true{
​    n = sum
​    sum = 0
​    for n != 0 {//将数分离
​      sum += (n % 10) * (n % 10)
​      n /= 10
​    }
​    if sum == 1{
​      return true
​    }
​    if m[sum] == true{//使用哈希表
​      return false
​    }
​    m[sum] = true
  }
  return false
}
```

```
两数之和，使用哈希表
输入：nums = [3,2,4], target = 6
输出：[1,2]
```

```Go
func twoSum(nums []int, target int) []int {
    hax := map[int]int{}
    for i,v := range nums{
        v2,ok:= hax[target-v]
        if ok{
            return []int{i,v2}
        }
        hax[v] = i
    }
    return []int{-1,-1} 
}
```

