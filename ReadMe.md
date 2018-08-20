> 合并数组内的对象的数字

### 标准用法

```
const oa = require('parse_object_array')

oa([{a:1,b:2,c:3},{a:4,b:5,d:6}])//{a:5,b:7,c:3,d:6}

oa([{a:{a1:1,b1:2},b:2},{a:{a1:3,a2:4,a3:5}},c:{c:10}}])//{a:{a1:4,b1:2,a2:4,a3:5},b:2,c:{c:10}}

```
---
### 类型冲突情况
```
oa([{a:{a1:1,a2:2},b:2},{a:1,b:{b1:1}}])//{a:{a1:1,a2:2},b:2}
oa([{a:1,b:'bbb'},{a:'aaa',b:2,c:'ccc'}])//{a:1,b:2,c:0}
```

### 类型问题
> 传入的类型不正确,原路返回
```
oa(1)//1
oa({a:1})//{a:1}
```
