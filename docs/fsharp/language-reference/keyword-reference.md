---
title: "关键字参考 (F#)"
description: "查找有关 F # 语言关键字的所有信息的链接。"
keywords: "visual f#, f#, 函数编程"
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: cdfdd86843acf05a8b33647823f934a161f6d885
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="keyword-reference"></a>关键字参考

本主题包含有关所有 F # 语言关键字的信息的链接。

## <a name="f-keyword-table"></a>F # 关键字表

下表显示了按字母顺序，简要说明以及指向包含详细信息的相关主题的链接的所有 F # 关键字。

|关键字|Link|描述|
|-------|----|-----------|
|`abstract`|[成员](members/index.md)<br /><br />[抽象类](abstract-classes.md)|指示既可以在其中声明它或，其中是虚拟的但默认实现的类型中具有没有实现的方法。|
|`and`|[`let`绑定](functions/let-bindings.md)<br /><br />[成员](members/index.md)<br /><br />[约束](generics/constraints.md)|相互递归在绑定中使用，在属性声明中，并使用泛型形参上的多个约束。|
|`as`|[类](classes.md)<br /><br />[模式匹配](Pattern-Matching.md)|用于为当前类对象提供一个对象名称。 此外用于在模式匹配整个模式为提供一个名称。|
|`assert`|[断言](assertions.md)|用于在调试期间验证代码。|
|`base`|[类](classes.md)<br /><br />[继承](inheritance.md)|用作基类对象的名称。|
|`begin`|[详细语法](verbose-syntax.md)|在详细语法中，该值指示代码块的起始位置。|
|`class`|[类](classes.md)|在详细语法中，指示类定义的开头。|
|`default`|[成员](members/index.md)|指示一个抽象方法; 的实现与一个抽象方法声明一起使用，以创建虚拟方法。|
|`delegate`|[委托](delegates.md)|用于声明委托。|
|`do`|[do 绑定](functions/do-bindings.md)<br /><br />[循环：`for...to` 表达式](loops-for-to-expression.md)<br /><br />[循环：`for...in` 表达式](loops-for-in-expression.md)<br /><br />[循环：`while...do` 表达式](loops-while-do-expression.md)|用于在循环构造或执行命令性代码。|
|`done`|[详细语法](verbose-syntax.md)|在详细语法中，指示的循环表达式中的代码块的末尾。|
|`downcast`|[强制转换和转换](casting-and-conversions.md)|用于将转换为较低的继承链中的类型。|
|`downto`|[循环：`for...to` 表达式](loops-for-to-expression.md)|在`for`时按相反的顺序计数所用的表达式。|
|`elif`|[条件表达式：`if...then...else`](conditional-expressions-if-then-else.md)|使用条件分支中。 缩写形式`else if`。|
|`else`|[条件表达式：`if...then...else`](conditional-expressions-if-then-else.md)|使用条件分支中。|
|`end`|[结构](structures.md)<br /><br />[可区分联合](discriminated-unions.md)<br /><br />[记录](records.md)<br /><br />[类型扩展](type-extensions.md)<br /><br />[详细语法](verbose-syntax.md)|在类型定义和类型扩展，该值指示成员定义的节的结尾处。<br /><br />在详细语法中，用于指定开头的代码块的末尾`begin`关键字。|
|`exception`|[异常处理](exception-handling/index.md)<br /><br />[异常类型](exception-handling/exception-types.md)|用于声明异常类型。|
|`extern`|[外部函数](functions/external-functions.md)|指示声明的程序元素在另一个二进制文件或程序集定义。|
|`false`|[基元类型](primitive-types.md)|用作布尔值文字。|
|`finally`|[异常：`try...finally` 表达式](exception-handling/the-try-finally-expression.md)|一起使用`try`引入的执行而不考虑是否发生了异常的代码块。|
|`fixed`|[固定](fixed.md)|使用"固定"指针上的堆栈，以防止它被垃圾回收。|
|`for`|[循环：`for...to` 表达式](loops-for-to-expression.md)<br /><br />[循环：for...in 表达式](loops-for-in-expression.md)|在循环构造中使用。|
|`fun`|[Lambda 表达式：`fun`关键字](functions/lambda-expressions-the-fun-keyword.md)|在 lambda 表达式，也称为匿名函数中使用。|
|`function`|[match 表达式](match-expressions.md)<br /><br />[Lambda 表达式： fun 关键字](functions/lambda-expressions-the-fun-keyword.md)|用作一个较短的替代方法`fun`关键字和`match`具有在单个自变量匹配的模式的 lambda 表达式中的表达式。|
|`global`|[命名空间](namespaces.md)|用于引用顶级.NET 命名空间。|
|`if`|[条件表达式：`if...then...else`](conditional-expressions-if-then-else.md)|在条件分支构造中使用。|
|`in`|[循环：for...in 表达式](loops-for-in-expression.md)<br /><br />[详细语法](verbose-syntax.md)|用于序列表达式，并且，在详细语法中，分隔从绑定表达式。|
|`inherit`|[继承](inheritance.md)|用于指定基类或基接口。|
|`inline`|[函数](functions/index.md)<br /><br />[内联函数](functions/inline-functions.md)|用于指示应直接集成到调用方的代码的函数。|
|`interface`|[接口](interfaces.md)|用于声明和实现接口。|
|`internal`|[访问控制](access-control.md)|用于指定成员是可见的程序集内但之外无效。|
|`lazy`|[延迟计算](lazy-computations.md)|用于指定仅在需要结果时要执行的计算。|
|`let`|[`let`绑定](functions/let-bindings.md)|用于关联，或将绑定，请为值或函数的名称。|
|`let!`|[异步工作流](asynchronous-workflows.md)<br /><br />[计算表达式](computation-expressions.md)|使用异步工作流可将名称绑定到的异步计算的结果或在其他计算表达式，用于绑定到一个结果的计算类型的名称。|
|`match`|[match 表达式](match-expressions.md)|用于通过比较值与模式的分支。|
|`member`|[成员](members/index.md)|用于声明属性或方法中的对象类型。|
|`module`|[模块](modules.md)|用于将一个名称与相关的类型、 值和函数，以便逻辑上分开的其他代码的一组相关联。|
|`mutable`|[let 绑定](functions/let-bindings.md)|用于声明变量，即，一个值，可以更改。|
|`namespace`|[命名空间](namespaces.md)|用于将一个名称与一组相关的类型和模块，以便逻辑上分开的其他代码相关联。|
|`new`|[构造函数](members/constructors.md)<br /><br />[约束](generics/constraints.md)|用于声明、 定义，或调用构造函数创建，或者，可以创建一个对象。<br /><br />也用在泛型参数约束以指示类型必须具有某些构造函数。|
|`not`|[符号和运算符参考](symbol-and-operator-reference/index.md)<br /><br />[约束](generics/constraints.md)|实际上并没有关键字。 但是，`not struct`结合被用作泛型参数约束。|
|`null`|[Null 值](values/null-values.md)<br /><br />[约束](generics/constraints.md)|指示缺少对象。<br /><br />也用在泛型参数约束。|
|`of`|[可区分联合](discriminated-unions.md)<br /><br />[委托](delegates.md)<br /><br />[异常类型](exception-handling/exception-types.md)|用于可区分联合，以指示的值，类别类型和委托和异常声明中。|
|`open`|[导入声明：`open` 关键字](import-declarations-the-open-keyword.md)|用于使命名空间或模块的内容无需限定即可。|
|`or`|[符号和运算符参考](symbol-and-operator-reference/index.md)<br /><br />[约束](generics/constraints.md)|为布尔值用于布尔条件`or`运算符。 等效于||`.<br /><br />也用在成员约束。|
|`override`|[成员](members/index.md)|用于实现抽象方法或虚方法的基的版本不同的版本。|
|`private`|[访问控制](access-control.md)|将访问限制为向相同的类型或模块中的代码的成员。|
|`public`|[访问控制](access-control.md)|允许访问外部类型中的成员。|
|`rec`|[函数](functions/index.md)|用于指示函数是递归。|
|`return`|[异步工作流](Asynchronous-Workflows.md)<br /><br />[计算表达式](computation-expressions.md)|用于指示一个值，以提供作为计算表达式的结果。|
|`return!`|[计算表达式](computation-expressions.md)<br /><br />[异步工作流](asynchronous-workflows.md)|用于指示计算表达式，计算时，提供包含计算表达式的结果。|
|`select`|[查询表达式](query-expressions.md)|在查询表达式中用于指定哪些字段或要提取的列。 请注意，这是上下文关键字，这意味着，它并不实际的保留的字，其仅行为类似于合适的上下文中的关键字。|
|`static`|[成员](members/index.md)|用于指示方法或属性，可以调用的类型实例情况下或在类型的所有实例之间共享值成员。|
|`struct`|[结构](structures.md)<br /><br />[约束](generics/constraints.md)|用于声明结构类型。<br /><br />也用在泛型参数约束。<br /><br />用于实现 OCaml 模块定义中的兼容性。|
|`then`|[条件表达式：`if...then...else`](conditional-expressions-if-then-else.md)<br /><br />[构造函数](members/constructors.md)|在条件表达式中使用。<br /><br />此外用于在对象构造后执行负面影响。|
|`to`|[循环：`for...to` 表达式](loops-for-to-expression.md)|在中使用`for`循环，以表示一个范围。|
|`true`|[基元类型](primitive-types.md)|用作布尔值文字。|
|`try`|[异常： try...with 表达式](exception-handling/the-try-with-expression.md)<br /><br />[： 异常最后表达式](exception-handling/the-try-finally-expression.md)|用于引入的可能会生成异常的代码块。 一起使用`with`或`finally`。|
|`type`|[F# 类型](fsharp-types.md)<br /><br />[类](classes.md)<br /><br />[记录](records.md)<br /><br />[结构](structures.md)<br /><br />[枚举](enumerations.md)<br /><br />[可区分联合](discriminated-unions.md)<br /><br />[类型缩写](type-abbreviations.md)<br /><br />[度量单位](units-of-measure.md)|用于声明类、 记录、 结构、 可区分的联合、 枚举类型、 度量单位，或键入缩写。|
|`upcast`|[强制转换和转换](casting-and-conversions.md)|用于将转换为更高版本的继承链中的类型。|
|`use`|[资源管理：`use` 关键字](resource-management-the-use-keyword.md)|而不是使用`let`需要的值`Dispose`来释放资源调用。|
|`use!`|[计算表达式](computation-expressions.md)<br /><br />[异步工作流](asynchronous-workflows.md)|而不是使用`let!`在异步工作流和需要的值其他计算表达式`Dispose`来释放资源调用。|
|`val`|[显式字段：`val` 关键字](members/explicit-fields-the-val-keyword.md)<br /><br />[签名](signatures.md)<br /><br />[成员](members/index.md)|用于签名以指示值，或中的类型来声明的成员，在有限情况下。|
|`void`|[基元类型](primitive-types.md)|指示.NET`void`类型。 与其他.NET 语言进行互操作时使用。|
|`when`|[约束](generics/constraints.md)|用于布尔条件 (*时临界条件*) 模式匹配并引入泛型类型参数的约束子句。|
|`while`|[循环：`while...do` 表达式](loops-while-do-expression.md)|引入了循环构造。|
|`with`|[match 表达式](match-expressions.md)<br /><br />[对象表达式](object-expressions.md)<br /><br />[复制和更新记录表达式](copy-and-update-record-expressions.md)<br /><br />[类型扩展](type-extensions.md)<br /><br />[异常：`try...with` 表达式](exception-handling/the-try-with-expression.md)|一起使用`match`匹配表达式的模式中的关键字。 此外使用对象表达式、 记录复制表达式和类型扩展引入的成员定义，并引入异常处理程序。|
|`yield`|[序列](sequences.md)|用于为序列表达式生成的序列值。|
|`yield!`|[计算表达式](computation-expressions.md)<br /><br />[异步工作流](asynchronous-workflows.md)|在计算表达式中用于将给定的计算表达式的结果追加到集合中包含的计算表达式的结果。|

以下令牌将保留在 F # 中，因为它们是 OCaml 语言中的关键字：

* `asr`
* `land`
* `lor`
* `lsl`
* `lsr`
* `lxor`
* `mod`
* `sig`

如果你使用`--mlcompatibility`编译器选项时，上述关键字都是可供使用作为标识符。

以下令牌保留为未来扩展的 F # 语言关键字作为：

* `atomic`
* `break`
* `checked`
* `component`
* `const`
* `constraint`
* `constructor`
* `continue`
* `eager`
* `event`
* `external`
* `fixed`
* `functor`
* `include`
* `method`
* `mixin`
* `object`
* `parallel`
* `process`
* `protected`
* `pure`
* `sealed`
* `tailcall`
* `trait`
* `virtual`
* `volatile`

## <a name="see-also"></a>另请参阅
[F# 语言参考](index.md)

[符号和运算符参考](symbol-and-operator-reference/index.md)

[编译器选项](compiler-options.md)
