---
title: '&gt;&gt;= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '>>=_CSharpKeyword'
helpviewer_keywords:
- right shift assignment operator (>>=) [C#]
- '>>= operator (right-shift assignment) [C#]'
ms.assetid: b593778c-b9b4-440d-8b29-c1ac22cb81c0
ms.openlocfilehash: 02a9559a5c4086eeed09094c15c3620366ffad8c
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333678"
---
# <a name="gtgt-operator-c-reference"></a><span data-ttu-id="f4463-102">&gt;&gt;= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f4463-102">&gt;&gt;= operator (C# Reference)</span></span>

<span data-ttu-id="f4463-103">右移赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="f4463-103">The right-shift assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="f4463-104">备注</span><span class="sxs-lookup"><span data-stu-id="f4463-104">Remarks</span></span>

<span data-ttu-id="f4463-105">形式如下的表达式</span><span class="sxs-lookup"><span data-stu-id="f4463-105">An expression of the form</span></span>

```csharp
x >>= y
```

<span data-ttu-id="f4463-106">计算结果为</span><span class="sxs-lookup"><span data-stu-id="f4463-106">is evaluated as</span></span>

```csharp
x = x >> y
```

<span data-ttu-id="f4463-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="f4463-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="f4463-108">[>> 运算符](right-shift-operator.md) 将 `x` 右移 `y` 指定的量。</span><span class="sxs-lookup"><span data-stu-id="f4463-108">The [>> operator](right-shift-operator.md) shifts `x` right by an amount specified by `y`.</span></span>

<span data-ttu-id="f4463-109">不能直接重载 >>= 运算符，但用户定义的类型可重载 [>> 运算符](right-shift-operator.md)（参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="f4463-109">The >>= operator cannot be overloaded directly, but user-defined types can overload the [>> operator](right-shift-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="f4463-110">示例</span><span class="sxs-lookup"><span data-stu-id="f4463-110">Example</span></span>

[!code-csharp[csRefOperators#11](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#11)]

## <a name="see-also"></a><span data-ttu-id="f4463-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="f4463-111">See also</span></span>

- [<span data-ttu-id="f4463-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f4463-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f4463-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f4463-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f4463-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="f4463-114">C# operators</span></span>](index.md)