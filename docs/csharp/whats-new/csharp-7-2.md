---
title: "什么是 C# 7.2 中的新增功能"
description: "C# 7.2 中的新增功能概述。"
keywords: "C# 语言设计中，7.2，Visual Studio 2017，"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: a580a4a3a0a49e97ea8fb96699d1d978a9bc0a64
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="whats-new-in-c-72"></a>什么是 C# 7.2 中的新增功能

C# 7.2 是添加了大量有用的功能的另一个点版本。
对于此版本的一个主题通过避免不必要的副本或分配更有效地工作与值类型。 

其余的功能是小型、 nice 具有的功能。

使用 C# 7.2[语言版本选择](csharp-7-1.md#language-version-selection)要选择的编译器语言版本的配置元素。

在此版本中的新语言功能包括：

* [具有值类型的引用语义](#reference-semantics-with-value-types)
  - 启用使用引用语义的值类型的工作的语法改进的组合。
* [非尾随的命名自变量](#non-trailing-named-arguments)
  - 命名自变量可以跟位置自变量。
* [中数值的前导下划线](#leading-underscores-in-numeric-literals)
  - 数值现在可以在任何打印数字之前的前导下划线。
* [`private protected`访问修饰符](#private-protected)
  - `private protected`访问修饰符将启用为同一程序集中的派生类的访问。

## <a name="reference-semantics-with-value-types"></a>具有值类型的引用语义

7.2 中引入的语言功能允许你在使用引用语义时处理值类型。 它们旨在通过将复制的值类型而不会产生与使用引用类型相关联的内存分配降至最低来提高性能。 这些功能包括：

 - `in`参数，指定自变量是通过引用传递，但不是会修改调用的方法的修饰符。
 - `ref readonly`方法返回时，以指示一种方法通过引用返回其值，但不允许写入该对象上的修饰符。
 - `readonly struct`声明，以指示结构是不可变，并且应作为传递`in`到其成员方法的参数。
 - `ref struct`声明，以指示结构类型直接访问托管的内存，并且必须始终堆栈分配。

你可以阅读有关所有这些详细信息中的更改[值类型与引用语义一起使用](../reference-semantics-with-value-types.md)。

## <a name="non-trailing-named-arguments"></a>非尾随的命名自变量

方法调用现在可以使用命名参数之前位置自变量，当这些命名自变量位于正确位置的参数。 有关详细信息请参阅[命名实参和可选实参](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。

## <a name="leading-underscores-in-numeric-literals"></a>中数值的前导下划线

在 C# 7.0 中的数字分隔符对的支持的实现不允许`_`为文字值的第一个字符。 十六进制值和二进制数字文本可能会立即开始与`_`。 

例如: 

```csharp
int binaryValue = 0b_0101_0101;
```

## `private protected`

最后，新的复合的访问修饰符：`private protected`指示可能由在同一程序集中声明的派生类访问成员。 虽然`protected internal`允许的派生的类或位于同一程序集中的类访问`private protected`限制对同一程序集中所声明的派生类型的访问。

有关详细信息请参阅[访问修饰符](../language-reference/keywords/access-modifiers.md)语言参考中。
