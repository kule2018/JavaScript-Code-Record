JavaScript Code Record
===
概述：记录整理常用JavaScript代码以备后续项目需要，代码可能参考网上常用代码。实时更新中...

### 1.将对象数组按照传入的属性值进行分组
```javascript
function groupBy(array, f) {
    const groups = {};
    array.forEach(function (o) {
        const group = JSON.stringify(f(o));
        groups[group] = groups[group] || [];
        groups[group].push(o);
    });
    return Object.keys(groups).map(function (group) {
        return groups[group];
    });
}
```

使用方法示例：
```javascript
const sorted = groupBy(data, function (item) {
    return [item.name]
});
```

### 2.字符串与数组的相互转换
```javascript
// 数组转字符串
array.join(',')
// 字符串转数组
string.split(',')
```

### 3.求两个数组的并、交、差
```javascript
// 并集
let union = a.concat(b.filter(v => !a.includes(v))) // [1,2,3,4,5]
// 交集
let intersection = a.filter(v => b.includes(v)) // [2]
// 差集
let difference = a.concat(b).filter(v => a.includes(v) && !b.includes(v)) // [1,3]
```

### 4.for-in语句的使用
```javascript
//for-in语句是一种精准的迭代语句可以用来枚举对象的属性
for(let propName in window) {
    document.wirte(propName)
}
```

### 5.数组的深拷贝(一度的深拷贝)
```javascript
//concat(arr1,arr2,...,arrn) 方法用于连接两个或多个数组。
//该方法不会改变现有的数组，而仅仅会返回被连接数组的一个副本。
array.concat();

//slice(start,end)方法返回一个新的数组，该方法可从已有的数组中返回选定的元素
array.slice(0,array.length);

//ES6新方法
let [...arr1] = arr;
```

### 6.数组的插入、删除和替换
```javascript
//splice()方法
array.splice(0,2)                     //指定两个参数，要删除的第一项位置和要删除的项数
array.splice(2,0,'test')              //指定3个参数，起始位置、0（要删除的项数）和要插入的项
array.splice(2,1,'test')              //指定3个参数，起始位置、要删除（替换）的项数和要插入的项
```

### 7.数组的迭代、归并方法
```javascript
//迭代函数
//调用格式
array.every/filter/forEach/map/some(function(item,index,array){
    //...
})
//作用
every():对数组中的每一项运行给定函数，如果该函数对每一项都返回true,则返回true;
some():对数组中的每一项运行给定函数，如果该函数对任一项返回true,则返回true;
filter():对数组中的每一项运行给定函数，返回该函数会返回true的项组成的数组;
forEach():对数组中的每一项运行给定函数。该方法没有返回值;
map():对数组中的每一项运行给定函数，返回每次函数调用的结果组成的数组;

//归并函数
//调用格式
array.reduce/reduceRight(function(prev,cur,index,array){
    //...
},origin);
//作用
reduce():从第一项开始迭代数组的所有项，构建一个最终返回的值。
reduceRight():从最后一项开始迭代数组的所有项，构建一个最终返回的值。
```

### 8.对象的深拷贝(一度的深拷贝)
```javascript

```
