---
title: Attributes1
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51aa91b1acbae9f1a15ac12441090dd4c1c2dcb1
ms.sourcegitcommit: 4b6490b2529707627ad77c3a43fbe64120397175
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2018
ms.locfileid: "44259479"
---
# <a name="attributes"></a><span data-ttu-id="0c70b-102">特性</span><span class="sxs-lookup"><span data-stu-id="0c70b-102">Attributes</span></span>
<span data-ttu-id="0c70b-103"><xref:System.Attribute?displayProperty=nameWithType> 用于定义自定义特性的基类。</span><span class="sxs-lookup"><span data-stu-id="0c70b-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="0c70b-104">属性是可以添加到程序集、 类型、 成员和参数等的编程元素的批注。</span><span class="sxs-lookup"><span data-stu-id="0c70b-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="0c70b-105">它们存储在程序集的元数据，可在运行时使用反射 Api 访问。</span><span class="sxs-lookup"><span data-stu-id="0c70b-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="0c70b-106">例如，该框架定义<xref:System.ObsoleteAttribute>，这可以应用于类型或成员，以指示类型或成员已被弃用。</span><span class="sxs-lookup"><span data-stu-id="0c70b-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="0c70b-107">属性可以具有一个或多个执行其他数据相关的属性的属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="0c70b-108">例如，`ObsoleteAttribute`可以携带有关中的发布的其他信息的类型或成员已弃用的和新的 Api 替换为已过时 API 的说明。</span><span class="sxs-lookup"><span data-stu-id="0c70b-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="0c70b-109">应用该属性时，必须指定属性的某些属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="0c70b-110">这些被称为所需的属性或所需的参数，因为它们表示作为位置构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="0c70b-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="0c70b-111">例如，<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>属性的<xref:System.Diagnostics.ConditionalAttribute>是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="0c70b-112">一定不需要应用了该属性指定的属性被称为可选属性 （或可选参数）。</span><span class="sxs-lookup"><span data-stu-id="0c70b-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="0c70b-113">它们由可设置的属性表示。</span><span class="sxs-lookup"><span data-stu-id="0c70b-113">They are represented by settable properties.</span></span> <span data-ttu-id="0c70b-114">编译器提供特殊语法来设置这些属性时应用的特性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="0c70b-115">例如，<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>属性表示的可选参数。</span><span class="sxs-lookup"><span data-stu-id="0c70b-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="0c70b-116">**✓ DO** 命名自定义特性类带有后缀"属性"。</span><span class="sxs-lookup"><span data-stu-id="0c70b-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="0c70b-117">**✓ DO** 应用<xref:System.AttributeUsageAttribute>到自定义属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="0c70b-118">**✓ DO** 为可选自变量提供可设置属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="0c70b-119">**✓ DO** 提供所需的参数只获取属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="0c70b-120">**✓ DO** 提供构造函数参数初始化对应于所需的参数的属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="0c70b-121">每个参数应为相应的属性 （尽管具有不同大小写） 具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="0c70b-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="0c70b-122">**X AVOID** 提供构造函数参数初始化对应于可选参数的属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="0c70b-123">换而言之，不具有可使用构造函数和 setter 设置的属性。</span><span class="sxs-lookup"><span data-stu-id="0c70b-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="0c70b-124">此原则使非常明确，哪些参数是可选的它是必需的并可避免让两种方法执行同一操作。</span><span class="sxs-lookup"><span data-stu-id="0c70b-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="0c70b-125">**X AVOID** 重载自定义特性构造函数。</span><span class="sxs-lookup"><span data-stu-id="0c70b-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="0c70b-126">拥有一个构造函数清楚地传达给用户哪些参数是必需参数和可选。</span><span class="sxs-lookup"><span data-stu-id="0c70b-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="0c70b-127">**✓ DO** 尽可能密封自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="0c70b-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="0c70b-128">这使属性查找速度更快。</span><span class="sxs-lookup"><span data-stu-id="0c70b-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="0c70b-129">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="0c70b-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0c70b-130">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="0c70b-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c70b-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="0c70b-131">See also</span></span>

- [<span data-ttu-id="0c70b-132">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="0c70b-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
- [<span data-ttu-id="0c70b-133">使用准则</span><span class="sxs-lookup"><span data-stu-id="0c70b-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)
