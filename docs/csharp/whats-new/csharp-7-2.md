---
title: "C# 7.2 中的新增功能"
description: "C# 7.2 中的新增功能概述。"
keywords: "C# 语言设计, 7.2, Visual Studio 2017,"
author: billwagner
ms.author: wiwagn
ms.date: 08/16/2017
ms.topic: article
ms.prod: .net
ms.devlang: devlang-csharp
ms.openlocfilehash: 9e7fefde6763dbd5c73c01e45e5652d9f207c213
ms.sourcegitcommit: 2142a4732bb4ff519b9817db4c24a237b9810d4b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/05/2018
---
# <a name="whats-new-in-c-72"></a>C# 7.2 中的新增功能

C# 7.2 又是一个单点版本，它增添了大量有用的功能。
此版本的一项主要功能是避免不必要的复制或分配，进而更有效地处理值类型。 

其余功能很微小，但值得拥有。

C# 7.2 使用[语言版本选择](csharp-7-1.md#language-version-selection)配置元素来选择编译器语言版本。

此版本中新增的语言功能包括：

* [引用语义结合值类型](#reference-semantics-with-value-types)
  - 结合了多项语法改进，可使用引用语义处理值类型。
* [非尾随命名参数](#non-trailing-named-arguments)
  - 命名的参数可后接位置参数。
* [数值文字中的前导下划线](#leading-underscores-in-numeric-literals)
  - 数值文字现可在任何打印数字前放置前导下划线。
* [`private protected` 访问修饰符](#private-protected)
  - `private protected` 访问修饰符允许访问同一程序集中的派生类。

## <a name="reference-semantics-with-value-types"></a>具有值类型的引用语义

利用 7.2 中引入的语言功能，可在使用引用语义时处理值类型。 它们旨在尽量减少值类型的复制，而不造成与引用类型使用相关的内存分配，进而提升性能。 功能包括：

 - 针对实参的 `in` 修饰符，指定形参通过引用传递，但不通过调用方法修改。
 - 针对方法返回的 `ref readonly` 修饰符，指示方法通过引用返回其值，但不允许写入该对象。
 - `readonly struct` 声明，指示结构不可变，且应作为 `in` 参数传递到其成员方法。
 - `ref struct` 声明，指示结构类型直接访问托管的内存，且必须始终分配有堆栈。

若要详细了解所有这些更改，请参阅[结合使用值类型和引用语义](../reference-semantics-with-value-types.md)。

## <a name="non-trailing-named-arguments"></a>非尾随命名参数

方法调用现可使用位于位置参数前面的命名参数（若这些命名参数的位置正确）。 有关详细信息，请参阅[命名参数和可选参数](../programming-guide/classes-and-structs/named-and-optional-arguments.md)。

## <a name="leading-underscores-in-numeric-literals"></a>数值文字中的前导下划线

C# 7.0 中实现了对数字分隔符的支持，但这不允许文字值的第一个字符是 `_`。 十六进制文本和二进制文件现可以 `_` 开头。 

例如:

```csharp
int binaryValue = 0b_0101_0101;
```

## <a name="private-protected-access-modifier"></a>_private protected_ 访问修饰符

最后，新的复合访问修饰符 `private protected` 指示可通过包含同一程序集中声明的类或派生类来访问成员。 虽然 `protected internal` 允许通过同一程序集中的类或派生类进行访问，但 `private protected` 限制对同一程序集中声明的派生类的访问。

有关详细信息，请参阅语言参考中的[访问修饰符](../language-reference/keywords/access-modifiers.md)。
