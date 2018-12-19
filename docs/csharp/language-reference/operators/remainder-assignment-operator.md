---
title: '%= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: d0732f9578b64c894ecc1d3bb15cee11a8d5b6a3
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53245556"
---
# <a name="-operator-c-reference"></a>%= 运算符（C# 参考）

余数赋值运算符。

使用 `%=` 运算符的表达式，例如  

```csharp
x %= y
```  

等效于  

```csharp
x = x % y
```  

不同的是 `x` 只计算一次。
  
[余数运算符](remainder-operator.md) `%` 其计算操作数相除后的余数。 它受所有数值类型支持。

如果用户定义类型[重载](../keywords/operator.md)[余数运算符](remainder-operator.md) `%`，余数赋值运算符 `%=` 为隐式重载。
  
下面的示例演示 `%=` 运算符的用法：

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
