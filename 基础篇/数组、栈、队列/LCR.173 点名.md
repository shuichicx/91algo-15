## LCR.173 点名
某班级 n 位同学的学号为 0 ~ n-1。点名结果记录于升序数组 `records`。假定仅有一位同学缺席，请返回他的学号。

**示例 1:**

**输入:** records = [0,1,2,3,5]
**输出:** 4

**示例 2:**

**输入:** records = [0, 1, 2, 3, 4, 5, 6, 8]
**输出:** 7

**提示：**

`1 <= records.length <= 10000`

## 思路
- 二分查找
- 举例 [0,1,2,3,4,6,7,8,9,10]

|i|0|1|2|3|4|5|6|7|8|9|
|-|-|-|-|-|-|-|-|-|-|-|-|
|record|0|1|2|3|4|6|7|8|9|10

- 可知没缺失之前i和record相等，缺失后record比i多1，因此可用二分法

## 代码
```py
class Solution:
	def takeAttendance(self, records: List[int]) -> int:
		l,r=0,len(records)-1
		while l<=r:
			mid=(l+r)//2
			if records[mid]==mid:
				l=mid+1
			else:
				r=mid-1
		return l
```

## 复杂度分析
- 时间复杂度 O(logN)
- 空间复杂度 O(1)
