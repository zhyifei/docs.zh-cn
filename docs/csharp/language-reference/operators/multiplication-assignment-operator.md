---
title: '*= 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- '*=_CSharpKeyword'
helpviewer_keywords:
- '*= operator [C#]'
- binary multiplication assignment operator (*=) [C#]
ms.assetid: 2e472155-59db-4dbf-bb94-bcccfa1a794d
ms.openlocfilehash: 2038f3b55d46f3503496275b3d25b17663b8c1db
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333429"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="23959-102">\*= 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="23959-102">\*= Operator (C# Reference)</span></span>

<span data-ttu-id="23959-103">二进制乘法赋值运算符。</span><span class="sxs-lookup"><span data-stu-id="23959-103">The binary multiplication assignment operator.</span></span>

## <a name="remarks"></a><span data-ttu-id="23959-104">备注</span><span class="sxs-lookup"><span data-stu-id="23959-104">Remarks</span></span>

<span data-ttu-id="23959-105">使用 `*=` 赋值运算符的表达式，如</span><span class="sxs-lookup"><span data-stu-id="23959-105">An expression using the `*=` assignment operator, such as</span></span>

```csharp
x *= y
```

<span data-ttu-id="23959-106">等效于</span><span class="sxs-lookup"><span data-stu-id="23959-106">is equivalent to</span></span>

```csharp
x = x * y
```

<span data-ttu-id="23959-107">不同的是 `x` 只计算一次。</span><span class="sxs-lookup"><span data-stu-id="23959-107">except that `x` is only evaluated once.</span></span> <span data-ttu-id="23959-108">针对数值类型预定义了 [\* 运算符](multiplication-operator.md)以进行乘法运算。</span><span class="sxs-lookup"><span data-stu-id="23959-108">The [\* operator](multiplication-operator.md) is predefined for numeric types to perform multiplication.</span></span>

<span data-ttu-id="23959-109">不能直接重载 `*=` 运算符，但用户定义的类型可重载 [\* 运算符](multiplication-operator.md)（参阅[运算符](../keywords/operator.md)）。</span><span class="sxs-lookup"><span data-stu-id="23959-109">The `*=` operator cannot be overloaded directly, but user-defined types can overload the [\* operator](multiplication-operator.md) (see [operator](../keywords/operator.md)).</span></span>

## <a name="example"></a><span data-ttu-id="23959-110">示例</span><span class="sxs-lookup"><span data-stu-id="23959-110">Example</span></span>

[!code-csharp[csRefOperators#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#13)]

## <a name="see-also"></a><span data-ttu-id="23959-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="23959-111">See also</span></span>

- [<span data-ttu-id="23959-112">C# 参考</span><span class="sxs-lookup"><span data-stu-id="23959-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="23959-113">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="23959-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="23959-114">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="23959-114">C# Operators</span></span>](index.md)
