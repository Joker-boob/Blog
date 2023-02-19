---
title: js中的各种遍历
tags: [js,前端]
categories: JS
cover: https://th.bing.com/th/id/R.fc32f16276c6e6459d579924c0456e11?rik=2K8yVgHO12Is6w&riu=http%3a%2f%2f3.bp.blogspot.com%2f-PTty3CfTGnA%2fTpZOEjTQ_WI%2fAAAAAAAAAeo%2fKeKt_D5X2xo%2fw1200-h630-p-k-nu%2fjs.jpg&ehk=2PrB9111t3zKW%2f42wxMGGN6YYYRN3%2bgtuPOWner1T8M%3d&risl=&pid=ImgRaw&r=0
top_img: https://blog-img-joker.oss-cn-nanjing.aliyuncs.com/blogImg/2022/11/24/14/12171669270661640.webp
---
```javascript
let arr = ['Joker','Pink','north','Red']
```

<a name="16f2fd8d"></a>

## for 循环

**普通的for循环，也是最常用到的**

```javascript
for(let i = 0;i<arr.length;i++){
	console.log(arr[i]);
}
```

<a name="5b31cbae"></a>

## for in

**for in 循环 用于遍历对象的属性**
**如果用其来遍历数组 key值则为下标**

```javascript
let obj = {
    age: 18, name: "Joker", sayHello() {
        console.log("Hello")
    }
};
for (let key in obj) {
    console.log(`key:${key},value:${obj[key]}`);
}
```

<a name="4c0bdc05"></a>

## for of

**for of 语句循环遍历可迭代对象的值。such as:数组，字符串，节点列表......**

```javascript
for (let item of arr) {
	console.log(item)
}
```

<a name="forEach"></a>

## forEach

**ES5数组自带的循环，主要是用来遍历数组，性能比for循环还弱**

```javascript
arr.forEach((item,index,arr)=>{
	console.log(`key:${index},value:${item}`)
})
```

<a name="map"></a>

## map

**用法与forEach类同，但参数中的函数支持返回值**
**返回值是一个新的数组，其每项就是参数中的函数返回的值**

```javascript
arr.map((value, index, array) => {
	return value === 123;
});
```

<a name="filter"></a>

## filter

**用法与forEach类同，但参数中的函数支持返回值**
**返回值为一个新的数组，如果参数中的函数返回为真 则会将这一项push进新的数组当中，为假或没有返回，则不会**

```javascript
arr.filter((value, key) => {
	return value === 123;//[]
	return value.indexOf('o') !== -1;//['Joker', 'north']
})
```

<a name="includes"></a>

## includes

**检测数组当中是不是存在某个元素**

```javascript
console.log(arr.includes('Joker'));//true
console.log(arr.includes('111'));//false
console.log(arr.includes('north'));//true
```

<a name="find"></a>

## find

**寻找第一个符合条件的元素**

```javascript
console.log(arr.find((value, key, arr) => {
    return value.indexOf('o') !== -1;
}));//Joker
```

<a name="findIndex"></a>

## findIndex

**寻找第一个符合条件元素的索引**

```javascript
console.log(arr.findIndex((value, key, arr) => {
    return value.indexOf('o') !== -1;
}));//0
```

<a name="some"></a>

## some

**数组中是不是有值符合某个条件**
**所有值中有一个符合条件就不继续执行，返回true**

```javascript
console.log(arr.some((value, key, arr) => {
	return value.indexOf('o') !== -1;
}));//true
```

<a name="every"></a>

## every

**数组中是不是所有值符合某个条件**
**所有值中有一个不符合条件就不继续执行，返回false**

```javascript
console.log(arr.every((value, key, arr) => {
	return value.indexOf('o') !== -1;
}));//false
```
