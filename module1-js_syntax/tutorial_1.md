# 模块1：JavaScript语法简介

> JavaScript是Web编程语言，绝大多数网站都使用Javascript，所有现代Web浏览器（无论是桌面、平板还是手机浏览器）都包含JavaScript解释器，这让JavaScript成为有史以来部署最广泛的编程语言。
> 
> Node.js让浏览器之外的JavaScript编程成为可能。Node的巨大成功意味着JavaScript如今也是软件开发者最常用的编程语言。
>
> JavaScript这个名字相当具有误导性；除了表面上语法相似，它与Java是完全不同的两门语言。JavaScript经历了很长时间才从一门脚本语言成长为一门高效健壮的通用语言，适合开发代码量巨大的重要软件工程和项目。
> 
> --JavaScript权威指南

JavaScript由ECMA公司维护。因此，讨论JavaScript这门语言的标准及版本时，人们使用EMCAScript (ES)这个名字。重要版本包括ES5 (2010)，ES6 (2015)。ES2015后，版本代号改为ES加年份。最新标准版本为ES2022。ES6做出了许多重要更新。除了少数特殊情况，应当尽量遵循和使用ES6及以后版本的规范和特性。

## 词法结构、类型、值、变量、操作符

~~~javascript
/**
 * literals, or fixed values
 * 字面量
*/
3.14
'js'
/pattern/ // regular expressions

true, false, null, undefined, this

[1, 2, 'a', [{f: console.log}]]

/**
 * variables: const, let, var (avoid using var in es6 and later versions of javascript)
 * 变量声明和运算
*/
const a = 'a'; let b = [1, 2, 3] // use semicolon when more than one operation are placed in the same line, the last semicolon can be omitted
let smith = 1, jack = undefined;
// or let smith = 1, jack (default is undefined)
// or let [smith, jack] = [1, undefined]
// do not do this: let smith, jack = 1, undefined
jack = 1
jack += smith // jack = jack + smith
jack **= 2
jack /= 4
smith = jack % 2
let someBool = !(jack === 1) && (smith >= 100) || (undefined) // '==' performs automatic type conversion. Try to use '===' as often as possible.
let binary = 4 // binary 100
binary = binary << 2 // binary 10000 <=> 16
// a = 'A' raises an exception: Uncaught TypeError: Assignment to constant variable.
let c = binary ++ // c = 17, side effect: binary += 1
smith = 'smith';
jack = 'jack';
let mike = smith + ' ' + jack // 'smith jack'
~~~

## 分支，循环

~~~javascript
// calculate fibonacci, using iteration and memoization
let [fibonacci_n, fibonacci_n_1, fibonacci_n_2] = [0, 0, 0];
for(let n=1; n<=100; n++) {
    if(n === 1) {
        fibonacci_n = 1;
        continue;
    }
    else if(n === 2) {
        fibonacci_n_1 = fibonacci_n
        fibonacci_n = 1;
        continue;
    }
    else {
        fibonacci_n_2 = fibonacci_n_1
        fibonacci_n_1 = fibonacci_n
        fibonacci_n = fibonacci_n_1 + fibonacci_n_2
        if(n % 10 === 0) {
            console.log(`n = ${n}, fibonacci = ${fibonacci_n}`);
        }
    }
}

let m = 0;
while(true) {
    if(m>9) break;
    switch(m%2) {
        case 0:
            console.log(m + ' is even'); // auto type conversion, number m to string
            break;
        case 1:
            console.log(m + ' is odd');
            break;
        default:
            break;
    }
    m++;
}
// switch in js is not as efficient as equivalents in C++ or Java. Try to use alternatives like hash tables (objects) instead.

// let ... of ITERABLE
for(let i of [1,2,3]) console.log(i);

// let ... in OBJECT
let hash_table = {'a': 1, 'b': 2, 'c': 3};
for(let a in hash_table) console.log(`${a}: ${hash_table[a]}`);
~~~


## 函数和闭包

## 对象

## 类

## 异步