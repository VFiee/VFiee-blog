# Javascript面试指南

## 概念问题

### 😃请先做一下自我介绍~

### Javascript的数据类型都有哪些,有什么区别?

### 说一下你工作中常用的ES6

### 描述一下Set和Map数据结构

### WeakMap和Map的区别?

### let const var之间的区别?

### 为什么var可以重复声明?

### 描述一下你对Promise的理解,Promise的原理是什么?

### CommonJS中的require/exports 和 ES6中的import/export的区别?

### 描述一下Javascript的事件模型?

### 描述一下你对闭包的了解?

### == 和 === 有什么区别?

### 什么是跨域? 跨域的解决方法有哪些?

### 描述一下localstorage sessionStorage cookie以及他们之间的区别?




## 实现问题

### 怎么判断两个对象相等?

### call,apply,bind相同点和不同点?

### 浅拷贝和深拷贝的区别? 
[掘进资源](https://juejin.im/post/5b5dcf8351882519790c9a2e)

### 函数内部 arguments 变量有哪些特性,有哪些属性,如何将它转换为数组

### 描述一下节流和防抖的应用场景及区别

### 创建一个长度为5的空数组,生成一个(2~32)之间的随机证书rand,递归将随机整数rand插入arr,如果arr存在则重新生成并插入,输出一个长度为5且内容不重复的arr

```js
// 创建一个长度为5的空数组
let arr = new Array(5);
// 生成一个(2~32)之间的随机证书rand
let randomInt = getRandomInt(2,32);
// 递归将随机整数rand插入arr,如果arr存在则重新生成并插入,输出一个长度为5且内容不重复的arr
insertArr(getRandomInt(2,32));

function getRandomInt(min,max) {
    min = Math.ceil(min);
    max = Math.floor(max);
    return Math.floor(Math.random()*(max-min)) + min;
}

function insertArr(num){
    arr = arr.flat();
    if(arr.includes(num)){
        insertArr(getRandomInt(2,32));
        return;
    }
    arr.push(num);
    if(arr.length===5){
        return arr;
    }
    inserrtArr(getRandomInt(2,32));
}
```