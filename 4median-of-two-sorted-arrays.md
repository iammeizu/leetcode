## 4.Median of Two Sorted Arrays

解题思路：

![](/assets/4. Median of Two Sorted Arrays.png)

如图所示，采用两个游标分别遍历两个数组，将两游标所指向的较小元素插入新的数组，直到其中一个数组遍历到末尾

然后，将另一个数组余下的元素保持原有顺序插入到新的数组，最后根据元素数量，输出中位数

```
class Solution:
    def findMedianSortedArrays(self, nums1, nums2):
        """
        :type nums1: List[int]
        :type nums2: List[int]
        :rtype: float
        """
        n1 = len(nums1)
        n2 = len(nums2)
        n4 = n1 + n2
        s = []
        index1 = 0
        index2 = 0
        while index1 < n1 and index2 < n2:
            if nums1[index1] < nums2[index2]:
                s.append(nums1[index1])
                index1 += 1
            else:
                s.append(nums2[index2])
                index2 += 1
        if index1 == n1:
            s.extend(nums2[index2:])
        elif index2 == n2:
            s.extend(nums1[index1:])
        if n4 % 2 == 0:
            return (s[int(n4/2 - 1)] +s[int(n4/2)])/2
        else:
            return s[int(n4/2)]
        
```



