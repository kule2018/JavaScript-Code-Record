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
//for-in语句是一种精准的迭代语句可以用来美枚举对象的属性
for(let propName in window) {
    document.wirte(propName)
}
```
