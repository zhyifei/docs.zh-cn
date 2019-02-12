---
title: '>>= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 8cc341c14ee1b90fde2abb369c187e57b4ce5c00
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55278975"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="63452-102">>>= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="63452-102">>>= operator (C# Reference)</span></span>

<span data-ttu-id="63452-103">右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="63452-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="63452-104">备注</span><span class="sxs-lookup"><span data-stu-id="63452-104">Remarks</span></span>

<span data-ttu-id="63452-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="63452-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="63452-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="63452-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="63452-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="63452-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="63452-108">[>> 运算符](right-shift-operator.md) 将 `x` 右移 `y` 指定的量。</span><span class="sxs-lookup"><span data-stu-id="63452-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="63452-109">不能直接重载 >>= 运算符，但用户定义的类型可重载 [>> 运算符](right-shift-operator.md)（参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="63452-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="63452-110">示例</span><span class="sxs-lookup"><span data-stu-id="63452-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="63452-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="63452-111">See also</span></span>

- [<span data-ttu-id="63452-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="63452-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="63452-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="63452-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="63452-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="63452-114">C# operators</span></span>](index.md)