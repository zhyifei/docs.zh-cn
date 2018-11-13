---
title: public 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: b2e09bdb16d6128d69a3eb33cf2cffd4cba60376
ms.sourcegitcommit: 3b1cb8467bd73dee854b604e306c0e7e3882d91a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/07/2018
ms.locfileid: "43518181"
---
# <a name="public-c-reference"></a><span data-ttu-id="39fec-102">public（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="39fec-102">public (C# Reference)</span></span>

<span data-ttu-id="39fec-103">`public` 关键字是类型和类型成员的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="39fec-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="39fec-104">公共访问是允许的最高访问级别。</span><span class="sxs-lookup"><span data-stu-id="39fec-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="39fec-105">对访问公共成员没有限制，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="39fec-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="39fec-106">有关详细信息，请参阅[访问修饰符](../../programming-guide/classes-and-structs/access-modifiers.md)和[可访问性级别](accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="39fec-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="39fec-107">示例</span><span class="sxs-lookup"><span data-stu-id="39fec-107">Example</span></span>

<span data-ttu-id="39fec-108">在下面的示例中，声明了两个类：`PointTest` 和 `MainClass`。</span><span class="sxs-lookup"><span data-stu-id="39fec-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="39fec-109">直接从 `MainClass` 访问 `PointTest` 的公共成员 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="39fec-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="39fec-110">如果将 `public` 访问级别更改为 [private](private.md) 或 [protected](protected.md)，则会收到错误消息：</span><span class="sxs-lookup"><span data-stu-id="39fec-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="39fec-111">“PointTest.y”不可访问，因为它受保护级别限制。</span><span class="sxs-lookup"><span data-stu-id="39fec-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="39fec-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="39fec-112">C# language specification</span></span>  

<span data-ttu-id="39fec-113">有关详细信息，请参阅 [C# 语言规范](../language-specification/index.md)中的[声明的可访问性](~/_csharplang/spec/basic-concepts.md#declared-accessibility)。</span><span class="sxs-lookup"><span data-stu-id="39fec-113">For more information, see [Declared accessibility](~/_csharplang/spec/basic-concepts.md#declared-accessibility) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="39fec-114">该语言规范是 C# 语法和用法的权威资料。</span><span class="sxs-lookup"><span data-stu-id="39fec-114">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="39fec-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="39fec-115">See also</span></span>

- [<span data-ttu-id="39fec-116">C# 参考</span><span class="sxs-lookup"><span data-stu-id="39fec-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39fec-117">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="39fec-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39fec-118">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="39fec-118">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="39fec-119">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="39fec-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="39fec-120">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="39fec-120">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="39fec-121">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="39fec-121">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="39fec-122">修饰符</span><span class="sxs-lookup"><span data-stu-id="39fec-122">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="39fec-123">private</span><span class="sxs-lookup"><span data-stu-id="39fec-123">private</span></span>](private.md)
- [<span data-ttu-id="39fec-124">protected</span><span class="sxs-lookup"><span data-stu-id="39fec-124">protected</span></span>](protected.md)
- [<span data-ttu-id="39fec-125">internal</span><span class="sxs-lookup"><span data-stu-id="39fec-125">internal</span></span>](internal.md)