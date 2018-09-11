---
title: 接口（C# 参考）
ms.date: 07/20/2015
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 4adc7ba106e0044ba6aff94ea3180d9c8e3ded7b
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44266834"
---
# <a name="interface-c-reference"></a><span data-ttu-id="1e3ba-102">接口（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="1e3ba-102">interface (C# Reference)</span></span>

<span data-ttu-id="1e3ba-103">接口只包含[方法](../../programming-guide/classes-and-structs/methods.md)、[属性](../../programming-guide/classes-and-structs/properties.md)、[事件](../../programming-guide/events/index.md)或[索引器](../../programming-guide/indexers/index.md)的签名。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-103">An interface contains only the signatures of [methods](../../programming-guide/classes-and-structs/methods.md), [properties](../../programming-guide/classes-and-structs/properties.md), [events](../../programming-guide/events/index.md) or [indexers](../../programming-guide/indexers/index.md).</span></span> <span data-ttu-id="1e3ba-104">实现接口的类或结构必须实现接口定义中指定的接口成员。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-104">A class or struct that implements the interface must implement the members of the interface that are specified in the interface definition.</span></span> <span data-ttu-id="1e3ba-105">在以下示例中，类 `ImplementationClass` 必须实现一个不含参数但返回 `void` 的名为 `SampleMethod` 的方法。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-105">In the following example, class `ImplementationClass` must implement a method named `SampleMethod` that has no parameters and returns `void`.</span></span>

<span data-ttu-id="1e3ba-106">有关详细信息和示例，请参阅[接口](../../programming-guide/interfaces/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-106">For more information and examples, see [Interfaces](../../programming-guide/interfaces/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e3ba-107">示例</span><span class="sxs-lookup"><span data-stu-id="1e3ba-107">Example</span></span>

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

<span data-ttu-id="1e3ba-108">接口可以是命名空间或类的成员，并且可以包含下列成员的签名：</span><span class="sxs-lookup"><span data-stu-id="1e3ba-108">An interface can be a member of a namespace or a class and can contain signatures of the following members:</span></span>

- [<span data-ttu-id="1e3ba-109">方法</span><span class="sxs-lookup"><span data-stu-id="1e3ba-109">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)

- [<span data-ttu-id="1e3ba-110">属性</span><span class="sxs-lookup"><span data-stu-id="1e3ba-110">Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)

- [<span data-ttu-id="1e3ba-111">索引器</span><span class="sxs-lookup"><span data-stu-id="1e3ba-111">Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)

- [<span data-ttu-id="1e3ba-112">事件</span><span class="sxs-lookup"><span data-stu-id="1e3ba-112">Events</span></span>](event.md)

<span data-ttu-id="1e3ba-113">一个接口可从一个或多个基接口继承。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-113">An interface can inherit from one or more base interfaces.</span></span>

<span data-ttu-id="1e3ba-114">基类型列表包含基类和接口时，基类必须是列表中的第 1 项。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-114">When a base type list contains a base class and interfaces, the base class must come first in the list.</span></span>

<span data-ttu-id="1e3ba-115">实现接口的类可以显式实现该接口的成员。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-115">A class that implements an interface can explicitly implement members of that interface.</span></span> <span data-ttu-id="1e3ba-116">显式实现的成员不能通过类实例访问，而只能通过接口实例访问。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-116">An explicitly implemented member cannot be accessed through a class instance, but only through an instance of the interface.</span></span>

<span data-ttu-id="1e3ba-117">有关显式接口实现的更多详细信息和代码示例，请参阅[显式接口实现](../../programming-guide/interfaces/explicit-interface-implementation.md)。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-117">For more details and code examples on explicit interface implementation, see [Explicit Interface Implementation](../../programming-guide/interfaces/explicit-interface-implementation.md).</span></span>

## <a name="example"></a><span data-ttu-id="1e3ba-118">示例</span><span class="sxs-lookup"><span data-stu-id="1e3ba-118">Example</span></span>

<span data-ttu-id="1e3ba-119">下例演示了接口实现。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-119">The following example demonstrates interface implementation.</span></span> <span data-ttu-id="1e3ba-120">在此示例中，接口包含属性声明，类包含实现。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-120">In this example, the interface contains the property declaration and the class contains the implementation.</span></span> <span data-ttu-id="1e3ba-121">实现 `IPoint` 的类的任何实例都具有整数属性 `x` 和 `y`。</span><span class="sxs-lookup"><span data-stu-id="1e3ba-121">Any instance of a class that implements `IPoint` has integer properties `x` and `y`.</span></span>

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a><span data-ttu-id="1e3ba-122">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="1e3ba-122">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="1e3ba-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="1e3ba-123">See also</span></span>

- [<span data-ttu-id="1e3ba-124">C# 参考</span><span class="sxs-lookup"><span data-stu-id="1e3ba-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="1e3ba-125">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="1e3ba-125">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="1e3ba-126">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="1e3ba-126">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="1e3ba-127">引用类型</span><span class="sxs-lookup"><span data-stu-id="1e3ba-127">Reference Types</span></span>](reference-types.md)  
- [<span data-ttu-id="1e3ba-128">接口</span><span class="sxs-lookup"><span data-stu-id="1e3ba-128">Interfaces</span></span>](../../programming-guide/interfaces/index.md)  
- [<span data-ttu-id="1e3ba-129">使用属性</span><span class="sxs-lookup"><span data-stu-id="1e3ba-129">Using Properties</span></span>](../../programming-guide/classes-and-structs/using-properties.md)  
- [<span data-ttu-id="1e3ba-130">使用索引器</span><span class="sxs-lookup"><span data-stu-id="1e3ba-130">Using Indexers</span></span>](../../programming-guide/indexers/using-indexers.md)  
- [<span data-ttu-id="1e3ba-131">class</span><span class="sxs-lookup"><span data-stu-id="1e3ba-131">class</span></span>](class.md)  
- [<span data-ttu-id="1e3ba-132">struct</span><span class="sxs-lookup"><span data-stu-id="1e3ba-132">struct</span></span>](struct.md)  
- [<span data-ttu-id="1e3ba-133">接口</span><span class="sxs-lookup"><span data-stu-id="1e3ba-133">Interfaces</span></span>](../../programming-guide/interfaces/index.md)
