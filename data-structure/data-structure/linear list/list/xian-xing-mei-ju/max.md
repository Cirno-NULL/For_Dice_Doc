# 最值算法

### 数组中两元素的最大乘积

```
def maxProduct(nums):
    a = b = 0
    for i in nums:
        if i > a:
            b , a = a , i
        elif i > b:
            b = i
    return (a-1)*(b-1)
```

### 最大连续1的个数

```
def findMaxConsecutiveOnes(nums):
    max = now = 0
    last_count = False
    for i in nums:
        if i == 1:
            if last_count:
                now +=1
            else:
                now = 1
                last_count=True
            if max < now:
                max = now
        else:
            last_count = False
    return max
```
