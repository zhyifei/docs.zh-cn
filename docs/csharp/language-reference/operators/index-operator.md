---
title: '[] 运算符 - C# 参考'
ms.custom: seodec18
ms.date: 01/10/2019
f1_keywords:
- '[]_CSharpKeyword'
helpviewer_keywords:
- subscript operator [C#]
- square brackets [ ] operator [C#]
- '[] operator [C#]'
- indexing operator [C#]
ms.assetid: 5c16bb45-88f7-45ff-b42c-1af1972b042c
ms.openlocfilehash: 948ce238058307631cf0e5a7a5e3d72664233052
ms.sourcegitcommit: 5c36aaa8299a2437c155700c810585aff19edbec
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "54333390"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="35de3-102">[] 运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="35de3-102">[] operator (C# Reference)</span></span>

<span data-ttu-id="35de3-103">方括号 `[]` 通常用于数组、索引器或指针元素访问。</span><span class="sxs-lookup"><span data-stu-id="35de3-103">Square brackets, `[]`, are typically used for array, indexer, or pointer element access.</span></span>

<span data-ttu-id="35de3-104">有关指针元素访问的详细信息，请参阅[如何：通过指针访问数组元素](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md)。</span><span class="sxs-lookup"><span data-stu-id="35de3-104">For more information about pointer element access, see [How to: access an array element with a pointer](../../programming-guide/unsafe-code-pointers/how-to-access-an-array-element-with-a-pointer.md).</span></span>

<span data-ttu-id="35de3-105">方括号还用于指定[属性](../../programming-guide/concepts/attributes/index.md)：</span><span class="sxs-lookup"><span data-stu-id="35de3-105">You also use square brackets to specify [attributes](../../programming-guide/concepts/attributes/index.md):</span></span>

```csharp
[System.Diagnostics.Conditional("DEBUG")]
void TraceMethod() {}
```

## <a name="array-access"></a><span data-ttu-id="35de3-106">数组访问</span><span class="sxs-lookup"><span data-stu-id="35de3-106">Array access</span></span>

<span data-ttu-id="35de3-107">下面的示例演示如何访问数组元素：</span><span class="sxs-lookup"><span data-stu-id="35de3-107">The following example demonstrates how to access array elements:</span></span>

[!code-csharp-interactive[array access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Arrays)]

<span data-ttu-id="35de3-108">如果数组索引超出数组相应维度的边界，将引发 <xref:System.IndexOutOfRangeException>。</span><span class="sxs-lookup"><span data-stu-id="35de3-108">If an array index is outside the bounds of the corresponding dimension of an array, an <xref:System.IndexOutOfRangeException> is thrown.</span></span>

<span data-ttu-id="35de3-109">如前面的示例所示，还可以在声明数组类型和实例化数组实例时使用方括号。</span><span class="sxs-lookup"><span data-stu-id="35de3-109">As the preceding example shows, you also use square brackets in declaration of an array type and instantiation of array instances.</span></span>

<span data-ttu-id="35de3-110">有关数组的详细信息，请参阅[数组](../../programming-guide/arrays/index.md)。</span><span class="sxs-lookup"><span data-stu-id="35de3-110">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="indexer-access"></a><span data-ttu-id="35de3-111">索引器访问</span><span class="sxs-lookup"><span data-stu-id="35de3-111">Indexer access</span></span>

<span data-ttu-id="35de3-112">下面的示例使用 .NET <xref:System.Collections.Generic.Dictionary%602>类型来演示索引器访问：</span><span class="sxs-lookup"><span data-stu-id="35de3-112">The following example uses .NET <xref:System.Collections.Generic.Dictionary%602> type to demonstrate indexer access:</span></span>

[!code-csharp-interactive[indexer access](~/samples/snippets/csharp/language-reference/operators/IndexOperatorExamples.cs#Indexers)]

<span data-ttu-id="35de3-113">使用索引器，可通过类似于编制数组索引的方式对用户定义类型的实例编制索引。</span><span class="sxs-lookup"><span data-stu-id="35de3-113">Indexers allow you to index instances of a user-defined type in the similar way as array indexing.</span></span> <span data-ttu-id="35de3-114">与必须是整数的数组索引不同，可以将索引器参数声明为任何类型。</span><span class="sxs-lookup"><span data-stu-id="35de3-114">Unlike array indices, which must be integer, the indexer arguments can be declared to be of any type.</span></span>

<span data-ttu-id="35de3-115">有关索引器的详细信息，请参阅[索引器](../../programming-guide/indexers/index.md)。</span><span class="sxs-lookup"><span data-stu-id="35de3-115">For more information about indexers, see [Indexers](../../programming-guide/indexers/index.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="35de3-116">运算符可重载性</span><span class="sxs-lookup"><span data-stu-id="35de3-116">Operator overloadability</span></span>

<span data-ttu-id="35de3-117">元素访问 `[]` 不被视为可重载运算符。</span><span class="sxs-lookup"><span data-stu-id="35de3-117">Element access `[]` is not considered an overloadable operator.</span></span> <span data-ttu-id="35de3-118">使用[索引器](../../programming-guide/indexers/index.md)以支持对用户定义的类型编制索引。</span><span class="sxs-lookup"><span data-stu-id="35de3-118">Use [indexers](../../programming-guide/indexers/index.md) to support indexing with user-defined types.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="35de3-119">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="35de3-119">C# language specification</span></span>

<span data-ttu-id="35de3-120">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[元素访问](~/_csharplang/spec/expressions.md#element-access)和[指针元素访问](~/_csharplang/spec/unsafe-code.md#pointer-element-access)部分。</span><span class="sxs-lookup"><span data-stu-id="35de3-120">For more information, see the [Element access](~/_csharplang/spec/expressions.md#element-access) and [Pointer element access](~/_csharplang/spec/unsafe-code.md#pointer-element-access) sections of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35de3-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="35de3-121">See also</span></span>

- [<span data-ttu-id="35de3-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="35de3-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="35de3-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="35de3-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="35de3-124">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="35de3-124">C# Operators</span></span>](index.md)
- [<span data-ttu-id="35de3-125">数组</span><span class="sxs-lookup"><span data-stu-id="35de3-125">Arrays</span></span>](../../programming-guide/arrays/index.md)
- [<span data-ttu-id="35de3-126">索引器</span><span class="sxs-lookup"><span data-stu-id="35de3-126">Indexers</span></span>](../../programming-guide/indexers/index.md)
- [<span data-ttu-id="35de3-127">指针类型</span><span class="sxs-lookup"><span data-stu-id="35de3-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="35de3-128">特性</span><span class="sxs-lookup"><span data-stu-id="35de3-128">Attributes</span></span>](../../programming-guide/concepts/attributes/index.md)