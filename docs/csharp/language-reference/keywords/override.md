---
title: override 修饰符 - C# 参考
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- override
- override_CSharpKeyword
helpviewer_keywords:
- override keyword [C#]
ms.assetid: dd1907a8-acf8-46d3-80b9-c2ca4febada8
ms.openlocfilehash: 6a8e79da3897e867fa3becab5fcfc70afe72e614
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53244435"
---
# <a name="override-c-reference"></a><span data-ttu-id="3c4b4-102">override（C# 参考）</span><span class="sxs-lookup"><span data-stu-id="3c4b4-102">override (C# Reference)</span></span>

<span data-ttu-id="3c4b4-103">扩展或修改继承的方法、属性、索引器或事件的抽象或虚拟实现需要 `override` 修饰符。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-103">The `override` modifier is required to extend or modify the abstract or virtual implementation of an inherited method, property, indexer, or event.</span></span>

## <a name="example"></a><span data-ttu-id="3c4b4-104">示例</span><span class="sxs-lookup"><span data-stu-id="3c4b4-104">Example</span></span>

<span data-ttu-id="3c4b4-105">在此示例中，`Square` 类必须提供 `Area` 的重写实现，因为 `Area` 继承自抽象 `ShapesClass`：</span><span class="sxs-lookup"><span data-stu-id="3c4b4-105">In this example, the `Square` class must provide an overridden implementation of `Area` because `Area` is inherited from the abstract `ShapesClass`:</span></span>

[!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]

<span data-ttu-id="3c4b4-106">`override` 方法提供从基类继承的成员的新实现。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-106">An `override` method provides a new implementation of a member that is inherited from a base class.</span></span> <span data-ttu-id="3c4b4-107">通过 `override` 声明重写的方法称为重写基方法。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-107">The method that is overridden by an `override` declaration is known as the overridden base method.</span></span> <span data-ttu-id="3c4b4-108">重写基方法必须具有与 `override` 方法相同的签名。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-108">The overridden base method must have the same signature as the `override` method.</span></span> <span data-ttu-id="3c4b4-109">有关继承的信息，请参阅[继承](../../programming-guide/classes-and-structs/inheritance.md)。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-109">For information about inheritance, see [Inheritance](../../programming-guide/classes-and-structs/inheritance.md).</span></span>

<span data-ttu-id="3c4b4-110">不能重新非虚方法或静态方法。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-110">You cannot override a non-virtual or static method.</span></span> <span data-ttu-id="3c4b4-111">重写基方法必须是 `virtual`、`abstract` 或 `override`。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-111">The overridden base method must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="3c4b4-112">`override` 声明不能更改 `virtual` 方法的可访问性。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-112">An `override` declaration cannot change the accessibility of the `virtual` method.</span></span> <span data-ttu-id="3c4b4-113">`override` 方法和 `virtual` 方法必须具有相同[级别访问修饰符](access-modifiers.md)。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-113">Both the `override` method and the `virtual` method must have the same [access level modifier](access-modifiers.md).</span></span>

<span data-ttu-id="3c4b4-114">不能使用 `new`、`static` 或 `virtual` 修饰符修改 `override` 方法。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-114">You cannot use the `new`, `static`, or `virtual` modifiers to modify an `override` method.</span></span>

<span data-ttu-id="3c4b4-115">重写属性声明必须指定与继承的属性完全相同的访问修饰符、类型和名称，并且重写的属性必须是 `virtual`、`abstract` 或 `override`。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-115">An overriding property declaration must specify exactly the same access modifier, type, and name as the inherited property, and the overridden property must be `virtual`, `abstract`, or `override`.</span></span>

<span data-ttu-id="3c4b4-116">有关如何使用 `override` 关键字的详细信息，请参阅[使用 Override 和 New 关键字进行版本控制](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md)和[了解何时使用 Override 和 New 关键字](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md)。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-116">For more information about how to use the `override` keyword, see [Versioning with the Override and New Keywords](../../programming-guide/classes-and-structs/versioning-with-the-override-and-new-keywords.md) and [Knowing when to use Override and New Keywords](../../programming-guide/classes-and-structs/knowing-when-to-use-override-and-new-keywords.md).</span></span>

## <a name="example"></a><span data-ttu-id="3c4b4-117">示例</span><span class="sxs-lookup"><span data-stu-id="3c4b4-117">Example</span></span>

<span data-ttu-id="3c4b4-118">此示例定义一个名为 `Employee` 的基类和一个名为 `SalesEmployee` 的派生类。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-118">This example defines a base class named `Employee`, and a derived class named `SalesEmployee`.</span></span> <span data-ttu-id="3c4b4-119">`SalesEmployee` 类包含一个额外字段 `salesbonus`，并且重写方法 `CalculatePay` 以将它考虑在内。</span><span class="sxs-lookup"><span data-stu-id="3c4b4-119">The `SalesEmployee` class includes an extra field, `salesbonus`, and overrides the method `CalculatePay` in order to take it into account.</span></span>

[!code-csharp[csrefKeywordsModifiers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#9)]

## <a name="c-language-specification"></a><span data-ttu-id="3c4b4-120">C# 语言规范</span><span class="sxs-lookup"><span data-stu-id="3c4b4-120">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="3c4b4-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="3c4b4-121">See also</span></span>

- [<span data-ttu-id="3c4b4-122">C# 参考</span><span class="sxs-lookup"><span data-stu-id="3c4b4-122">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="3c4b4-123">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="3c4b4-123">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="3c4b4-124">继承</span><span class="sxs-lookup"><span data-stu-id="3c4b4-124">Inheritance</span></span>](../../programming-guide/classes-and-structs/inheritance.md)
- [<span data-ttu-id="3c4b4-125">C# 关键字</span><span class="sxs-lookup"><span data-stu-id="3c4b4-125">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="3c4b4-126">修饰符</span><span class="sxs-lookup"><span data-stu-id="3c4b4-126">Modifiers</span></span>](modifiers.md)
- [<span data-ttu-id="3c4b4-127">abstract</span><span class="sxs-lookup"><span data-stu-id="3c4b4-127">abstract</span></span>](abstract.md)
- [<span data-ttu-id="3c4b4-128">virtual</span><span class="sxs-lookup"><span data-stu-id="3c4b4-128">virtual</span></span>](virtual.md)
- [<span data-ttu-id="3c4b4-129">new</span><span class="sxs-lookup"><span data-stu-id="3c4b4-129">new</span></span>](new.md)
- [<span data-ttu-id="3c4b4-130">多态性</span><span class="sxs-lookup"><span data-stu-id="3c4b4-130">Polymorphism</span></span>](../../programming-guide/classes-and-structs/polymorphism.md)
