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
# <a name="-operator-c-reference"></a><span data-ttu-id="5663e-102">%= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="5663e-102">%= Operator (C# Reference)</span></span>

<span data-ttu-id="5663e-103">余数赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="5663e-103">The remainder assignment operator.</span></span>

<span data-ttu-id="5663e-104">使用 `%=` 运算符的表达式，例如</span><span class="sxs-lookup"><span data-stu-id="5663e-104">An expression using the `%=` operator, such as</span></span>  

```csharp
x %= y
```  

<span data-ttu-id="5663e-105">等效于</span><span class="sxs-lookup"><span data-stu-id="5663e-105">is equivalent to</span></span>  

```csharp
x = x % y
```  

<span data-ttu-id="5663e-106">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="5663e-106">except that `x` is only evaluated once.</span></span>
  
<span data-ttu-id="5663e-107">[余数运算符](remainder-operator.md) `%` 其计算操作数相除后的余数。</span><span class="sxs-lookup"><span data-stu-id="5663e-107">The [remainder operator](remainder-operator.md) `%` computes the remainder after division of its operands.</span></span> <span data-ttu-id="5663e-108">它受所有数值类型支持。</span><span class="sxs-lookup"><span data-stu-id="5663e-108">It's supported by all numeric types.</span></span>

<span data-ttu-id="5663e-109">如果用户定义类型[重载](../keywords/operator.md)[余数运算符](remainder-operator.md) `%`，余数赋值运算符 `%=` 为隐式重载。</span><span class="sxs-lookup"><span data-stu-id="5663e-109">If a user-defined type [overloads](../keywords/operator.md) the [remainder operator](remainder-operator.md) `%`, the remainder assignment operator `%=` is implicitly overloaded.</span></span>
  
<span data-ttu-id="5663e-110">下面的示例演示 `%=` 运算符的用法：</span><span class="sxs-lookup"><span data-stu-id="5663e-110">The following example demonstrates the usage of the `%=` operator:</span></span>

[!code-csharp-interactive[%= example](~/samples/snippets/csharp/language-reference/operators/RemainderExamples.cs#3)]

## <a name="see-also"></a><span data-ttu-id="5663e-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="5663e-111">See also</span></span>

- [<span data-ttu-id="5663e-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="5663e-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="5663e-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="5663e-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="5663e-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="5663e-114">C# Operators</span></span>](index.md)
