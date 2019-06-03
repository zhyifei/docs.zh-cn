---
title: typeof - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
ms.openlocfilehash: 7962a3d0a5885e64701cb9d9a4d689cd982b9830
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422551"
---
# <a name="typeof-c-reference"></a><span data-ttu-id="8c63d-102">typeof（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="8c63d-102">typeof (C# Reference)</span></span>

<span data-ttu-id="8c63d-103">用于为类型获取 <xref:System.Type?displayProperty=nameWithType> 对象。</span><span class="sxs-lookup"><span data-stu-id="8c63d-103">Used to obtain the <xref:System.Type?displayProperty=nameWithType> object for a type.</span></span> <span data-ttu-id="8c63d-104">`typeof` 表达式采用以下格式：</span><span class="sxs-lookup"><span data-stu-id="8c63d-104">A `typeof` expression takes the following form:</span></span>

```csharp
System.Type type = typeof(int);
```

## <a name="remarks"></a><span data-ttu-id="8c63d-105">备注</span><span class="sxs-lookup"><span data-stu-id="8c63d-105">Remarks</span></span>

<span data-ttu-id="8c63d-106">若要获取表达式的运行时类型，可以使用 .NET Framework 方法 <xref:System.Object.GetType%2A>，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="8c63d-106">To obtain the run-time type of an expression, you can use the .NET Framework method <xref:System.Object.GetType%2A>, as in the following example:</span></span>

```csharp
int i = 0;
System.Type type = i.GetType();
```

<span data-ttu-id="8c63d-107">不能重载 `typeof` 运算符。</span><span class="sxs-lookup"><span data-stu-id="8c63d-107">The `typeof` operator cannot be overloaded.</span></span>

<span data-ttu-id="8c63d-108">`typeof` 运算符也可用于开放式泛型类型。</span><span class="sxs-lookup"><span data-stu-id="8c63d-108">The `typeof` operator can also be used on open generic types.</span></span> <span data-ttu-id="8c63d-109">具有多个类型参数的类型必须在规范中具有适当数量的逗号。</span><span class="sxs-lookup"><span data-stu-id="8c63d-109">Types with more than one type parameter must have the appropriate number of commas in the specification.</span></span> <span data-ttu-id="8c63d-110">例如，<xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> 有两个类型参数，因此，请使用一个逗号：</span><span class="sxs-lookup"><span data-stu-id="8c63d-110">For example, the <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWIthType> has two type arguments, so you use one comma:</span></span>

```csharp
Type t = typeof(System.Collection.Generic.Dictionary<,>);
```

<span data-ttu-id="8c63d-111">以下示例显示如何确定方法的返回类型是否为泛型 <xref:System.Collections.Generic.IEnumerable%601>。</span><span class="sxs-lookup"><span data-stu-id="8c63d-111">The following example shows how to determine whether the return type of a method is a generic <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="8c63d-112">如果返回类型不是 <xref:System.Collections.Generic.IEnumerable%601> 泛型类型，则 <xref:System.Type.GetInterface%2A?displayProperty=nameWithType> 将返回 `null`。</span><span class="sxs-lookup"><span data-stu-id="8c63d-112"><xref:System.Type.GetInterface%2A?displayProperty=nameWithType> will return `null` if the return type is not an <xref:System.Collections.Generic.IEnumerable%601> generic type.</span></span>

[!code-csharp[typeof_3.cs](~/samples/snippets/csharp/keywords/typeof/typeof_3.cs)]

## <a name="example"></a><span data-ttu-id="8c63d-113">示例</span><span class="sxs-lookup"><span data-stu-id="8c63d-113">Example</span></span>

[!code-csharp[csrefKeywordsOperator#12](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#12)] 

## <a name="example"></a><span data-ttu-id="8c63d-114">示例</span><span class="sxs-lookup"><span data-stu-id="8c63d-114">Example</span></span>

<span data-ttu-id="8c63d-115">此示例使用 <xref:System.Object.GetType%2A> 方法来确定用于包含数值计算结果的类型。</span><span class="sxs-lookup"><span data-stu-id="8c63d-115">This sample uses the <xref:System.Object.GetType%2A> method to determine the type that is used to contain the result of a numeric calculation.</span></span> <span data-ttu-id="8c63d-116">这取决于所得数字的存储要求。</span><span class="sxs-lookup"><span data-stu-id="8c63d-116">This depends on the storage requirements of the resulting number.</span></span>

[!code-csharp[csrefKeywordsOperator#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsOperator/CS/csrefKeywordsOperators.cs#13)]

## <a name="c-language-specification"></a><span data-ttu-id="8c63d-117">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="8c63d-117">C# language specification</span></span>

<span data-ttu-id="8c63d-118">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的 [typeof 运算符](~/_csharplang/spec/expressions.md#the-typeof-operator)。</span><span class="sxs-lookup"><span data-stu-id="8c63d-118">For more information, see [The typeof operator](~/_csharplang/spec/expressions.md#the-typeof-operator) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="8c63d-119">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="8c63d-119">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c63d-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="8c63d-120">See also</span></span>

- <xref:System.Type?displayProperty=nameWithType>
- [<span data-ttu-id="8c63d-121">C# 参考</span><span class="sxs-lookup"><span data-stu-id="8c63d-121">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="8c63d-122">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="8c63d-122">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="8c63d-123">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="8c63d-123">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="8c63d-124">is</span><span class="sxs-lookup"><span data-stu-id="8c63d-124">is</span></span>](../../../csharp/language-reference/keywords/is.md)
