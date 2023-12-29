# JavaScript

## 概念

### 运算符

JavaScript 拥有如下类型的运算符：

- [赋值运算符（Assignment operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#赋值运算符)
- [比较运算符（Comparison operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#比较运算符)
- [算数运算符（Arithmetic operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#算术运算符)
- [位运算符（Bitwise operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#位运算符)
- [逻辑运算符（Logical operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#逻辑运算符)
- [字符串运算符（String operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#字符串运算符)
- [条件（三元）运算符（Conditional operator）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#条件（三元）运算符)
- [逗号运算符（Comma operator）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#逗号操作符)
- [一元运算符（Unary operators）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#一元操作符)
- [关系运算符（Relational operator）](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#关系运算符)

### 操作符

包括在运算符中，操作符基于操作数进行返回结果，如操作符`delete`、`typeof`、`void`

### 表达式

表达式是一组代码的集合，它返回一个值。每一个合法的表达式都能计算成某个值，但从概念上讲，有两种类型的表达式：有副作用的（比如赋值）和单纯计算求值的。

表达式 x=7 是第一类型的一个例子。该表达式使用=运算符将值 7 赋予变量 x。这个表达式自己的值等于 7。

代码 3 + 4 是第二个表达式类型的一个例子。该表达式使用 + 运算符把 3 和 4 加到一起但并没有把结果（7）赋值给一个变量。

- JavaScript 有以下表达式类型：
  - 算数：得出一个数字，例如 3.14159。（通常使用[算数运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#算术运算符)）
  - 字符串：得出一个字符串，例如，"Fred" 或 "234"。（通常使用[字符串运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#字符串运算符)。）
  - 逻辑值：得出 true 或者 false。（经常涉及到[逻辑运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#逻辑运算符)。）
  - 基本表达式：javascript 中基本的关键字和一般表达式。
  - 左值表达式：分配给左值。

### 关键字

Javascript关键字(Reserved Words)是指在Javascript语言中有特定含义，成为Javascript语法中一部分的那些字。Javascript关键字是不能作为变量名和函数名使用的。使用Javascript关键字作为变量名或函数名，会使Javascript在载入过程中出现编译错误。

## 语法和数据类型

### 声明

**JavaScript 有三种声明方式。**

- [`var`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var)

  声明一个变量，可选初始化一个值。

- [`let`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/let)

  声明一个块作用域的局部变量，可选初始化一个值。

- [`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const)

  声明一个块作用域的只读常量。



**var**

var无论在何处声明变量，都会在执行任何代码之前进行处理。

用 `var` 声明的变量的作用域是它当前的执行上下文及其闭包（嵌套函数），或者对于声明在任何函数外的变量来说是全局。使用 `var` 重复声明 JavaScript 变量并不会抛出错误（即使在严格模式 (strict mode) 下），同时，变量也不会丢失其值，直到调用其他的赋值操作。



`变量提升`：使用 `var` 声明的变量将在任何代码执行前被创建，这被称为变量提升。这些变量的初始值为 `undefined`。



**let**

**`let`** 允许你声明一个作用域被限制在[`块`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/block)作用域中的变量、语句或者表达式。与 [`var`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/var) 关键字不同的是，`var` 声明的变量作用域是全局或者整个函数块的。 `var` 和 `let` 的另一个重要区别，`let` 声明的变量不会在作用域中被提升，它是在编译时才初始化

就像 [`const`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/const#描述) 一样，`let` 不会在全局声明时（在最顶层的作用域）创建 [`window`](https://developer.mozilla.org/zh-CN/docs/Web/API/Window) 对象的属性。



作用域规则：

**`let`** 声明的变量作用域只在其声明的块或子块内部，这一点，与 **`var`** 相似。二者之间最主要的区别在于 **`var`** 声明的变量的作用域是整个封闭函数。

重复声明：

在同一个函数或块作用域中重复声明同一个变量会抛出 [`SyntaxError`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/SyntaxError)。



`暂时性死区`：从一个代码块的开始直到代码执行到声明变量的行之前，`let` 或 `const` 声明的变量都处于“暂时性死区”



**const**

其他规则和`let`一致，但常量的值是无法（通过重新赋值）改变的，也不能被重新声明。



你可以使用[解构赋值](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)将[对象字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#对象字面量)的属性绑定到变量。就像这样 `let { bar } = foo`。这会创建一个名为 `bar` 的变量，并且将 `foo` 对象中属性名与之相同的属性的值赋给它。



### 变量

在应用程序中，使用变量来作为值的符号名。变量的名字又叫做[标识符](https://developer.mozilla.org/zh-CN/docs/Glossary/Identifier)，其需要遵守一定的规则。

一个 JavaScript 标识符必须以字母、下划线（_）或者美元符号（$）开头；后续的字符也可以是数字（0-9）。因为 JavaScript 语言是区分大小写的，所以字母可以是从“A”到“Z”的大写字母和从“a”到“z”的小写字母。



你可以使用大部分 ISO 8859-1 或 Unicode 编码的字符作标识符，例如 å 和 ü（详情可查看[这篇博客文章](https://mathiasbynens.be/notes/javascript-identifiers-es6)）。你也可以使用 [Unicode 转义字符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Lexical_grammar#string_literals)作标识符。

合法的标识符示例：`Number_hits`、`temp99`、`$credit` 和 `_name`。



### 函数提升

对于函数来说，只有函数声明会被提升到顶部，而函数表达式不会被提升。

```js
/* 函数声明 */

foo(); // "bar"

function foo() {
  console.log("bar");
}

/* 函数表达式 */

baz(); // 类型错误：baz 不是一个函数

var baz = function () {
  console.log("bar2");
};
```

### 数据类型

最新的 ECMAScript 标准定义了 8 种数据类型：

- 七种基本数据类型：
  - 布尔值（Boolean），有 2 个值分别是：`true` 和 `false`。
  - null，一个表明 null 值的特殊关键字。JavaScript 是大小写敏感的，因此 `null` 与 `Null`、`NULL`或变体完全不同。
  - undefined，和 null 一样是一个特殊的关键字，undefined 表示变量未赋值时的属性。
  - 数字（Number），整数或浮点数，例如： `42` 或者 `3.14159`。
  - 任意精度的整数（BigInt），可以安全地存储和操作大整数，甚至可以超过数字的安全整数限制。
  - 字符串（String），字符串是一串表示文本值的字符序列，例如：`"Howdy"`。
  - 代表（Symbol，在 ECMAScript 6 中新添加的类型）。一种实例是唯一且不可改变的数据类型。
- 以及对象（Object）。



### 数字转换为字符串

在包含的数字和字符串的表达式中使用加法运算符（+），JavaScript 会把数字转换成字符串。例如，观察以下语句：

```js
x = "The answer is " + 42; // "The answer is 42"
y = 42 + " is the answer"; // "42 is the answer"
```

在涉及其他运算符时，JavaScript 语言不会把数字变为字符串。例如：

```js
"37" - 7; // 30
"37" + 7; // "377"
```



### 字面量

在 JavaScript 中，你可以使用各种字面量。这些字面量是脚本中按字面意思给出的固定的值，而不是变量

- [数组字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#数组字面量)
- [布尔字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#布尔字面量)
- [数字字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#数字字面量)
- [对象字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#对象字面量)
- [RegExp 字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#regexp_字面量)
- [字符串字面量](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Grammar_and_types#字符串字面量)

**在字符串中使用的特殊字符**

作为一般字符的扩展，你可以在字符串中使用特殊字符，如下例所示。

| 字符 | 意思            |
| ---- | --------------- |
| \0   | Null 字节       |
| \b   | 退格符          |
| \f   | 换页符          |
| \n   | 换行符          |
| \r   | 回车符          |
| \t   | Tab (制表符)    |
| \v   | 垂直制表符      |
| \'   | 单引号          |
| \"   | 双引号          |
| \\   | 反斜杠字符（\） |



**模版字面量**

模板字面量是用反引号（`）分隔的字面量，允许多行字符串、带嵌入表达式的字符串插值和一种叫带标签的模板的特殊结构。



模板字面量有时被非正式地叫作`模板字符串`，因为它们最常被用作字符串插值（通过替换占位符来创建字符串）。然而，带标签的模板字面量可能不会产生字符串——它可以与自定义标签函数一起使用，来对模板字面量的不同部分执行任何操作。



若要转义模板字面量中的反引号（`），需在反引号之前加一个反斜杠（\）。

```js
`\`` === "`"; // true
```

美元符号 `$` 也可以被转义，来阻止插值。

```js
`\${1}` === "${1}"; // true
```



使用模板字面量，可以做到多行字符串：

```js
console.log(`string text line 1
string text line 2`);
// "string text line 1
// string text line 2"
```



字符串插值：

有了模板字面量，就可以通过使用占位符 `${}` 嵌入待替换的表达式，从而避免串联运算符，并提高代码的可读性：

```js
const a = 5;
const b = 10;
console.log(`Fifteen is ${a + b} and
not ${2 * a + b}.`);
// "Fifteen is 15 and
// not 20."
```



带标签的模板：

*带标签的*模板是模板字面量的一种更高级的形式，它允许你使用函数解析模板字面量。标签函数的第一个参数包含一个字符串数组，其余的参数与表达式相关。你可以用标签函数对这些参数执行任何操作，并返回被操作过的字符串（或者，也可返回完全不同的内容，见下面的示例）。用作标签的函数名没有限制。

```js
const person = "Mike";
const age = 28;

function myTag(strings, personExp, ageExp) {
  const str0 = strings[0]; // "That "
  const str1 = strings[1]; // " is a "
  const str2 = strings[2]; // "."

  const ageStr = ageExp > 99 ? "centenarian" : "youngster";

  // 我们甚至可以返回使用模板字面量构建的字符串
  return `${str0}${personExp}${str1}${ageStr}${str2}`;
}

const output = myTag`That ${person} is a ${age}.`;

console.log(output);
// That Mike is a youngster.
```

## 条件判断与错误处理

### 条件判断语句

> 条件判断语句指的是根据指定的条件所返回的结果（真或假或其他预定义的），来执行特定的语句。JavaScript 支持两种条件判断语句：`if...else`和`switch`。



**if...else 语句**

当一个逻辑条件为真，用 if 语句执行一个语句。当这个条件为假，使用可选择的 else 从句来执行这个语句。if 语句如下所示：

```js
if (condition) {
  statement_1;
} else {
  statement_2;
} //推荐使用严格的语句块模式，语句 else 可选
```

条件可以是任何返回结果被计算为 true 或 false 的表达式。如果条件表达式返回的是 true，statement_1 语句会被执行；否则，statement_2 被执行。statement_1 和 statement_2 可以是任何语句，甚至你可以将另一个 if 语句嵌套其中。



你也可以组合语句通过使用 `else if` 来测试连续多种条件判断，就像下面一样：

```js
if (condition_1) {
  statement_1;
} else if (condition_2) {
  statement_2;
} else if (condition_n_1) {
  statement_n;
} else {
  statement_last;
}
```



错误的值：

- `false`
- `undefined`
- `null`
- `0`
- `NaN`
- 空字符串（`""`）

当传递给条件语句所有其他的值，包括所有对象会被计算为真。



**switch 语句**

`switch` 语句允许一个程序求一个表达式的值并且尝试去匹配表达式的值到一个 `case` 标签。如果匹配成功，这个程序执行相关的语句。`switch` 语句如下所示：

```js
switch (expression) {
   case label_1:
      statements_1
      [break;]
   case label_2:
      statements_2
      [break;]
   ...
   default:
      statements_def
      [break;]
}
```

程序首先查找一个与 `expression` 匹配的 `case` 语句，然后将控制权转移到该子句，执行相关的语句。如果没有匹配值，程序会去找 `default` 语句，如果找到了，控制权转移到该子句，执行相关的语句。如果没有找到 `default`，程序会继续执行 `switch` 语句后面的语句。`default` 语句通常出现在 switch 语句里的最后面，当然这不是必须的。

`可选的 break` 语句与每个 `case` 语句相关联，如果没有`break`可以跳出 `switch` 并且继续执行 `switch` 后面的语句。如果 break 存在，则程序将不会继续执行 switch 语句后的语句。



### 异常处理语句

**throw 语句**

使用`throw`语句抛出一个异常。当你抛出异常，你规定一个含有值的表达式要被抛出。

```js
throw expression;
```



**try...catch 语句**

`try...catch` 语句有一个包含一条或者多条语句的 try 代码块，0 个或 1 个的`catch`代码块，catch 代码块中的语句会在 try 代码块中抛出异常时执行。换句话说，如果你在 try 代码块中的代码如果没有执行成功，那么你希望将执行流程转入 catch 代码块。如果 try 代码块中的语句（或者`try` 代码块中调用的方法）一旦抛出了异常，那么执行流程会立即进入`catch` 代码块。如果 try 代码块没有抛出异常，catch 代码块就会被跳过。`finally` 代码块总会紧跟在 try 和 catch 代码块之后执行，但会在 try 和 catch 代码块之后的其他代码之前执行。



下面的例子通过传一个数字参数来寻找月份，如果寻找到则返回月份的英文，否则抛出错误。`finally`块则是否抛出异常都会执行

```js
function getMonthName(mo) {
  mo = mo - 1; // Adjust month number for array index (1 = Jan, 12 = Dec)
  var months = [
    "Jan",
    "Feb",
    "Mar",
    "Apr",
    "May",
    "Jun",
    "Jul",
    "Aug",
    "Sep",
    "Oct",
    "Nov",
    "Dec",
  ];
  if (months[mo]) {
    return months[mo];
  } else {
    throw "InvalidMonthNo"; //throw keyword is used here
  }
}

try {
  // statements to try
  monthName = getMonthName(123); // function could throw exception
} catch (e) {
  monthName = "unknown";
  console.log(e); // InvalidMonthNo
} finally {
  console.log('无论是否抛出错误都会执行')
}
```



如果`finally`块返回一个值，该值会是整个`try-catch-finally`流程的返回值，不管在`try`和`catch`块中语句返回了什么，意味着`finally`返回值的优先级更高。

用`finally`块覆盖返回值也适用于在`catch`块内抛出或重新抛出的异常：

```js
function f() {
  try {
    throw "bogus";
  } catch (e) {
    console.log('caught inner "bogus"');
    throw e; // 会暂时挂起，等待所有区块执行完成
  } finally {
    return false; // 会覆盖之前的throw
  }
  //最后执行了  return false
}

try {
  f();
} catch (e) {
  console.log('错误执行');
}

// 最后打印 caught inner "bogus"
```



根据错误类型，你也许可以用`错误对象`的'`name`'和'`message`'获取更精炼的信息。'`name`'提供了常规的错误类（如 '`DOMException`' 或 '`Error`'），而'message'通常提供了一条从错误对象转换成字符串的简明信息

```js
function f() {
  try {
    throw new Error('The message');
  } catch (e) {
	throw e;
  }
}

try {
  f();
} catch (e) {
  console.log(e.name); //Error
  console.log(e.message); // The message
}

```

## 循环与迭代

### for 语句

一个 [`for`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/for) 循环会一直重复执行，直到指定的循环条件为 false。JavaScript 的 for 循环，和 Java、C 的 for 循环，是很相似的。一个 for 语句是这个样子的：

```js
for ([initialExpression]; [condition]; [incrementExpression]){
   statement
}
```

当一个 `for` 循环执行的时候，会发生以下过程：

1. 如果有初始化表达式 `initialExpression`，它将被执行。这个表达式通常会初始化一个或多个循环计数器，但语法上是允许一个任意复杂度的表达式的。这个表达式也可以声明变量。
2. 计算 `condition` 表达式的值。如果 `condition` 的值是 true，循环中的语句会被执行。如果 `condition` 的值是 false，`for` 循环终止。如果 `condition` 表达式整个都被省略掉了，condition 的值会被认为是 true。
3. 循环中的 `statement` 被执行。如果需要执行多条语句，可以使用块（`{ ... }`）来包裹这些语句。
4. 如果有更新表达式 `incrementExpression`，执行更新表达式。
5. 回到步骤 2。

### do...while 语句

do...while语句一直重复直到求值得到假值

```js
do{
  statement
} while (condition);
```

statement会在检查条件之前执行一次，如果condition为真，则statement继续执行；如果为假则停止执行



### while 语句

while语句只要指定的条件为真就会一直执行它的语句块

```js
while (condition) {
  statement
}
```

先判断condition，只要为真，就会执行statement



### label 语句

一个label语句让你在程序中其他位置提供引用它的标识符。你可以用label标识一个循环，然后使用break和continue指出程序是该停止循环还是继续循环

```js
var num = 0;
for (var i = 0; i < 10; i++) {
  // i 循环
  for (var j = 0; j < 10; j++) {
    // j 循环
    if (i == 5 && j == 5) {
      break; // i = 5，j = 5 时，会跳出 j 循环
    } // 但 i 循环会继续执行，等于跳出之后又继续执行更多次 j 循环
    num++;
  }
}

alert(num); // 输出 95
```

添加label后：

```js

var num = 0;
outPoint: for (var i = 0; i < 10; i++) {
  for (var j = 0; j < 10; j++) {
    if (i == 5 && j == 5) {
      break outPoint; // 在 i = 5，j = 5 时，跳出所有循环，
      // 返回到整个 outPoint 下方，继续执行
    }
    num++;
  }
}

alert(num); // 输出 55
```

使用continue可以停止当前循环，从新执行label标识循环

```js
var num = 0;
outPoint: for (var i = 0; i < 10; i++) {
  for (var j = 0; j < 10; j++) {
    if (i == 5 && j == 5) {
      continue outPoint;
    }
    num++;
  }
}
alert(num); // 95
```

### break 语句

使用 [`break`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/break) 语句来终止循环，`switch`，或者是链接到 label 语句。

- 当你使用不带 label 的 `break` 时，它会立即终止当前所在的 `while`，`do-while`，`for`，或者 `switch` 并把控制权交回这些结构后面的语句。
- 当你使用带 label 的 `break` 时，它会终止指定的带标记（label）的语句。

```js
break [label];
```

### for...in 语句

for...in 语句循环一个对象。JavaScript 会为每一个不同的属性执行指定的语句。

```
for (属性 in 对象) {
  statements
}
```



## 函数

### 函数定义

**函数定义**（也称为**函数声明**，或**函数语句**）由 [`function`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Statements/function) 关键字，并跟随以下部分组成：

- 函数名称。
- 函数参数列表，包围在括号中并由逗号分隔。
- 定义函数的 JavaScript 语句，用大括号括起来，`{ /* … */ }`。

```js
function square(number) {
  return number * number;
}
```

### 函数表达式

虽然上面的函数声明在语法上是一个语句，但函数也可以由[函数表达式](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/function)创建。

这样的函数可以是**匿名**的；它不必有一个名称。例如，函数 `square` 也可这样来定义：

```js
const square = function (number) {
  return number * number;
};

console.log(square(4)); // 16
```

然而，*也可以*为函数表达式提供名称，并且可以用于在函数内部代指其本身，或者在调试器堆栈跟踪中识别该函数：

```js
const factorial = function fac(n) {
  return n < 2 ? 1 : n * fac(n - 1);
};

console.log(factorial(3)); // 6
```

### 函数提升

考虑以下示例：

```js
console.log(square(5)); // 25

function square(n) {
  return n * n;
}
```

尽管 `square()` 函数在声明之前被调用，但此代码的运行并没有任何错误。这是因为 JavaScript 解释器会将整个函数声明提升到当前作用域的顶部，因此上面的代码等价于：

```js
// 所有函数声明实际上都位于作用域的顶部
function square(n) {
  return n * n;
}

console.log(square(5)); // 25
```

函数提升仅适用于函数*声明*，而不适用于函数*表达式*。以下代码无法运行：

```js
console.log(square(5)); // ReferenceError: Cannot access 'square' before initialization
const square = function (n) {
  return n * n;
};
```

### 函数作用域

在函数内定义的变量不能在函数之外的任何地方访问，因为变量仅仅在该函数的作用域内定义。相对应的，一个函数可以访问定义在其范围内的任何变量和函数。

换言之，定义在全局域中的函数可以访问所有定义在全局域中的变量。在另一个函数中定义的函数也可以访问在其父函数中定义的所有变量和父函数有权访问的任何其他变量。

```js
// 下面的变量定义在全局作用域中
const num1 = 20;
const num2 = 3;
const name = "Chamakh";

// 此函数定义在全局作用域中
function multiply() {
  return num1 * num2;
}

console.log(multiply()); // 60

// 嵌套函数示例
function getScore() {
  const num1 = 2;
  const num2 = 3;

  function add() {
    return `${name} 的得分为 ${num1 + num2}`;
  }

  return add();
}

console.log(getScore()); // "Chamakh 的得分为 5"
```

### 闭包

闭包是 JavaScript 中最强大的特性之一。JavaScript 允许函数嵌套，并且内部函数具有定义在外部函数中的所有变量和函数（以及外部函数能访问的所有变量和函数）的完全访问权限。

但是，外部函数却*不能*访问定义在内部函数中的变量和函数。这给内部函数的变量提供了一种封装。

此外，由于内部函数可以访问外部函数的作用域，因此当内部函数生存周期大于外部函数时，外部函数中定义的变量和函数的生存周期将比内部函数执行的持续时间要长。当内部函数以某一种方式被任何一个外部函数之外的任何作用域访问时，就会创建闭包。

### arguments 对象

函数的实际参数会被保存在一个类似数组的 arguments 对象中。在函数内，你可以按如下方式找出传入的参数：

```js
arguments[i];
```

其中 `i` 是参数的序号，从 `0` 开始。所以第一个传入函数的参数会是 `arguments[0]`。参数的数量由 `arguments.length` 表示。



使用arguments对象，你可以处理比声明更多的参数来调用函数，这才处理事先你不知道有多少参数的函数十分有用。可以先使用arguments.length来知道一共有几个参数。



例如可以创建一个创建喜爱的水果列表的函数：

```js
function myFruit(separator) {
    let fruit = ''
    for(let i = 1; i < arguments.length; i++){
        fruit += arguments[i] + separator
    }
    return fruit
}

console.log(myFruit('、','苹果','香蕉','火龙果')) //苹果、香蕉、火龙果、
```

**备注：** `arguments` 变量只是“类数组”，而不是数组。它与数组类似，有索引编号和 `length` 属性。尽管如此，它并不*具备* Array 对象的所有数组操作方法。



### 函数参数

有两种特殊的参数语法：*默认参数*和*剩余参数*。

**默认参数**

函数的默认参数是`undefind`，可以使用默认参数指定参数默认值，则函数内的手动检查不再必要

```js
unction multiply(a, b = 1) {
  return a * b;
}

console.log(multiply(5)); // 5
```



**剩余参数**

剩余参数语法允许将不确定数量的参数表示为一个数组

```js
function multiply(multiplier, ...theArgs) {
  return theArgs.map((x) => multiplier * x);
}

const arr = multiply(2, 1, 2, 3);
console.log(arr); // [2, 4, 6]
```



### 箭头函数

[箭头函数表达式](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/Arrow_functions)（也称*胖箭头*，以区分未来 JavaScript 中假设的 `->` 语法）相比函数表达式具有较短的语法且没有它自己的 [`this`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/this)、[`arguments`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Functions/arguments)、[`super`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/super) 和 [`new.target`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/new.target)。箭头函数总是匿名的。

有两个因素会影响对箭头函数的引入：*更简洁的函数*和 `this` 的*无绑定性*。



### 内置函数

| 函数                 | 简介                                                         |
| -------------------- | ------------------------------------------------------------ |
| isNaN()              | **`isNaN()`** 函数判断一个值是否是 [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN)。 |
| parseFloat()         | **`parseFloat()`** 函数解析字符串参数，并返回一个浮点数。    |
| parseInt()           | **`parseInt()`** 函数解析字符串参数，并返回指定的基数（基础数学中的数制）的整数。 |
| encodeURI()          | **`encodeURI()`** 方法通过以表示字符的 UTF-8 编码的一个、两个、三个或四个转义序列替换统一资源标识符（URI）的某些字符来进行编码（对于由两个“代理（surrogate）”字符组成的字符，只会编码为四个转义序列）。 |
| decodeURI()          | **`decodeURI()`** 函数对先前经过 [`encodeURI`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURI) 函数或者其他类似方法编码过的统一资源标志符（URI）进行解码。 |
| encodeURIComponent() | **`encodeURIComponent()`** 方法通过以表示字符的 UTF-8 编码的一个、两个、三个或四个转义序列替换统一资源标识符（URI）的某些字符来进行编码（对于由两个“代理”字符组成的字符，只会编码为四个转义序列）。 |
| decodeURIComponent() | **`decodeURIComponent()`** 方法对先前经过 [`encodeURIComponent`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/encodeURIComponent) 函数或者其他类似方法编码的统一资源标志符（URI）进行解码。 |

## 表达式与运算符

### 解构

对于更复杂的赋值，[解构赋值](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)语法是一个能从数组或对象对应的数组结构或对象字面量里提取数据的 Javascript 表达式。

```js
var foo = ["one", "two", "three"];

// 不使用解构
var one = foo[0];
var two = foo[1];
var three = foo[2];

// 使用解构
var [one, two, three] = foo;
```

### 逗号操作符

[逗号操作符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/Comma_operator)（`,`）对两个操作数进行求值并返回最终操作数的值。它常常用在 `for` 循环中，在每次循环时对多个变量进行更新。

```js
var x = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9];
var a = [x, x, x, x, x];

for (var i = 0, j = 9; i <= j; i++, j--)
  console.log("a[" + i + "][" + j + "]= " + a[i][j]);
```

### 一元操作符



**`delete`**

[`delete`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Operators/delete)操作符，删除一个对象的属性或者一个数组中某一个键值。语法如下：

```js
// 对象
delete objectName.property;
delete objectName[index];

// 数组
var trees = new Array("redwood", "bay", "cedar", "oak", "maple");
delete trees[3];
```



**`typeof`**

typeof 操作符 可通过下面 2 种方式使用：

```js
typeof operand;
typeof (operand);
```

typeof 操作符返回一个表示 operand 类型的字符串值。operand 可为字符串、变量、关键词或对象，其类型将被返回。operand 两侧的括号为可选。

```js
var myFun = new Function("5 + 2");
var shape = "round";
var size = 1;
var today = new Date();

typeof myFun; // returns "function"
typeof shape; // returns "string"
typeof size; // returns "number"
typeof today; // returns "object"
typeof dontExist; // returns "undefined"

// 对于关键词 true 和 null， typeof 操作符将会返回如下结果：
typeof true; // returns "boolean"
typeof null; // returns "object"
```

`typeof`判断`null`和`数组`会返回object



**`void`**

对给定的表达式进行求值，然后返回 **undefined**

```js
void expression
```

常见的作用：

- 替代undefined

- 阻止默认事件
- 阻止a标签跳转



### 关系运算符

> 关系运算符对操作数进行比较，根据比较结果真或假，返回相应的布尔值。

**`in`**

如果指定的属性在指定的对象或其原型链中，则 **`in`** **运算符**返回 `true`。也可以判断某数组下标是否存在

```js
属性名|数组下标 in object
```

```js
// 数组
var trees = new Array("redwood", "bay", "cedar", "oak", "maple");
0 in trees; // 返回 true
3 in trees; // 返回 true
6 in trees; // 返回 false
"bay" in trees; // 返回 false (必须使用索引号，而不是数组元素的值)

"length" in trees; // 返回 true (length 是一个数组属性)

Symbol.iterator in trees; // 返回 true (数组可迭代，只在 ES2015+ 上有效)

// 内置对象
"PI" in Math; // 返回 true

// 自定义对象
var mycar = { make: "Honda", model: "Accord", year: 1998 };
"make" in mycar; // 返回 true
"model" in mycar; // 返回 true
```



**`instanceof`**

 如果所判别的对象确实是所指定的类型，则返回`true`。其语法如下：

```js
objectName instanceof objectType;
```

`objectName` 是需要做判别的对象的名称，而`objectType`是假定的对象的类型，例如[`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date)或 [`Array`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array).

### 表达式

表达式是一组代码的集合，它返回一个值。每一个合法的表达式都能计算成某个值，但从概念上讲，有两种类型的表达式：有副作用的（比如赋值）和单纯计算求值的。

表达式 x=7 是第一类型的一个例子。该表达式使用=运算符将值 7 赋予变量 x。这个表达式自己的值等于 7。

代码 3 + 4 是第二个表达式类型的一个例子。该表达式使用 + 运算符把 3 和 4 加到一起但并没有把结果（7）赋值给一个变量。

- JavaScript 有以下表达式类型：
  - 算数：得出一个数字，例如 3.14159。（通常使用[算数运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#算术运算符)）
  - 字符串：得出一个字符串，例如，"Fred" 或 "234"。（通常使用[字符串运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#字符串运算符)。）
  - 逻辑值：得出 true 或者 false。（经常涉及到[逻辑运算符](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Expressions_and_operators#逻辑运算符)。）
  - 基本表达式：javascript 中基本的关键字和一般表达式。
  - 左值表达式：分配给左值。

## 数值和日期

### 数字对象

内置的 [`Number`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number) 对象有一些有关数字的常量属性，如最大值、不是一个数字和无穷大的。你不能改变这些属性，但可以按下边的方式使用它们：

```js
const biggestNum = Number.MAX_VALUE;
const smallestNum = Number.MIN_VALUE;
const infiniteNum = Number.POSITIVE_INFINITY;
const negInfiniteNum = Number.NEGATIVE_INFINITY;
const notANum = Number.NaN;
```

下面的表格汇总了数字对象的属性：



**数字的属性**

| 属性                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [`Number.MAX_VALUE`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_VALUE) | 可表示的最大值                                               |
| [`Number.MIN_VALUE`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_VALUE) | 可表示的最小值                                               |
| [`Number.NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/NaN) | 特指”非数字“                                                 |
| [`Number.NEGATIVE_INFINITY`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/NEGATIVE_INFINITY) | 特指“负无穷”;在溢出时返回                                    |
| [`Number.POSITIVE_INFINITY`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/POSITIVE_INFINITY) | 特指“正无穷”;在溢出时返回                                    |
| [`Number.EPSILON`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/EPSILON) | 表示 1 和比最接近 1 且大于 1 的最小[`Number`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number)之间的差别 |
| [`Number.MIN_SAFE_INTEGER`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/MIN_SAFE_INTEGER) | JavaScript 最小安全整数。                                    |
| [`Number.MAX_SAFE_INTEGER`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/MAX_SAFE_INTEGER) | JavaScript 最大安全整数。                                    |

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [`Number.parseFloat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/parseFloat) | 把字符串参数解析成浮点数，和全局方法 [`parseFloat()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseFloat) 作用一致。 |
| [`Number.parseInt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/parseInt) | 把字符串解析成特定基数对应的整型数字，和全局方法 [`parseInt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/parseInt) 作用一致。 |
| [`Number.isFinite()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/isFinite) | 判断传递的值是否为有限数字。                                 |
| [`Number.isInteger()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/isInteger) | 判断传递的值是否为整数。                                     |
| [`Number.isNaN()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/isNaN) | 判断传递的值是否为 [`NaN`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/NaN). More robust version of the original global [`isNaN()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/isNaN). |
| [`Number.isSafeInteger()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Number/isSafeInteger) | 判断传递的值是否为安全整数。                                 |

### 数学对象（Math）

对于内置的[`Math`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math)数学常项和函数也有一些属性和方法。比方说， `Math` 对象的 `PI` 属性会有属性值 pi (3.141...)，你可以像这样调用它：

```js
Math.PI; // π
```

Math 的方法

| 方法                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [`abs()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/abs) | 绝对值                                                       |
| [`sin()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sin), [`cos()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/cos), [`tan()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/tan) | 标准三角函数;参数为弧度                                      |
| [`asin()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/asin), [`acos()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/acos), [`atan()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/atan), [`atan2()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/atan2) | 反三角函数; 返回值为弧度                                     |
| [`sinh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sinh), [`cosh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/cosh), [`tanh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/tanh) | 双曲三角函数; 参数为弧度。                                   |
| [`asinh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/asinh), [`acosh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/acosh), [`atanh()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/atanh) | 反双曲三角函数;返回值为弧度。                                |
| [`pow()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/pow), [`exp()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/exp), [`expm1()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/expm1), [`log10()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/log10), [`log1p()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/log1p), [`log2()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/log2) | 指数与对数函数                                               |
| [`floor()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/floor), [`ceil()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/ceil) | 返回小于等于参数的最大整数；返回大于等于参数的最小整数       |
| [`min()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/min), [`max()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/max) | 返回一个以逗号间隔的数字参数列表中的较小或较大值 (分别地)    |
| [`random()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/random) | 返回 0 和 1 之间的随机数。                                   |
| [`round()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/round), [`fround()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/fround), [`trunc()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/trunc), | 四舍五入和截断函数                                           |
| [`sqrt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sqrt), [`cbrt()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/cbrt), [`hypot()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/hypot) | 平方根，立方根，所有参数平方和的平方根两个参数平方和的平方根 |
| [`sign()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/sign) | 数字的符号，说明数字是否为正、负、零。                       |
| [`clz32()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/clz32), [`imul()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Math/imul) | 在 32 位 2 进制表示中，开头的 0 的数量。*返回传入的两个参数相乘结果的类 C 的 32 位表现形式* |

和其他对象不同，你不能够创建一个自己的 Math 对象。你只能使用内置的 Math 对象。

### 日期对象

JavaScript 没有日期数据类型。但是你可以在你的程序里使用 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象和其方法来处理日期和时间。Date 对象有大量的设置、获取和操作日期的方法。它并不含有任何属性。

JavaScript 处理日期数据类似于 Java。这两种语言有许多一样的处理日期的方法，也都是以 1970 年 1 月 1 日 00:00:00 以来的毫秒数来储存数据类型的。



创建一个日期对象：

```js
var dateObjectName = new Date([parameters]);
```

`dateObjectName`为所创建的Date对象的名字，或是其他对象的一个属性

不使用 *new* 关键字来调用 Date 对象将返回当前时间和日期的字符串



`parameters`参数可选：

- 无参数 : 创建今天的日期和时间，例如： `today = new Date();`.
- 一个符合以下格式的表示日期的字符串："月 日，年 时：分：秒"。例如： `var Xmas95 = new Date("December 25, 1995 13:30:00")。`如果你省略时、分、秒，那么他们的值将被设置为 0。
- 表示日期的字符串值。该字符串应该能被 [`Date.parse()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/parse) 正确方法识别（即符合 [IETF-compliant RFC 2822 timestamps](https://tools.ietf.org/html/rfc2822#page-14) 或 [version of ISO8601](https://www.ecma-international.org/ecma-262/5.1/#sec-15.9.1.15)）。
- 一个年，月，日，时，分，秒的集合，例如： `var Xmas95 = new Date(1995, 11, 25, 9, 30, 0);`.



**方法**

[`Date.parse()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/parse)

解析一个表示日期的字符串，并返回从 1970-1-1 00:00:00 所经过的毫秒数。

[`Date.now()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/now)

返回自 1970-1-1 00:00:00 UTC（世界标准时间）至今所经过的毫秒数。



**实例方法**

[`Date.prototype.getDate()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDate)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象为一个月中的`哪一日`（`1`-`31`）。

[`Date.prototype.getDay()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getDay)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象是在一周中的第几天（`0`-`6`），0 表示`星期`天。

[`Date.prototype.getFullYear()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getFullYear)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的完整`年份`（四位数年份）。

[`Date.prototype.getHours()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getHours)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`小时`（`0`–`23`）。

[`Date.prototype.getMilliseconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMilliseconds)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`毫秒数`（`0`–`999`）。

[`Date.prototype.getMinutes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMinutes)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`分钟数`（`0`–`59`）。

[`Date.prototype.getMonth()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getMonth)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`月份`（`0`–`11`），0 表示一年中的第一月。

[`Date.prototype.getSeconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getSeconds)

根据本地时间，返回一个指定的 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`秒数`（`0`–`59`）。

[`Date.prototype.getTime()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/getTime)

返回一个数值，表示从 1970 年 1 月 1 日 0 时 0 分 0 秒（UTC，即协调世界时）距离该 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象所代表时间的毫秒数。（更早的时间会用负数表示）

[`Date.prototype.setDate()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setDate)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象在所属月份中的`天数`。数值超过天数会用差值

[`Date.prototype.setFullYear()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setFullYear)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的完整`年份`（四位数年份）。

[`Date.prototype.setHours()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setHours)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的小时数。

[`Date.prototype.setMilliseconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setMilliseconds)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`豪秒数`。

[`Date.prototype.setMinutes()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setMinutes)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的分钟数。

[`Date.prototype.setMonth()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setMonth)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`月份`。

[`Date.prototype.setSeconds()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setSeconds)

根据本地时间，设置一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象的`秒数`。

[`Date.prototype.setTime()`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date/setTime)

用一个从 1970-1-1 00:00:00 UTC 计时的毫秒数来为一个 [`Date`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Date) 对象设置时间。用负数来设置更早的时间。

## 文本格式化

### 字符串对象

[`String`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/String) 对象是对原始 string 类型的封装 .

```js
const foo = new String("foo"); // 创建一个 String 对象
console.log(foo); // 输出：[String: 'foo']
typeof foo; // 返回 'object'
```

你可以在 String 字面值上使用 String 对象的任何方法—JavaScript 自动把 String 字面值转换为一个临时的 String 对象，然后调用其相应方法，最后丢弃此临时对象。在 String 字面值上也可以使用 String.length 属性。



除非必要，应该尽量使用 String 字面值，因为 String 对象的某些行为可能并不与直觉一致。举例：

```js
const firstString = "2 + 2"; //创建一个字符串字面量
const secondString = new String("2 + 2"); // 创建一个字符串对象
eval(firstString); // 返回数字 4
eval(secondString); // 返回包含 "2 + 2" 的字符串对象
```



`String` 对象有一个属性 `length`，标识了字符串中 UTF-16 的码点个数。举例，下面的代码把 13 赋值给了`helloLength`，因为 "Hello, World!" 包含 13 个字符，每个字符用一个 UTF-16 码点表示。你可以通过数组的方式访问每一个码点，但你不能修改每个字符，因为字符串是不变的类数组对象：

```js
const hello = "Hello, World!";
const helloLength = hello.length;
hello[0] = "L"; // 无效，因为字符串是不变的
hello[0]; // 返回 "H"
```



### **字符串方法**

| 方法                    | 参数                         | 描述                                                         |
| ----------------------- | ---------------------------- | ------------------------------------------------------------ |
| startsWith              | 查找的字符串，[起始位置索引] | 判断当前字符串是否以另外一个给定的子字符串开头，并根据判断结果返回 `true` 或 `false`。 |
| endsWith                | 查找的字符串，[起始位置索引] | 判断当前字符串是否以另外一个给定的子字符串结尾，并根据判断结果返回 `true` 或 `false`。 |
| includes                | 指定字符串                   | 是否包含指定字符串，并根据判断结果返回 `true` 或 `false`。   |
| concat                  | n个字符串...                 | 连接多个字符串并返回新字符串                                 |
| split                   | 分隔符，数组数量限制         | 将字符串分割成数组并返回                                     |
| slice                   | 开始索引，结束索引           | 提取字符串的一部分                                           |
| substring               | 开始索引，[结束索引]         | 方法返回该字符串从起始索引到结束索引（不包括）的部分，如果未提供结束索引，则返回到字符串末尾的部分。 |
| replace                 | 正则或字符串，替换值         | 将字符串替换指定内容，返回替换后的字符串                     |
| match                   | 正则                         | 返回匹配项的数组，如无匹配则返回`null`                       |
| search                  | 正则                         | 返回首个匹配项的索引，如无匹配则返回`-1`                     |
| toLowerCase,toUpperCase |                              | 将字符串转换为小写和大写                                     |
| repeat                  | 数量                         | 将字符串内容重复指定次数后返回。                             |
| trim                    |                              | 去除开头和结尾的空白字符                                     |

## 正则表达式

### 创建一个正则表达式

利用双斜杠之间创建

```js
let re = /A-Z{8}/
```

脚本加载后，正则表达式字面量就会被编译。当正则表达式保持不变时，使用此方法可获得更好的性能。



或者调用`RegExp`对象的构造函数

```js
var re = new RegExp("ab+c");
```

在脚本运行过程中，用构造函数创建的正则表达式会被编译。如果正则表达式将会改变，或者它将会从用户输入等来源中动态地产生，就需要使用构造函数来创建正则表达式。



### 使用简单模式

简单模式是由你想直接找到的字符构成。比如，`/abc/` 这个模式就能且仅能匹配 "abc" 字符按照顺序同时出现的情况。

### 使用特殊字符

当你需要匹配一个不确定的字符串时，比如寻找一个或多个 "b"，或者寻找空格，可以在模式中使用特殊字符。比如，你可以使用 `/ab*c/` 去匹配一个单独的 "a" 后面跟了零个或者多个 "b"，同时后面跟着 "c" 的字符串：`*`的意思是前一项出现零次或者多次。

| 字符                                                         | 含义                                                         |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| `^`                                                          | 匹配输入的开头。                                             |
| `$`                                                          | 匹配输入的结束。                                             |
| `\b`                                                         | 匹配一个字母的开头或结尾边界                                 |
| `\B`                                                         | 匹配一个字母的非边界开头或非边界结尾                         |
| `[a-c]`                                                      | 字符类，匹配包含在方括号中的任何字符。`[abcd]` 与 `[a-d]` 相同。 |
| `[^a-c]`                                                     | 它匹配未包含在方括号中的任何字符。                           |
| `.`                                                          | 匹配字符前或后`.`的位数，必须符合位数                        |
| `\d`                                                         | 匹配任何数字 (阿拉伯数字)。相当于 `[0-9]`。                  |
| `\D`                                                         | 匹配任何非数字 (阿拉伯数字) 的字符。相当于`[^0-9]`           |
| `\w`                                                         | 匹配基本拉丁字母中的任何字母数字字符，包括下划线。相当于 `[A-Za-z0-9_]`。 |
| `\W`                                                         | 匹配任何不是来自基本拉丁字母的单词字符。相当于 `[^A-Za-z0-9_]`。 |
| `\s`                                                         | 匹配单个空白字符，包括空格、制表符、换页符、换行符和其他 Unicode 空格。 |
| `\S`                                                         | 匹配除空格以外的单个字符。                                   |
| `x|y`                                                        | 匹配 "x" 或 "y" 任意一个字符。                               |
| `(x)`                                                        | **捕获组：**匹配 x 并记住匹配项。使用 `RegExp` 对象的属性 (`$1, ..., $9`)来获取 |
| `\n`                                                         | 其中 n 是一个正整数。对之前的捕获组进行反向引用，n为第几个   |
| [`(?<Name>x)`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Guide/Regular_expressions/Groups_and_backreferences) | **具名捕获组：**匹配"x"并将其存储在返回的匹配项的 groups 属性中 |
| `x*`                                                         | 将前面的项“x”匹配 0 次或更多次。                             |

## 数组

### 创建数组

以下语句创建了等效的数组：

```js
const arr1 = new Array(element0, element1, /* … ,*/ elementN);
const arr2 = Array(element0, element1, /* … ,*/ elementN);
const arr3 = [element0, element1, /* … ,*/ elementN];
```



为了创建一个长度不为 0，但是又没有任何元素的数组，可选以下任何一种方式：

```js
// 这种方式...
const arr1 = new Array(arrayLength);

// ...与这种方式会形成相同数组
const arr2 = Array(arrayLength);

// 这个效果也一样
const arr3 = [];
arr3.length = arrayLength;
```

如果你创建的数组是一个元素，正好又是一个数值，可以用 [`Array.of`](https://developer.mozilla.org/zh-CN/docs/Web/JavaScript/Reference/Global_Objects/Array/of) 静态方法来创建包含单个元素的数组。

```js
const wisenArray = Array.of(9.3); // wisenArray 只包含一个元素：9.3
```



你也可以给 `length` 属性赋值。

写一个小于数组元素数量的值将截断数组，写 `0` 会彻底清空数组：

```js
const cats = ["Dusty", "Misty", "Twiggy"];
console.log(cats.length); // 3

cats.length = 2;
console.log(cats); // [ 'Dusty', 'Misty' ] - Twiggy 已经被移除了

cats.length = 0;
console.log(cats); // 输出 []，猫名称的数组现在已经空了

cats.length = 3;
console.log(cats); // 输出 [ <3 empty items> ]
```

### 数组方法

#### **forEach()**

传递给 `forEach` 的函数对数组中的每个元素执行一次，数组元素作为参数传递给该函数。未赋值的值不会在 `forEach` 循环迭代。

注意，在数组定义时省略的元素不会在 `forEach` 遍历时被列出，但是手动赋值为 `undefined` 的元素是*会*被列出的：

```js
const sparseArray = ["first", "second", , "fourth"];

sparseArray.forEach((element) => {
  console.log(element);
});
// first
// second
// fourth

if (sparseArray[2] === undefined) {
  console.log("sparseArray[2] 是 undefined"); // true
}

const nonsparseArray = ["first", "second", undefined, "fourth"];

nonsparseArray.forEach((element) => {
  console.log(element);
});
// first
// second
// undefined
// fourth
```

#### **concat()**

方法连接两个或多个数组并返回一个新的数组。

```js
let myArray = ["1", "2", "3"];
myArray = myArray.concat("a", "b", "c");
// myArray 现在是 ["1", "2", "3", "a", "b", "c"]
```

#### join()

方法将数组中的所有元素连接成一个字符串。

```js
const myArray = ["Wind", "Rain", "Fire"];
const list = myArray.join(" - "); // list 现在是 "Wind - Rain - Fire"
```

#### push()

方法在数组末尾添加一个或多个元素，并返回数组操作后的 `length`。

```js
const myArray = ["1", "2"];
myArray.push("3"); // myArray 现在是 ["1", "2", "3"]
```

#### pop()

方法从数组移出最后一个元素，并返回该元素。

```js
const myArray = ["1", "2", "3"];
const last = myArray.pop();
// myArray 现在是 ["1", "2"]，last 为 "3"
```

#### shift()

方法从数组移出第一个元素，并返回该元素。

```js
const myArray = ["1", "2", "3"];
const first = myArray.shift();
// myArray 现在是 ["2", "3"]，first 为 "1"
```

#### unshift()

方法在数组开头添加一个或多个元素，并返回数组的新长度。

```js
const myArray = ["1", "2", "3"];
myArray.unshift("4", "5");
// myArray 变成了 ["4", "5", "1", "2", "3"]
```

#### slice()

方法从数组提取一个片段，并作为一个新数组返回。

```js
let myArray = ["a", "b", "c", "d", "e"];
myArray = myArray.slice(1, 4); // [ "b", "c", "d"]
// 从索引 1 开始，提取所有的元素，直到索引 3 为止
```

#### at()

方法返回数组中指定索引处的元素，如果索引超出范围，则返回 `undefined`。它主要用于从数组末尾访问元素的负下标。

```js
const myArray = ["a", "b", "c", "d", "e"];
myArray.at(-2); // "d"，myArray 的倒数第二个元素
```

#### splice()

方法通过移除或者替换已存在的元素和/或添加新元素就地改变一个数组的内容。

参数: start, deleteCount, itemN

start：从 0 开始计算的索引，表示要开始改变数组的位置

deleteCount：一个整数，表示数组中要从 `start` 开始删除的元素数量。如果省略了 `deleteCount`，或者其值大于或等于由 `start` 指定的位置到数组末尾的元素数量，那么从 `start` 到数组末尾的所有元素将被删除。如果 `deleteCount` 是 `0` 或者负数，则不会移除任何元素。

itemN：从 `start` 开始要加入到数组中的元素。如果不指定任何元素，`splice()` 将只从数组中删除元素。

```js
const months = ['Jan', 'March', 'April', 'June'];
months.splice(1, 0, 'Feb');
// Inserts at index 1
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "June"]

months.splice(4, 1, 'May');
// Replaces 1 element at index 4
console.log(months);
// Expected output: Array ["Jan", "Feb", "March", "April", "May"]
```

#### reverse()

方法原地颠倒数组元素的顺序

```js
const myArray = ["1", "2", "3"];
myArray.reverse();
// 将原数组颠倒，myArray = [ "3", "2", "1" ]
```

#### flat()

方法返回一个新数组，所有子数组元素递归地连接到其中，直到指定的深度。

```js
let myArray = [1, 2, [3, 4]];
myArray = myArray.flat();
// myArray 现在是 [1, 2, 3, 4]，因为子数组 [3, 4] 已被展平
```

#### sort()

方法对数组的元素进行适当的排序，并返回对数组的引用。默认排序是将元素转换为字符串，然后按照它们的 UTF-16 码元值升序排序。

```js
const myArray = ["Wind", "Rain", "Fire"];
myArray.sort();
// 对数组排序，myArray = ["Fire", "Rain", "Wind"]
```

#### indexOf()

方法在数组中搜索 `searchElement` 并返回第一个匹配的索引。第二个参数可以指定索引开始搜索。

```js
const a = ["a", "b", "a", "b", "a"];
console.log(a.indexOf("b")); // 1

// 再试一次，这次从最后一次匹配之后开始
console.log(a.indexOf("b", 2)); // 3
console.log(a.indexOf("z")); // -1, 因为找不到 'z'
```

#### lastIndexOf()

方法的工作原理类似于 `indexOf`，但这是从末尾开始，反向搜索。

#### map()

方法返回由每个数组元素上执行 `callback` 的返回值所组成的新数组。

```js
const a1 = ["a", "b", "c"];
const a2 = a1.map((item) => item.toUpperCase());
console.log(a2); // ['A', 'B', 'C']
```

#### flatMap()

方法先执行 `map()`，再执行深度为 1 的 `flat()`。

```js
const a1 = ["a", "b", "c"];
const a2 = a1.flatMap((item) => [item.toUpperCase(), item.toLowerCase()]);
console.log(a2); // ['A', 'a', 'B', 'b', 'C', 'c']
```

#### filter()

方法返回一个新数组，其中包含 `callback` 返回 `true` 的元素。

```js
const a1 = ["a", 10, "b", 20, "c", 30];
const a2 = a1.filter((item) => typeof item === "number");
console.log(a2); // [10, 20, 30]
```

#### find()

方法返回 `callback` 返回 `true` 的第一个元素。

```js
const a1 = ["a", 10, "b", 20, "c", 30];
const i = a1.find((item) => typeof item === "number");
console.log(i); // 10
```

#### findLast() 

方法返回 `callback` 返回 `true` 的最后一个元素。

```js
const a1 = ["a", 10, "b", 20, "c", 30];
const i = a1.findLast((item) => typeof item === "number");
console.log(i); // 30
```

#### findIndex()

方法返回 `callback` 返回 `true` 的第一个元素的索引。

```js
const a1 = ["a", 10, "b", 20, "c", 30];
const i = a1.findIndex((item) => typeof item === "number");
console.log(i); // 1
```

### findLastIndex()

方法返回 `callback` 返回 `true` 的最后一个元素的索引。

```js
const a1 = ["a", 10, "b", 20, "c", 30];
const i = a1.findLastIndex((item) => typeof item === "number");
console.log(i); // 5
```

#### every()

如果 `callback` 对数组中的每一个元素都返回 `true`，则返回`true`

```js
function isNumber(value) {
  return typeof value === "number";
}
const a1 = [1, 2, 3];
console.log(a1.every(isNumber)); // true
const a2 = [1, "2", 3];
console.log(a2.every(isNumber)); // false
```

#### some()

如果 `callback` 对数组中有一个元素返回 `true`，则返回`true`

```js
function isNumber(value) {
  return typeof value === "number";
}
const a1 = [1, 2, 3];
console.log(a1.some(isNumber)); // true
const a2 = [1, "2", 3];
console.log(a2.some(isNumber)); // true
const a3 = ["1", "2", "3"];
console.log(a3.some(isNumber)); // false
```

#### reduce()

方法对数组中的每个值执行 `callback(accumulator, currentValue, currentIndex, Array)`，一般用于求和

```js
const a = [10, 20, 30];
const total = a.reduce(
  (accumulator, currentValue) => accumulator + currentValue,
  0,
);
console.log(total); // 60
```

#### reduceRight()

方法的工作原理类似于 `reduce()`，但从最后一个元素开始。