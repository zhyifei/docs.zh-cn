---
title: -> 运算符 - C# 参考
ms.custom: seodec18
ms.date: 11/26/2018
f1_keywords:
- ->_CSharpKeyword
helpviewer_keywords:
- member access operator (->) [C#]
- -> operator [C#]
ms.assetid: e39ccdc1-f1ff-4a92-bf1d-ac2c8c11316a
ms.openlocfilehash: be74f02a85aa05cdab32768ed38222fc4d9289b1
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55255362"
---
# <a name="--operator-c-reference"></a><span data-ttu-id="9d6a1-102">-> 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="9d6a1-102">-> Operator (C# Reference)</span></span>

<span data-ttu-id="9d6a1-103">指针成员访问运算符 `->` 结合了指针间接和成员访问。</span><span class="sxs-lookup"><span data-stu-id="9d6a1-103">The pointer member access operator `->` combines pointer indirection and member access.</span></span>

<span data-ttu-id="9d6a1-104">如果 `x` 是类型为 `T*` 的指针而 `y` 是 `T` 的可访问成员，则这种形式的表达式</span><span class="sxs-lookup"><span data-stu-id="9d6a1-104">If `x` is a pointer of the type `T*` and `y` is an accessible member of `T`, an expression of the form</span></span>

```csharp
x->y
```

<span data-ttu-id="9d6a1-105">等效于</span><span class="sxs-lookup"><span data-stu-id="9d6a1-105">is equivalent to</span></span>

```csharp
(*x).y
```

<span data-ttu-id="9d6a1-106">`->` 运算符需要[不安全](../keywords/unsafe.md)上下文。</span><span class="sxs-lookup"><span data-stu-id="9d6a1-106">The `->` operator requires [unsafe](../keywords/unsafe.md) context.</span></span>

<span data-ttu-id="9d6a1-107">有关详细信息，请参阅[如何：使用指针访问成员](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md)。</span><span class="sxs-lookup"><span data-stu-id="9d6a1-107">For more information, see [How to: access a member with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-a-member-with-a-pointer.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="9d6a1-108">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="9d6a1-108">Operator overloadability</span></span>

<span data-ttu-id="9d6a1-109">不能重载 `->` 运算符。</span><span class="sxs-lookup"><span data-stu-id="9d6a1-109">The `->` operator cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9d6a1-110">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="9d6a1-110">C# language specification</span></span>

<span data-ttu-id="9d6a1-111">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[指针成员访问](~/_csharplang/spec/unsafe-code.md#pointer-member-access)部分。</span><span class="sxs-lookup"><span data-stu-id="9d6a1-111">For more information, see the [Pointer member access](~/_csharplang/spec/unsafe-code.md#pointer-member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d6a1-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9d6a1-112">See also</span></span>

- [<span data-ttu-id="9d6a1-113">C# 参考</span><span class="sxs-lookup"><span data-stu-id="9d6a1-113">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9d6a1-114">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="9d6a1-114">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9d6a1-115">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="9d6a1-115">C# Operators</span></span>](index.md)
- [<span data-ttu-id="9d6a1-116">指针类型</span><span class="sxs-lookup"><span data-stu-id="9d6a1-116">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
