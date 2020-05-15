### 循环
最基本的for循环和while循环
#### for-Each和map
这两个函数都是遍历Array对象，唯一的区别是返回值不同。
- map返回的是一个经过函数处理后的新数组
- for-Each返回的是undefinend，不会改变原数组。
```
let x = array1.forEach((valuse, index, array1)=>{...;return value},thisArg);
console.log(x);//undefiend
```
- for-Each不能break和return
```
let y = array2.map((vlaue, index) => {
    cosnole.log(value);
    return value+10
})
console.log(y);//会返回一个加10的新数组
```
#### for-in
每次都记不住for-in和for-of到底哪个是遍历键，哪个遍历值。

`for-in==属性（shuxing里有in，所以是键）`
注意点：
- for-in的顺序是按执行的顺序来确定的，如果严格需要顺序就使用其他的循环
- for-in遍历的是可枚举属性，如果通过definePorpety方法设置为不可枚举属性那么就不能遍历
- 不想遍历原型方法和属性的话，可以在循环内部判断一下,hasOwnPropery方法可以判断某属性是否是该对象的实例属性
#### for-of
for-of遍历的是就有itrater接口属性值
#### 为什么要for-of循环
1. 由于for-Each不能break、return
2. 因为for-in遍历的顺序不确定。访问的数据功能不够友好
   - 它不仅遍历数组中的元素，还会遍历自定义的属性，
   - 甚至原型链上的属性都被访问到。而且
#### for-of的优点
1. 简洁方便
2. 改进了前面两种的不足
3. 支持类数组，字符串，nodeList，set，map，类型化数组（TypedArray）
#### for-of缺点
for-of循环不支持普通对象，但如果你想迭代一个对象的属性，你可以用for-in循环（这也是它的本职工作）或内建的Object.keys()方法：
```
for (var key of Object.keys(someObject)) {
  console.log(key + ": " + someObject[key]);
}
```

参考：
- [知乎文章](https://zhuanlan.zhihu.com/p/30328361)
- [MDN](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for...of)