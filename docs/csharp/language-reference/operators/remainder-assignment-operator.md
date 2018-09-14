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
# <a name="-operator-c-reference"></a><span data-ttu-id="cb617-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="cb617-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="cb617-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="cb617-103">The remainder assignment operator.</span></span>

<span data-ttu-id="cb617-104">使用 `%=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="cb617-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="cb617-105">等效于</span><span class="sxs-lookup"><span data-stu-id="cb617-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="cb617-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="cb617-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="cb617-107">所有数值类型都支持[余数运算符](remainder-operator.md)`%`，该运算符计算其操作数相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="cb617-107">The [remainder operator](remainder-operator.md) `%` is supported by all numeric types and computes the remainder after division of its operands.</span></span>

<span data-ttu-id="cb617-108">如果用户定义类型[重载](../keywords/operator.md)[余数运算符](remainder-operator.md) `%`，余数赋值运算符 `%=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="cb617-108">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="cb617-109">下面的示例演示 `%=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="cb617-109">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="cb617-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="cb617-110">See also</span></span>

- [<span data-ttu-id="cb617-111">C# 参考</span><span class="sxs-lookup"><span data-stu-id="cb617-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cb617-112">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="cb617-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cb617-113">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="cb617-113">C# Operators</span></span>](index.md)
