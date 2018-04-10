---
title: base（C# 参考）
description: 了解 base 关键字，使用它从 C# 中的派生类中访问基类的成员。
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- base
- BaseClass.BaseClass
- base_CSharpKeyword
helpviewer_keywords:
- base keyword [C#]
ms.assetid: 8b645dbe-1a33-49b8-8716-1c401f9a5ea5
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 1bbaa0cc05b35f822113bc3a8c3cde966b1484ef
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="base-c-reference"></a>base（C# 参考）

`base` 关键字用于从派生类中访问基类的成员：

- 调用基类上已被其他方法重写的方法。

- 指定创建派生类实例时应调用的基类构造函数。

仅允许基类访问在构造函数、实例方法或实例属性访问器中进行。

从静态方法中使用 `base` 关键字是错误的。

所访问的基类是类声明中指定的基类。 例如，如果指定 `class ClassB : ClassA`，则从 ClassB 访问 ClassA 的成员，而不考虑 ClassA 的基类。

## <a name="example"></a>示例
在本例中，基类 `Person` 和派生类 `Employee` 都有一个名为 `Getinfo` 的方法。 通过使用 `base` 关键字，可以从派生类中调用基类的 `Getinfo` 方法。

[!code-csharp[csrefKeywordsAccess#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_1.cs)]

有关其他示例，请参阅 [new](../../../csharp/language-reference/keywords/new.md)、[virtual](../../../csharp/language-reference/keywords/virtual.md) 和 [override](../../../csharp/language-reference/keywords/override.md)。

## <a name="example"></a>示例
本示例显示如何指定在创建派生类实例时调用的基类构造函数。

[!code-csharp[csrefKeywordsAccess#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/base_2.cs)]

## <a name="c-language-specification"></a>C# 语言规范
[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>请参阅
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [this](../../../csharp/language-reference/keywords/this.md)