## 1.TWO SUM

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

上述代码解释：

同时遍历nums的索引和值

将每个遍历到元素的补，存进字典d。遍历到后面的元素时，如果在d中找到了该元素，说明之前有可以与之组成target的元素，然后返回两者的索引即可。

不需要额外开辟一个列表来存储所有的索引

笔者一开始也没有想到这么好的算法，看到之后感觉很神奇

虽然还可以用排序来优化，但重点是上面这个算法，这里就不再深入探讨

