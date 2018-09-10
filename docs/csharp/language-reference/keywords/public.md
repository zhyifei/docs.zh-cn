---
title: public 关键字（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- public
- public_CSharpKeyword
helpviewer_keywords:
- public keyword [C#]
ms.assetid: 0ae45d16-a551-4b74-9845-57208de1328e
ms.openlocfilehash: 84a3bc49b6eea047d518edc01dab7f2301854b6a
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2018
ms.locfileid: "43484152"
---
# <a name="public-c-reference"></a><span data-ttu-id="f6170-102">public（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="f6170-102">public (C# Reference)</span></span>

<span data-ttu-id="f6170-103">`public` 关键字是类型和类型成员的访问修饰符。</span><span class="sxs-lookup"><span data-stu-id="f6170-103">The `public` keyword is an access modifier for types and type members.</span></span> <span data-ttu-id="f6170-104">公共访问是允许的最高访问级别。</span><span class="sxs-lookup"><span data-stu-id="f6170-104">Public access is the most permissive access level.</span></span> <span data-ttu-id="f6170-105">对访问公共成员没有限制，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f6170-105">There are no restrictions on accessing public members, as in this example:</span></span>

```csharp
class SampleClass
{
    public int x; // No access restrictions.
}
```

<span data-ttu-id="f6170-106">有关详细信息，请参阅[访问修饰符](../../programming-guide/classes-and-structs/access-modifiers.md)和[可访问性级别](accessibility-levels.md)。</span><span class="sxs-lookup"><span data-stu-id="f6170-106">See [Access Modifiers](../../programming-guide/classes-and-structs/access-modifiers.md) and [Accessibility Levels](accessibility-levels.md) for more information.</span></span>

## <a name="example"></a><span data-ttu-id="f6170-107">示例</span><span class="sxs-lookup"><span data-stu-id="f6170-107">Example</span></span>

<span data-ttu-id="f6170-108">在下面的示例中，声明了两个类：`PointTest` 和 `MainClass`。</span><span class="sxs-lookup"><span data-stu-id="f6170-108">In the following example, two classes are declared, `PointTest` and `MainClass`.</span></span> <span data-ttu-id="f6170-109">直接从 `MainClass` 访问 `PointTest` 的公共成员 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="f6170-109">The public members `x` and `y` of `PointTest` are accessed directly from `MainClass`.</span></span>

[!code-csharp[csrefKeywordsModifiers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#13)]

<span data-ttu-id="f6170-110">如果将 `public` 访问级别更改为 [private](private.md) 或 [protected](protected.md)，则会收到错误消息：</span><span class="sxs-lookup"><span data-stu-id="f6170-110">If you change the `public` access level to [private](private.md) or [protected](protected.md), you will get the error message:</span></span>

<span data-ttu-id="f6170-111">“PointTest.y”不可访问，因为它受保护级别限制。</span><span class="sxs-lookup"><span data-stu-id="f6170-111">'PointTest.y' is inaccessible due to its protection level.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f6170-112">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="f6170-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f6170-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="f6170-113">See also</span></span>

- [<span data-ttu-id="f6170-114">C# 参考</span><span class="sxs-lookup"><span data-stu-id="f6170-114">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6170-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="f6170-115">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f6170-116">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="f6170-116">Access Modifiers</span></span>](../../programming-guide/classes-and-structs/access-modifiers.md)
- [<span data-ttu-id="f6170-117">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="f6170-117">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f6170-118">访问修饰符</span><span class="sxs-lookup"><span data-stu-id="f6170-118">Access Modifiers</span></span>](access-modifiers.md)
- [<span data-ttu-id="f6170-119">可访问性级别</span><span class="sxs-lookup"><span data-stu-id="f6170-119">Accessibility Levels</span></span>](accessibility-levels.md)
- [<span data-ttu-id="f6170-120">修饰符</span><span class="sxs-lookup"><span data-stu-id="f6170-120">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="f6170-121">private</span><span class="sxs-lookup"><span data-stu-id="f6170-121">private</span></span>](private.md)
- [<span data-ttu-id="f6170-122">protected</span><span class="sxs-lookup"><span data-stu-id="f6170-122">protected</span></span>](protected.md)
- [<span data-ttu-id="f6170-123">internal</span><span class="sxs-lookup"><span data-stu-id="f6170-123">internal</span></span>](internal.md)