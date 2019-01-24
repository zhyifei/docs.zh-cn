---
title: '|= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '|=_CSharpKeyword'
helpviewer_keywords:
- OR assignment operator (|=) [C#]
- '|= operator (OR assignment) [C#]'
ms.assetid: 8315b8cf-dd15-402f-92f0-c7db931696ca
ms.openlocfilehash: f4f7806c8679af400a371decd0c367929b3fb81d
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333260"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="c8cbb-102">|= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c8cbb-102">|= operator (C# Reference)</span></span>

<span data-ttu-id="c8cbb-103">OR 赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="c8cbb-103">The OR assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="c8cbb-104">备注</span><span class="sxs-lookup"><span data-stu-id="c8cbb-104">Remarks</span></span>

<span data-ttu-id="c8cbb-105">使用 `|=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="c8cbb-105">An expression using the `|=` assignment operator, such as</span></span>

```csharp
x |= y
```

<span data-ttu-id="c8cbb-106">等效于</span><span class="sxs-lookup"><span data-stu-id="c8cbb-106">is equivalent to</span></span>

```csharp
x = x | y
```

<span data-ttu-id="c8cbb-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="c8cbb-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="c8cbb-108">[&#124; 运算符](or-operator.md) 对整型操作数执行按位逻辑 OR 运算，对 bool 操作数执行逻辑 OR 运算。</span><span class="sxs-lookup"><span data-stu-id="c8cbb-108">The [&#124; operator](or-operator.md) performs a bitwise logical OR operation on integral operands and logical OR on bool operands.</span></span>

<span data-ttu-id="c8cbb-109">不能直接重载 `|=` 运算符，但用户定义的类型可重载 [&#124; 运算符](or-operator.md)（请参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="c8cbb-109">The `|=` operator cannot be overloaded directly, but user-defined types can overload the [&#124; operator](or-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="c8cbb-110">示例</span><span class="sxs-lookup"><span data-stu-id="c8cbb-110">Example</span></span>

[!code-csharp[csRefOperators#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#10)]

## <a name="see-also"></a><span data-ttu-id="c8cbb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="c8cbb-111">See also</span></span>

- [<span data-ttu-id="c8cbb-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c8cbb-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8cbb-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c8cbb-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8cbb-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c8cbb-114">C# operators</span></span>](index.md)