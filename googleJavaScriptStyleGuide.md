#####1.使用空格而不是Tab

```
// bad
function foo() {
∙∙∙∙let name;
}

// bad
function bar() {
∙let name;
}

// good
function baz() {
∙∙let name;
    
```

#####2.必须写分号，不允许让 JS 自动插入分号

```
// bad
let luke = {}
let leia = {}
[luke, leia].forEach(jedi => jedi.father = 'vader')
// good
let luke = {};
let leia = {};
[luke, leia].forEach((jedi) => {
  jedi.father = 'vader';
});
```

#####3.目前不要使用 ES 6 模块语法（import export 等）

```
// Don't do this kind of thing yet:
//------ lib.js ------
export function square(x) {
    return x * x;
}
export function diag(x, y) {
    return sqrt(square(x) + square(y));
}

//------ main.js ------
import { square, diag } from 'lib';
```

#####4.不鼓励垂直对齐冒号

```
// bad
{
  tiny:   42,  
  longer: 435, 
};
// good
{
  tiny: 42, 
  longer: 435,
};
```

#####5.不要用 var

```
// bad
var example = 42;
// good
let example = 42;
```

#####6.尽量用箭头函数

```
// bad
[1, 2, 3].map(function (x) {
  const y = x + 1;
  return x * y;
});

// good
[1, 2, 3].map((x) => {
  const y = x + 1;
  return x * y;
});
```

#####7.使用模板字符串代替字符串拼接

```
// bad
function sayHi(name) {
  return 'How are you, ' + name + '?';
}

// bad
function sayHi(name) {
  return ['How are you, ', name, '?'].join();
}

// bad
function sayHi(name) {
  return `How are you, ${ name }?`;
}

// good
function sayHi(name) {
  return `How are you, ${name}?`;
}
```

#####8.不要在字符串行尾加 \ 来换行

```
// bad (sorry, this doesn't show up well on mobile)
const longString = 'This is a very long string that \
    far exceeds the 80 column limit. It unfortunately \
    contains long stretches of spaces due to how the \
    continued lines are indented.';
// good
const longString = 'This is a very long string that ' + 
    'far exceeds the 80 column limit. It does not contain ' + 
    'long stretches of spaces since the concatenated ' +
    'strings are cleaner.';
```

#####9.优先使用 for...of 而不是 for 循环

#####10.不要使用 eval

```
// bad
let obj = { a: 20, b: 30 };
let propName = getPropName();  // returns "a" or "b"
eval( 'var result = obj.' + propName );
// good
let obj = { a: 20, b: 30 };
let propName = getPropName();  // returns "a" or "b"
let result = obj[ propName ];  //  obj[ "a" ] is the same as obj.a
```

#####11.常量必须全大写，并用下划线连接单词

```
// bad
const numberFive = 5;
// good
const NUMBER_FIVE = 5;
```

#####12.一行只声明一个变量

```
// bad
let a = 1, b = 2, c = 3;
// good
let a = 1;
let b = 2;
let c = 3;
```

#####13.使用单引号，不要使用双引号

```
// bad
let directive = "No identification of self or mission."
// bad
let saying = 'Say it ain\u0027t so.';
// good
let directive = 'No identification of self or mission.';
// good
let saying = `Say it ain't so`;
```