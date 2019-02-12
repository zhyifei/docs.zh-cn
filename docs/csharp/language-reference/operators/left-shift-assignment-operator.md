---
title: <<= 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- <<=_CSharpKeyword
helpviewer_keywords:
- <<= operator (left-shift assignment) [C#]
- left shift assignment operator (<<=) [C#]
ms.assetid: 3bc99c78-1edb-4827-86fc-bce6c3048871
ms.openlocfilehash: 0a005efa19be24f9adbf9031f562a30f9c1b0e34
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55258729"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c1f08-102">\<\<= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c1f08-102">\<\<= operator (C# Reference)</span></span>

<span data-ttu-id="c1f08-103">左移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="c1f08-103">The left-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="c1f08-104">备注</span><span class="sxs-lookup"><span data-stu-id="c1f08-104">Remarks</span></span>

<span data-ttu-id="c1f08-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="c1f08-105">An expression of the form</span></span>

```csharp
x <<= y
```

<span data-ttu-id="c1f08-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="c1f08-106">is evaluated as</span></span>

```csharp
x = x << y
```

<span data-ttu-id="c1f08-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="c1f08-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="c1f08-108">[<< 运算符](left-shift-operator.md) 将 `x` 向左移动 `y` 指定的位数。</span><span class="sxs-lookup"><span data-stu-id="c1f08-108">The [<< operator](left-shift-operator.md) shifts `x` left by the number of bits specified by `y`.</span></span>

<span data-ttu-id="c1f08-109">不能直接重载 `<<=` 运算符，但用户定义的类型可重载 [<< 运算符](left-shift-operator.md)（参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="c1f08-109">The `<<=` operator cannot be overloaded directly, but user-defined types can overload the [<< operator](left-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="c1f08-110">示例</span><span class="sxs-lookup"><span data-stu-id="c1f08-110">Example</span></span>

[!code-csharp[csRefOperators#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#12)]

## <a name="see-also"></a><span data-ttu-id="c1f08-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c1f08-111">See also</span></span>

- [<span data-ttu-id="c1f08-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c1f08-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c1f08-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c1f08-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c1f08-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c1f08-114">C# Operators</span></span>](index.md)
