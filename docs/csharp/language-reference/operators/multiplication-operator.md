---
title: '* 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 02/26/2019
f1_keywords:
- '*_CSharpKeyword'
helpviewer_keywords:
- multiplication operator (*) [C#]
- '* operator [C#]'
ms.assetid: abd9a5f0-9b24-431e-971a-09ee1c45c50e
ms.openlocfilehash: a5e120d26614f1e38cc2f2db02949552140b594e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977339"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="07614-102">\* 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="07614-102">\* operator (C# Reference)</span></span>

<span data-ttu-id="07614-103">支持以下两种形式的 `*` 运算符：一元指针间接运算符或二元乘法运算符。</span><span class="sxs-lookup"><span data-stu-id="07614-103">The `*` operator is supported in two forms: a unary pointer indirection operator or a binary multiplication operator.</span></span>

## <a name="pointer-indirection-operator"></a><span data-ttu-id="07614-104">指针间接运算符</span><span class="sxs-lookup"><span data-stu-id="07614-104">Pointer indirection operator</span></span>

<span data-ttu-id="07614-105">使用一元 `*` 运算符获取指针类型的操作数指向的变量。</span><span class="sxs-lookup"><span data-stu-id="07614-105">Use the unary `*` operator to obtain the variable to which an operand of a pointer type points.</span></span> <span data-ttu-id="07614-106">有关详细信息，请参阅[如何：获取指针变量的值](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md)。</span><span class="sxs-lookup"><span data-stu-id="07614-106">For more information, see [How to: obtain the value of a pointer variable](../../programming-guide/unsafe-code-pointers/how-to-obtain-the-value-of-a-pointer-variable.md).</span></span>

<span data-ttu-id="07614-107">指针间接运算符 `*` 需要 [unsafe](../keywords/unsafe.md) 上下文。</span><span class="sxs-lookup"><span data-stu-id="07614-107">The pointer indirection operator `*` requires [unsafe](../keywords/unsafe.md) context.</span></span>

## <a name="multiplication-operator"></a><span data-ttu-id="07614-108">乘法运算符</span><span class="sxs-lookup"><span data-stu-id="07614-108">Multiplication operator</span></span>

<span data-ttu-id="07614-109">对于数字类型，`*` 运算符计算其操作数的乘积：</span><span class="sxs-lookup"><span data-stu-id="07614-109">For numeric types, the `*` operator computes the product of its operands:</span></span>

[!code-csharp-interactive[multiplication](~/samples/snippets/csharp/language-reference/operators/MultiplicationExamples.cs#Multiply)]

## <a name="operator-overloadability"></a><span data-ttu-id="07614-110">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="07614-110">Operator overloadability</span></span>

<span data-ttu-id="07614-111">用户定义类型可以[重载](../keywords/operator.md)二元 `*` 运算符。</span><span class="sxs-lookup"><span data-stu-id="07614-111">User-defined types can [overload](../keywords/operator.md) a binary `*` operator.</span></span> <span data-ttu-id="07614-112">重载二元 `*` 运算符后，也会隐式重载[乘法赋值运算符](multiplication-assignment-operator.md) `*=`。</span><span class="sxs-lookup"><span data-stu-id="07614-112">When a binary `*` operator is overloaded, the [multiplication assignment operator](multiplication-assignment-operator.md) `*=` is also implicitly overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="07614-113">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="07614-113">C# language specification</span></span>

<span data-ttu-id="07614-114">有关详细信息，请参阅[C# 语言规范](../language-specification/index.md)的[指针间接](~/_csharplang/spec/unsafe-code.md#pointer-indirection)和[乘法运算符](~/_csharplang/spec/expressions.md#multiplication-operator)部分。</span><span class="sxs-lookup"><span data-stu-id="07614-114">For more information, see the [Pointer indirection](~/_csharplang/spec/unsafe-code.md#pointer-indirection) and [Multiplication operator](~/_csharplang/spec/expressions.md#multiplication-operator) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="07614-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="07614-115">See also</span></span>

- [<span data-ttu-id="07614-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="07614-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="07614-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="07614-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="07614-118">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="07614-118">C# Operators</span></span>](index.md)
- [<span data-ttu-id="07614-119">指针类型</span><span class="sxs-lookup"><span data-stu-id="07614-119">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)