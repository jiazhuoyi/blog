---
title: js拷贝
date: 2018-01-05 16:17:07
tags:  JavaScript
index_img: /img/js.jpg
categories: [javascript]
---

## 深拷贝和浅拷贝

前言： 

```
1.js有五种基本类型<简单数据类型>: Undefined, Null, Boolean, Number,  String ，以及引用类型<对象>

2.基本类型的值在内存中占据着固定大小的空间，并被保存在栈内存中，当一个变量向另一个变量复制基本类型的值，会创建这个值的副本，并且我们不能给基本数据类型的值添加属性 。

3.引用类型的值是保存在堆内存里面，栈内存里面存放的是指向该对象的指针, 即地址。
```

实现数组的浅拷贝：

```
var arr = [1, 2, 3, '4'];

var arr2 = arr;
arr2[1] = "test"; 
console.log(arr); // [1, "test", 3, "4"]
console.log(arr2); // [1, "test", 3, "4"]
```

实现数组的深拷贝：

slice

```
var arr = ['a', 'b', 'c'];
var arrCopy = arr.slice(0);
arrCopy[0] = 'test'
console.log(arr); // ["a", "b", "c"]
console.log(arrCopy); // ["test", "b", "c"]
```

concat

```
var arr = ['a', 'b', 'c'];
var arrCopy = arr.concat();
arrCopy[0] = 'test'
console.log(arr); // ["a", "b", "c"]
console.log(arrCopy); // ["test", "b", "c"]
```

实现对象的深拷贝：

```
function deepCopy(obj) {
  var result = {};
  for( var key in obj) {
	  typeof obj[key] === 'object' ? result[key] = deepCopy(obj[key]): result[key] = obj[key];
  }
  return result;
}
```

