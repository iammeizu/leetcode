## 3.Longest Substring Without Repeating Characters

解题思路：

![](/assets/最长子串问题.png)

这是笔者使用MindNode导出的图片，图中很清楚的解释了算法思路

推荐大家在刷题的过程中，使用思维导视图来理清思路，这其实可以节省很多时间，避免陷入不必要的死胡同

下面附上所有代码：

```
class Solution:
    def lengthOfLongestSubstring(self, s):
        """
        :type s: str
        :rtype: int
        """
        if len(s) == 0:
            return 0
        l = []
        max = 0
        d = set()
        for i in s:
            if i not in d:
                l.append(i)
                d.add(i)
                if len(l) > max:
                    max = len(l)
            else:
                l.append(i)
                while(i != l[0]):
                    d.remove(l[0])
                    l = l[1:]
                l = l[1:]
        return max
```



