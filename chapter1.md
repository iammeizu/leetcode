# 1.TWO SUM

解题思路：

1. 暴力两层循环算法，被证明超时
2. 排序之后再循环可以，但复杂度依然很高
3. 遍历一次，寻找target - 该元素是否在列表中，可行！

```
class Solution:
    def twoSum(self, nums, target):
        d = dict()
        for i, num in enumerate(nums):
            if num not in d:
                d[target-num] = i
            else:
                return [d[num], i]
```



