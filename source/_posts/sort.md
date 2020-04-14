---
title: 排序算法
date: 2017-11-15 12:06:30
tags: JavaScript
index_img: /img/js.jpg
categories: [javascript]
---


先讲两种排序:冒泡排序和快速排序

### **1.冒泡排序**

原理：

1. 比较两个相邻的元素，如果左边大于右边，交换顺序，并一直比较到最后一个数字。
2. 按顺序重复1操作，直至从左到右所有元素都依次执行完毕。

所以根据原理使用两个for循环嵌套

```
function bubbleSort(arr) {
	var times = 0;
	if(arr.length <= 1) {
		return arr;
	}
	for(var i = 0; i < arr.length -1 ; i++) {
		for(var j = i+1; j< arr.length;j++) {
			if(arr[i] > arr[j]) {
				var temp = arr[i];
				arr[i] = arr[j];
				arr[j] = temp;
			}
			times++;
		}
	}
	console.log('-----times:', times);
	return arr;
}

var a = bubbleSort([4,2,6,5,3]);
console.log(a);
```

根据上面实现代码，我们可以得出时间复杂为O(n^2)

### 2.快速排序

原理：（是对冒泡排序的改进）

1. 通过一次排序将要排序的数据分割成两部份，左边数据小于右边数据。
2. 分别对左右两部分数据再按照1排序，直到成为有序序列。

```
function quickSort(arr) {
	if( arr.length <= 1) {
		return arr;
	}
	var middleIndex = Math.floor(arr.length/2);
	var middleValue = arr.splice(middleIndex,1)[0];
	var leftArray = [];
	var rightArray = [];
	for(var i = 0; i < arr.length; i++) {
		if(arr[i] <= middleValue) {
			leftArray.push(arr[i]);
		}  else {
			rightArray.push(arr[i]);
		}
	}
	console.log('-----leftArray:', leftArray, '----rightArray:', rightArray);
	return quickSort(leftArray).concat([middleValue], quickSort(rightArray));
}
```

其他排序以后再添加
