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
