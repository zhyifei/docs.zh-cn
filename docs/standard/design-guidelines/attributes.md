---
title: 特性
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: KrzysztofCwalina
ms.openlocfilehash: 6d4cc6615b7f7346e9c8fc2a7264025f318c8a3d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54698877"
---
# <a name="attributes"></a><span data-ttu-id="974b2-102">特性</span><span class="sxs-lookup"><span data-stu-id="974b2-102">Attributes</span></span>
<span data-ttu-id="974b2-103"><xref:System.Attribute?displayProperty=nameWithType> 是用于定义自定义特性的基类。</span><span class="sxs-lookup"><span data-stu-id="974b2-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="974b2-104">特性是可以添加到编程元素（例如程序集、类型、成员和参数）的注释。</span><span class="sxs-lookup"><span data-stu-id="974b2-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="974b2-105">它们存储在程序集的元数据中，可以在运行时使用反射 API 时访问。</span><span class="sxs-lookup"><span data-stu-id="974b2-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="974b2-106">例如，框架可以定义 <xref:System.ObsoleteAttribute>，它可以应用于某个类型或成员，指示该类型或成员已被弃用。</span><span class="sxs-lookup"><span data-stu-id="974b2-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="974b2-107">特性可以具有一个或多个属性，这些属性包含与该特性相关的其他数据。</span><span class="sxs-lookup"><span data-stu-id="974b2-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="974b2-108">例如，`ObsoleteAttribute` 可以包含有关已过时的类型或成员的其他信息，以及替换过时 API 的新 API 的描述。</span><span class="sxs-lookup"><span data-stu-id="974b2-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="974b2-109">应用特性时，必须指定该特性的某些属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="974b2-110">这些被称为必需属性或必需参数，因为它们表示为位置型构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="974b2-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="974b2-111">例如，<xref:System.Diagnostics.ConditionalAttribute> 的<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> 属性是必需属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="974b2-112">应用该特性时不一定必须指定的属性称为可选属性（或可选参数）。</span><span class="sxs-lookup"><span data-stu-id="974b2-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="974b2-113">它们由可设置的属性表示。</span><span class="sxs-lookup"><span data-stu-id="974b2-113">They are represented by settable properties.</span></span> <span data-ttu-id="974b2-114">编译器提供特殊语法，以在应用特性时设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="974b2-115">例如， <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> 属性表示了一个可选参数。</span><span class="sxs-lookup"><span data-stu-id="974b2-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="974b2-116">**✓ 务必**使用后缀“Attribute”命名自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="974b2-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="974b2-117">**✓ 务必**为自定义特性应用 <xref:System.AttributeUsageAttribute>。</span><span class="sxs-lookup"><span data-stu-id="974b2-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="974b2-118">**✓ 务必**为可选实参提供可设置的属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="974b2-119">**✓ 务必**为必需参数提供 get-only 属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="974b2-120">**✓ 务必**提供构造函数参数来初始化与所需参数对应的属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="974b2-121">每个参数应与相应的属具有相同的名称（尽管具有不同的大小写）。</span><span class="sxs-lookup"><span data-stu-id="974b2-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="974b2-122">**X 避免**提供构造函数参数来初始化与可选参数对应的属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="974b2-123">换句话说，不要使用可同时用构造函数和 setter 设置的属性。</span><span class="sxs-lookup"><span data-stu-id="974b2-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="974b2-124">此原则使哪些参数是可选的、哪些参数是必需的变得非常明确，并可避免使用两种方法执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="974b2-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="974b2-125">**X 避免**重载自定义特性构造函数。</span><span class="sxs-lookup"><span data-stu-id="974b2-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="974b2-126">只使用一个构造函数来清晰地向用户传达哪些参数是必需的，哪些是可选的。</span><span class="sxs-lookup"><span data-stu-id="974b2-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="974b2-127">**✓ 务必**尽可能密封自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="974b2-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="974b2-128">这可使查找属性的速度更快。</span><span class="sxs-lookup"><span data-stu-id="974b2-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="974b2-129">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="974b2-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="974b2-130">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="974b2-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="974b2-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="974b2-131">See also</span></span>

- [<span data-ttu-id="974b2-132">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="974b2-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="974b2-133">使用准则</span><span class="sxs-lookup"><span data-stu-id="974b2-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
