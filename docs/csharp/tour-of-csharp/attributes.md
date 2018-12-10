---
title: C# 特性 - C#语言介绍
description: 了解在 C# 中使用特性的声明性编程
ms.date: 08/10/2016
ms.assetid: 753bcfe2-7ddd-4487-9513-ba70937fc8e9
ms.openlocfilehash: a8ee40e5d4956667dd54cf25cc7993d041cba6e7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53151078"
---
# <a name="attributes"></a><span data-ttu-id="94cfe-103">特性</span><span class="sxs-lookup"><span data-stu-id="94cfe-103">Attributes</span></span>

<span data-ttu-id="94cfe-104">C# 程序中的类型、成员和其他实体支持使用修饰符来控制其行为的某些方面。</span><span class="sxs-lookup"><span data-stu-id="94cfe-104">Types, members, and other entities in a C# program support modifiers that control certain aspects of their behavior.</span></span> <span data-ttu-id="94cfe-105">例如，方法的可访问性是由 `public`、`protected`、`internal` 和 `private` 修饰符控制。</span><span class="sxs-lookup"><span data-stu-id="94cfe-105">For example, the accessibility of a method is controlled using the `public`, `protected`, `internal`, and `private` modifiers.</span></span> <span data-ttu-id="94cfe-106">C# 整合了这种能力，以便可以将用户定义类型的声明性信息附加到程序实体，并在运行时检索此类信息。</span><span class="sxs-lookup"><span data-stu-id="94cfe-106">C# generalizes this capability such that user-defined types of declarative information can be attached to program entities and retrieved at run-time.</span></span> <span data-ttu-id="94cfe-107">程序通过定义和使用***特性***来指定此类额外的声明性信息。</span><span class="sxs-lookup"><span data-stu-id="94cfe-107">Programs specify this additional declarative information by defining and using ***attributes***.</span></span>

<span data-ttu-id="94cfe-108">以下示例声明了 `HelpAttribute` 特性，可将其附加到程序实体，以提供指向关联文档的链接。</span><span class="sxs-lookup"><span data-stu-id="94cfe-108">The following example declares a `HelpAttribute` attribute that can be placed on program entities to provide links to their associated documentation.</span></span>

[!code-csharp[AttributeDefined](../../../samples/snippets/csharp/tour/attributes/Program.cs#L3-L20)]

<span data-ttu-id="94cfe-109">所有特性类都派生自标准库提供的 <xref:System.Attribute> 基类。</span><span class="sxs-lookup"><span data-stu-id="94cfe-109">All attribute classes derive from the <xref:System.Attribute> base class provided by the standard library.</span></span> <span data-ttu-id="94cfe-110">特性的应用方式为，在相关声明前的方括号内指定特性的名称以及任意自变量。</span><span class="sxs-lookup"><span data-stu-id="94cfe-110">Attributes can be applied by giving their name, along with any arguments, inside square brackets just before the associated declaration.</span></span> <span data-ttu-id="94cfe-111">如果特性的名称以 `Attribute` 结尾，那么可以在引用特性时省略这部分名称。</span><span class="sxs-lookup"><span data-stu-id="94cfe-111">If an attribute’s name ends in `Attribute`, that part of the name can be omitted when the attribute is referenced.</span></span> <span data-ttu-id="94cfe-112">例如，可按如下方法使用 `HelpAttribute`。</span><span class="sxs-lookup"><span data-stu-id="94cfe-112">For example, the `HelpAttribute` can be used as follows.</span></span>

[!code-csharp[AttributeApplied](../../../samples/snippets/csharp/tour/attributes/Program.cs#L22-L28)]

<span data-ttu-id="94cfe-113">此示例将 `HelpAttribute` 附加到 `Widget` 类。</span><span class="sxs-lookup"><span data-stu-id="94cfe-113">This example attaches a `HelpAttribute` to the `Widget` class.</span></span> <span data-ttu-id="94cfe-114">还向此类中的 `Display` 方法附加了另一个 `HelpAttribute`。</span><span class="sxs-lookup"><span data-stu-id="94cfe-114">It adds another `HelpAttribute` to the `Display` method in the class.</span></span> <span data-ttu-id="94cfe-115">特性类的公共构造函数控制了将特性附加到程序实体时必须提供的信息。</span><span class="sxs-lookup"><span data-stu-id="94cfe-115">The public constructors of an attribute class control the information that must be provided when the attribute is attached to a program entity.</span></span> <span data-ttu-id="94cfe-116">可以通过引用特性类的公共读写属性（如上面示例对 `Topic` 属性的引用），提供其他信息。</span><span class="sxs-lookup"><span data-stu-id="94cfe-116">Additional information can be provided by referencing public read-write properties of the attribute class (such as the reference to the `Topic` property previously).</span></span>

<span data-ttu-id="94cfe-117">可以在运行时使用反射来读取和操纵特性定义的元数据。</span><span class="sxs-lookup"><span data-stu-id="94cfe-117">The metadata defined by attributes can be read and manipulated at runtime using reflection.</span></span> <span data-ttu-id="94cfe-118">如果使用这种方法请求获取特定特性，便会调用特性类的构造函数（在程序源中提供信息），并返回生成的特性实例。</span><span class="sxs-lookup"><span data-stu-id="94cfe-118">When a particular attribute is requested using this technique, the constructor for the attribute class is invoked with the information provided in the program source, and the resulting attribute instance is returned.</span></span> <span data-ttu-id="94cfe-119">如果是通过属性提供其他信息，那么在特性实例返回前，这些属性会设置为给定值。</span><span class="sxs-lookup"><span data-stu-id="94cfe-119">If additional information was provided through properties, those properties are set to the given values before the attribute instance is returned.</span></span>

<span data-ttu-id="94cfe-120">下面的代码示例展示了如何获取与 `Widget` 类及其 `Display` 方法相关联的 `HelpAttribute` 实例。</span><span class="sxs-lookup"><span data-stu-id="94cfe-120">The following code sample demonstrates how to get the `HelpAttribute` instances associated to the `Widget` class and its `Display` method.</span></span>

[!code-csharp[AttributeRead](../../../samples/snippets/csharp/tour/attributes/Program.cs#ReadAttributes)]

>[!div class="step-by-step"]
>[<span data-ttu-id="94cfe-121">上一篇</span><span class="sxs-lookup"><span data-stu-id="94cfe-121">Previous</span></span>](delegates.md)