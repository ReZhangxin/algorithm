# 数组的标准定义：一个储存元素的线性集合

## 字符串转成数组

`String.prototype.split()`

> 使用指定的分隔符字符串将一个String对象分割成字符串数组

```js
"a b c d".split(' ') ;//["a", "b", "c", "d"]
```

## 对整个数组进行操作

将一个数组赋值给另一个数组

```js
var nums = [];
for(var i=0;i<10;i++){
    nums[i] = i+1;
}
var samenums = nums;
// 数组的浅拷贝
nums[0] = 100;
samenums[0];//100

//数组的深拷贝
function coby(arr1,arr2){
    for(var i = 0; i<arr1.length; i++){
        arr2[i] = arr1[i];
    }
}
var samenums = [];
coby(nums,samenums)
nums[0] = 100;
samenums[0];//1
```

## 数组转化为字符串

> 有两种方法：`join()` `toString()`

```js
var names = ['xin','fei']
undefined
names.join('')
"xinfei"
names.join(' ')
"xin fei"
names.join()
"xin,fei"
names.toString()
"xin,fei"
```

## 迭代器

> 迭代器方法：就是对数组中的每个元素都应用一个函数，
> 可以返回一个值、一组值或者一个新的数组

### 不生成新数组的迭代方法

> 不会产生任何新的数组，要么对数组的每个元素执行某种操作，
> 要么返回一个值。

- `forEach()`

```js
function square(num){
    console.log(num*num);
}
var nums = [1,2,3,4,5];
nums.forEach(square);
```

- `reduce()` 方法对累加器和数组中的每个元素 (从左到右)应用一个函数，将其减少为单个值。

```js
var total = [0, 1, 2, 3].reduce(function(sum, value) {
  return sum + value;
}, 0);
// total is 6

var flattened = [[0, 1], [2, 3], [4, 5]].reduce(function(a, b) {
  return a.concat(b);
}, []);
// flattened is [0, 1, 2, 3, 4, 5]
```

### 生成新数组的迭代器方法

- `map()` 返回一个**新**的数组

```js
var a = [1,2,3];
var b = a.map(a=> a+1);
b;// [2, 3, 4]
a; //[1, 2, 3]
b[0]=5;
b;//[5, 3, 4]
a;// [1, 2, 3]
```

- `filter()` 对数组中所有元素执行函数，结果为true的时候返回新的数组

```js
function isBigEnough(value) {
  return value >= 10;
}

var filtered = [12, 5, 8, 130, 44].filter(isBigEnough);

// filtered is [12, 130, 44]

// ES6 way

const isBigEnough = value => value >= 10;

let [...spraed]= [12, 5, 8, 130, 44];

let filtered = spraed.filter(isBigEnough);

// filtered is [12, 130, 44]
```

## 二维和多维数组

