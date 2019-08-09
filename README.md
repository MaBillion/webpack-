## 2019-07-31   
> 关于css的 deep 用法    
```
当引用第三方库时，当我们想修改某些样式，但又不想影响全局样式时，就可用到 deep
语法：
/deep/ .dom {
    color: #ff0000;
}
```

## 2019-08-09    
> URLSearchParams() 用法   

#### 语法    
* URLSearchParams.append()
    - 插入一个指定的键/值对作为新的搜索参数。
* URLSearchParams.delete()
    - 从搜索参数列表里删除指定的搜索参数及其对应的值。
* URLSearchParams.entries()
    - 返回一个iterator可以遍历所有键/值对的对象。
* URLSearchParams.get()
    - 获取指定搜索参数的第一个值。
* URLSearchParams.getAll()
    - 获取指定搜索参数的所有值，返回是一个数组。
* URLSearchParams.has()
    - 返回 Boolean 判断是否存在此搜索参数。
* URLSearchParams.keys()
    - 返回iterator 此对象包含了键/值对的所有键名。
* URLSearchParams.set()
    - 设置一个搜索参数的新值，假如原来有多个值将删除其他所有的值。
* URLSearchParams.sort()
    - 按键名排序。
* URLSearchParams.toString()
    - 返回搜索参数组成的字符串，可直接使用在URL上。
* URLSearchParams.values()
    - 返回iterator 此对象包含了键/值对的所有值。   

> 例子   
```
var paramsString = "q=URLUtils.searchParams&topic=api"
var searchParams = new URLSearchParams(paramsString);

for (let p of searchParams) {
  console.log(p);
}

searchParams.has("topic") === true; // true
searchParams.get("topic") === "api"; // true
searchParams.getAll("topic"); // ["api"]
searchParams.get("foo") === ""; // true
searchParams.append("topic", "webdev");
searchParams.toString(); // "q=URLUtils.searchParams&topic=api&topic=webdev"
searchParams.set("topic", "More webdev");
searchParams.toString(); // "q=URLUtils.searchParams&topic=More+webdev"
searchParams.delete("topic");
searchParams.toString(); // "q=URLUtils.searchParams"
```    

> 目前兼容性 ie 完全不支持（edge支持） 其他浏览器支持度不错