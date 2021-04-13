# 排序算法

## 冒泡排序

冒泡排序的思想:  
利用数组下标的特性进行的比大小行为  
最差期望为逆序排序

伪代码如下:

```text
do
  swapped = false
  for i = 1 to indexOfLastUnsortedElement-1
    if leftElement > rightElement
      swap(leftElement, rightElement)
      swapped = true
while swapped
```

