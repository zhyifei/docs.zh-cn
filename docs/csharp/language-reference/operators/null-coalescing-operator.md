---
title: ?? 运算符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- ??_CSharpKeyword
helpviewer_keywords:
- coalesce operator [C#]
- ?? operator [C#]
- conditional-AND operator (&&) [C#]
ms.assetid: 088b1f0d-c1af-4fe1-b4b8-196fd5ea9132
ms.openlocfilehash: e1e981f9ec6a87f6e7de1900008520cde8e46095
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633937"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="ae073-103">??</span><span class="sxs-lookup"><span data-stu-id="ae073-103">??</span></span> <span data-ttu-id="ae073-104">运算符（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="ae073-104">operator (C# Reference)</span></span>

<span data-ttu-id="ae073-105">`??` 运算符称作 null 合并运算符。</span><span class="sxs-lookup"><span data-stu-id="ae073-105">The `??` operator is called the null-coalescing operator.</span></span>  <span data-ttu-id="ae073-106">如果此运算符的左操作数不为 null，则此运算符将返回左操作数；否则返回右操作数。</span><span class="sxs-lookup"><span data-stu-id="ae073-106">It returns the left-hand operand if the operand is not null; otherwise it returns the right hand operand.</span></span>

## <a name="remarks"></a><span data-ttu-id="ae073-107">备注</span><span class="sxs-lookup"><span data-stu-id="ae073-107">Remarks</span></span>

<span data-ttu-id="ae073-108">可以为 null 的类型可以表示类型的域中的值，或者值可以是未定义的（在这种情况下，值为 null）。</span><span class="sxs-lookup"><span data-stu-id="ae073-108">A nullable type can represent a value from the type’s domain, or the value can be undefined (in which case the value is null).</span></span> <span data-ttu-id="ae073-109">如果左操作数具有一个值为 null 的可以为 null 的类型，则可使用 `??` 运算符的语法表现力来返回适当的值（右操作数）。</span><span class="sxs-lookup"><span data-stu-id="ae073-109">You can use the `??` operator’s syntactic expressiveness to return an appropriate value (the right hand operand) when the left operand has a nullable type whose value is null.</span></span> <span data-ttu-id="ae073-110">如果在尝试将可以为 null 值的类型分配给不可以为 null 值的类型时没有使用 `??` 运算符，则会生成编译时错误。</span><span class="sxs-lookup"><span data-stu-id="ae073-110">If you try to assign a nullable value type to a non-nullable value type without using the `??` operator, you will generate a compile-time error.</span></span> <span data-ttu-id="ae073-111">如果使用强制转换，且当前未定义可以为 null 值的类型，则会引发 `InvalidOperationException` 异常。</span><span class="sxs-lookup"><span data-stu-id="ae073-111">If you use a cast, and the nullable value type is currently undefined, an `InvalidOperationException` exception will be thrown.</span></span>

<span data-ttu-id="ae073-112">有关详细信息，请参阅[可以为 null 的类型](../../programming-guide/nullable-types/index.md)。</span><span class="sxs-lookup"><span data-stu-id="ae073-112">For more information, see [Nullable Types](../../programming-guide/nullable-types/index.md).</span></span>

<span data-ttu-id="ae073-113">?? 的结果</span><span class="sxs-lookup"><span data-stu-id="ae073-113">The result of a ??</span></span> <span data-ttu-id="ae073-114">不能将运算符视为常量，即使其两个参数都是常量。</span><span class="sxs-lookup"><span data-stu-id="ae073-114">operator is not considered to be a constant even if both its arguments are constants.</span></span>

## <a name="example"></a><span data-ttu-id="ae073-115">示例</span><span class="sxs-lookup"><span data-stu-id="ae073-115">Example</span></span>

[!code-csharp[csRefOperators#53](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefOperators/CS/csrefOperators.cs#53)]

## <a name="c-language-specification"></a><span data-ttu-id="ae073-116">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="ae073-116">C# language specification</span></span>

<span data-ttu-id="ae073-117">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [null 合并运算符](~/_csharplang/spec/expressions.md#the-null-coalescing-operator)。</span><span class="sxs-lookup"><span data-stu-id="ae073-117">For more information, see [The null coalescing operator](~/_csharplang/spec/expressions.md#the-null-coalescing-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="ae073-118">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="ae073-118">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae073-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="ae073-119">See also</span></span>

- [<span data-ttu-id="ae073-120">C# 参考</span><span class="sxs-lookup"><span data-stu-id="ae073-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ae073-121">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="ae073-121">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ae073-122">C# 运算符</span><span class="sxs-lookup"><span data-stu-id="ae073-122">C# operators</span></span>](index.md)
- [<span data-ttu-id="ae073-123">可以为 null 的类型</span><span class="sxs-lookup"><span data-stu-id="ae073-123">Nullable Types</span></span>](../../programming-guide/nullable-types/index.md)
- [<span data-ttu-id="ae073-124">“提升”的准确含义是什么？</span><span class="sxs-lookup"><span data-stu-id="ae073-124">What Exactly Does 'Lifted' mean?</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/06/27/what-exactly-does-lifted-mean/)
