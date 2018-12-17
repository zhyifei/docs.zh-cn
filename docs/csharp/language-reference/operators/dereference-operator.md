---
title: -&gt; 运算符 - C# 参考
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: bb1ccd026f403e68565c5c7681943d8017578d01
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53234885"
---
# <a name="-gt-operator-c-reference"></a><span data-ttu-id="c4acd-102">-&gt; 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="c4acd-102">-&gt; Operator (C# Reference)</span></span>

<span data-ttu-id="c4acd-103">指针成员访问运算符 `->` 结合了指针间接和成员访问。</span><span class="sxs-lookup"><span data-stu-id="c4acd-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="c4acd-104">如果 `x` 是类型为 `T*` 的指针而 `y` 是 `T` 的可访问成员，则这种形式的表达式</span><span class="sxs-lookup"><span data-stu-id="c4acd-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="c4acd-105">等效于</span><span class="sxs-lookup"><span data-stu-id="c4acd-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="c4acd-106">`->` 运算符需要[不安全](../keywords/unsafe.md)上下文。</span><span class="sxs-lookup"><span data-stu-id="c4acd-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="c4acd-107">有关详细信息，请参阅[如何：使用指针访问成员](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md)。</span><span class="sxs-lookup"><span data-stu-id="c4acd-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="c4acd-108">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="c4acd-108">Operator overloadability</span></span>

<span data-ttu-id="c4acd-109">不能重载 `->` 运算符。</span><span class="sxs-lookup"><span data-stu-id="c4acd-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c4acd-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="c4acd-110">C# language specification</span></span>

<span data-ttu-id="c4acd-111">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[指针成员访问](~/_csharplang/spec/unsafe-code.md#pointer-member-access)部分。</span><span class="sxs-lookup"><span data-stu-id="c4acd-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4acd-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="c4acd-112">See also</span></span>

- [<span data-ttu-id="c4acd-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="c4acd-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c4acd-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c4acd-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c4acd-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="c4acd-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="c4acd-116">指针类型</span><span class="sxs-lookup"><span data-stu-id="c4acd-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
