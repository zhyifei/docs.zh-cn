---
title: '%= 运算符（C# 参考）'
ms.date: 09/04/2018
f1_keywords:
- '%=_CSharpKeyword'
helpviewer_keywords:
- remainder assignment operator (%=) [C#]
- '%= assignment operator (remainder assignment) [C#]'
ms.assetid: 47e5f068-1d97-4010-bd3b-e21b5d3a77f5
ms.openlocfilehash: c475517666bdadaa457dbb4188808b3a96fcdf0e
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "44085632"
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
  
所有数值类型都支持[余数运算符](remainder-operator.md)`%`，该运算符计算其操作数相除后的余数。

如果用户定义类型[重载](../keywords/operator.md)[余数运算符](remainder-operator.md) `%`，余数赋值运算符 `%=` 为隐式重载。
  
下面的示例演示 `%=` 运算符的用法：

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a>请参阅

- [C# 参考](../index.md)
- [C# 编程指南](../../programming-guide/index.md)
- [C# 运算符](index.md)
