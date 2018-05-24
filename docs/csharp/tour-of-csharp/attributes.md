---
title: C# 特性 - C#语言介绍
description: 了解在 C# 中使用特性的声明性编程
ms.date: 08/10/2016
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: 671023f268ae78d63db8868ef6046b8f13880659
ms.sourcegitcommit: 895c7602386a6dfe7ca4facce3d965b27e5c6e87
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2018
---
# <a name="attributes"></a><span data-ttu-id="1089e-103">特性</span><span class="sxs-lookup"><span data-stu-id="1089e-103">Attributes</span></span>

<span data-ttu-id="1089e-104">C# 程序中的类型、成员和其他实体支持使用修饰符来控制其行为的某些方面。</span><span class="sxs-lookup"><span data-stu-id="1089e-104">Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior.</span></span> <span data-ttu-id="1089e-105">例如，方法的可访问性是由 `public`、`protected`、`internal` 和 `private` 修饰符控制。</span><span class="sxs-lookup"><span data-stu-id="1089e-105">For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers.</span></span> <span data-ttu-id="1089e-106">C# 整合了这种能力，以便可以将用户定义类型的声明性信息附加到程序实体，并在运行时检索此类信息。</span><span class="sxs-lookup"><span data-stu-id="1089e-106">C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time.</span></span> <span data-ttu-id="1089e-107">程序通过定义和使用***特性***来指定此类额外的声明性信息。</span><span class="sxs-lookup"><span data-stu-id="1089e-107">Programs specify this additional declarative information by defining and using ***attributes***.</span></span>

<span data-ttu-id="1089e-108">以下示例声明了 `HelpAttribute` 特性，可将其附加到程序实体，以提供指向关联文档的链接。</span><span class="sxs-lookup"><span data-stu-id="1089e-108">The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.</span></span>

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

<span data-ttu-id="1089e-109">所有特性类都派生自标准库提供的 <xref:System.Attribute> 基类。</span><span class="sxs-lookup"><span data-stu-id="1089e-109">All attribute classes derive from the <xref:System.Attribute> base class provided by the standard library.</span></span> <span data-ttu-id="1089e-110">特性的应用方式为，在相关声明前的方括号内指定特性的名称以及任意自变量。</span><span class="sxs-lookup"><span data-stu-id="1089e-110">Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration.</span></span> <span data-ttu-id="1089e-111">如果特性的名称以 `Attribute` 结尾，那么可以在引用特性时省略这部分名称。</span><span class="sxs-lookup"><span data-stu-id="1089e-111">If an attribute’s name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced.</span></span> <span data-ttu-id="1089e-112">例如，可按如下方法使用 `HelpAttribute`。</span><span class="sxs-lookup"><span data-stu-id="1089e-112">For example, the `HelpAttribute` can be used as follows.</span></span>

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

<span data-ttu-id="1089e-113">此示例将 `HelpAttribute` 附加到 `Widget` 类。</span><span class="sxs-lookup"><span data-stu-id="1089e-113">This example attaches a `HelpAttribute` to the `Widget` class.</span></span> <span data-ttu-id="1089e-114">还向此类中的 `Display` 方法附加了另一个 `HelpAttribute`。</span><span class="sxs-lookup"><span data-stu-id="1089e-114">It adds another `HelpAttribute` to the `Display` method in the class.</span></span> <span data-ttu-id="1089e-115">特性类的公共构造函数控制了将特性附加到程序实体时必须提供的信息。</span><span class="sxs-lookup"><span data-stu-id="1089e-115">The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity.</span></span> <span data-ttu-id="1089e-116">可以通过引用特性类的公共读写属性（如上面示例对 `Topic` 属性的引用），提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="1089e-116">Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).</span></span>

<span data-ttu-id="1089e-117">通过反射请求获得特定特性时，将调用特性类的构造函数（由程序源提供信息），并返回生成的特性实例。</span><span class="sxs-lookup"><span data-stu-id="1089e-117">When a particular attribute is requested through reflection, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned.</span></span> <span data-ttu-id="1089e-118">如果是通过属性提供其他信息，那么在特性实例返回前，这些属性会设置为给定值。</span><span class="sxs-lookup"><span data-stu-id="1089e-118">If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.</span></span>

>[!div class="step-by-step"]
[<span data-ttu-id="1089e-119">上一页</span><span class="sxs-lookup"><span data-stu-id="1089e-119">Previous</span></span>](delegates.md)
