---
title: 隐式类型数组 - C# 编程指南
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#], implicitly-typed
- implicitly-typed arrays [C#]
- C# language, implicitly typed arrays
ms.assetid: e05be95c-6732-403d-ae42-b35f057cbbea
ms.openlocfilehash: 943760af30422cd333fdff65cdf678108c9d9564
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705712"
---
# <a name="implicitly-typed-arrays-c-programming-guide"></a><span data-ttu-id="d7542-102">隐式类型的数组（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="d7542-102">Implicitly Typed Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="d7542-103">可以创建隐式类型化的数组，其中数组实例的类型通过数组初始值设定项中指定的元素来推断。</span><span class="sxs-lookup"><span data-stu-id="d7542-103">You can create an implicitly-typed array in which the type of the array instance is inferred from the elements specified in the array initializer.</span></span> <span data-ttu-id="d7542-104">针对隐式类型化变量的任何规则也适用于隐式类型化数组。</span><span class="sxs-lookup"><span data-stu-id="d7542-104">The rules for any implicitly-typed variable also apply to implicitly-typed arrays.</span></span> <span data-ttu-id="d7542-105">有关详细信息，请参阅[隐式类型局部变量](../classes-and-structs/implicitly-typed-local-variables.md)。</span><span class="sxs-lookup"><span data-stu-id="d7542-105">For more information, see [Implicitly Typed Local Variables](../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

<span data-ttu-id="d7542-106">隐式类型化数组通常用于查询表达式、匿名类型、对象和集合初始值设定项。</span><span class="sxs-lookup"><span data-stu-id="d7542-106">Implicitly-typed arrays are usually used in query expressions together with anonymous types and object and collection initializers.</span></span>

<span data-ttu-id="d7542-107">下列示例演示如何创建隐式类型化数组：</span><span class="sxs-lookup"><span data-stu-id="d7542-107">The following examples show how to create an implicitly-typed array:</span></span>

[!code-csharp[csProgGuideLINQ#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#37)]

<span data-ttu-id="d7542-108">在上个示例中，请注意对于隐式类型化数组，初始化语句的左侧没有使用方括号。</span><span class="sxs-lookup"><span data-stu-id="d7542-108">In the previous example, notice that with implicitly-typed arrays, no square brackets are used on the left side of the initialization statement.</span></span> <span data-ttu-id="d7542-109">另请注意，和一维数组一样，通过使用 `new []` 来初始化交错数组。</span><span class="sxs-lookup"><span data-stu-id="d7542-109">Note also that jagged arrays are initialized by using `new []` just like single-dimension arrays.</span></span>

## <a name="implicitly-typed-arrays-in-object-initializers"></a><span data-ttu-id="d7542-110">对象初始值设定项中隐式类型化数组</span><span class="sxs-lookup"><span data-stu-id="d7542-110">Implicitly-typed Arrays in Object Initializers</span></span>

<span data-ttu-id="d7542-111">创建包含数组的匿名类型时，必须在类型的对象初始值设定项中隐式类型化数组。</span><span class="sxs-lookup"><span data-stu-id="d7542-111">When you create an anonymous type that contains an array, the array must be implicitly typed in the type's object initializer.</span></span> <span data-ttu-id="d7542-112">在下列示例中，`contacts` 是匿名类型的隐式类型化数组，每个类型都包含名为 `PhoneNumbers` 的数组。</span><span class="sxs-lookup"><span data-stu-id="d7542-112">In the following example, `contacts` is an implicitly-typed array of anonymous types, each of which contains an array named `PhoneNumbers`.</span></span> <span data-ttu-id="d7542-113">请注意，不可在对象初始值设定项中使用 `var` 关键字。</span><span class="sxs-lookup"><span data-stu-id="d7542-113">Note that the `var` keyword is not used inside the object initializers.</span></span>

[!code-csharp[csProgGuideLINQ#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#38)]

## <a name="see-also"></a><span data-ttu-id="d7542-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7542-114">See also</span></span>

- [<span data-ttu-id="d7542-115">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="d7542-115">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="d7542-116">隐式类型的局部变量</span><span class="sxs-lookup"><span data-stu-id="d7542-116">Implicitly Typed Local Variables</span></span>](../classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="d7542-117">数组</span><span class="sxs-lookup"><span data-stu-id="d7542-117">Arrays</span></span>](./index.md)
- [<span data-ttu-id="d7542-118">匿名类型</span><span class="sxs-lookup"><span data-stu-id="d7542-118">Anonymous Types</span></span>](../classes-and-structs/anonymous-types.md)
- [<span data-ttu-id="d7542-119">对象和集合初始值设定项</span><span class="sxs-lookup"><span data-stu-id="d7542-119">Object and Collection Initializers</span></span>](../classes-and-structs/object-and-collection-initializers.md)
- [<span data-ttu-id="d7542-120">var</span><span class="sxs-lookup"><span data-stu-id="d7542-120">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="d7542-121">C# 中的 LINQ</span><span class="sxs-lookup"><span data-stu-id="d7542-121">LINQ in C#</span></span>](../../linq/index.md)
