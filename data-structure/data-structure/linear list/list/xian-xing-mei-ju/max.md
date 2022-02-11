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
