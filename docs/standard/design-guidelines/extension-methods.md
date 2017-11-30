---
title: "扩展方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b7edc3420eabe4de20a2fe39f38ae5eee53b593c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="extension-methods"></a><span data-ttu-id="1fdbc-102">扩展方法</span><span class="sxs-lookup"><span data-stu-id="1fdbc-102">Extension Methods</span></span>
<span data-ttu-id="1fdbc-103">扩展方法是允许使用实例方法调用语法来调用静态方法的语言功能。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="1fdbc-104">这些方法必须采用至少一个参数，它表示的方法是在上运行的实例。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>  
  
 <span data-ttu-id="1fdbc-105">定义此类扩展方法的类称为"发起人"类，并必须声明为静态。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="1fdbc-106">若要使用扩展方法，其中一个必须导入定义发起人类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>  
  
 <span data-ttu-id="1fdbc-107">**请避免 x** frivolously 尤其是在你拥有的类型上定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-107">**X AVOID** frivolously defining extension methods, especially on types you don’t own.</span></span>  
  
 <span data-ttu-id="1fdbc-108">如果你拥有的一种类型的源代码，请考虑改为使用常规的实例方法。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="1fdbc-109">如果你拥有，并且你想要添加一个方法，保持谨慎。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="1fdbc-110">扩展方法的自由使用有可能会干扰的没有设计具有这些方法的类型的 Api。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>  
  
 <span data-ttu-id="1fdbc-111">**请考虑 ✓**任何以下方案中使用扩展方法：</span><span class="sxs-lookup"><span data-stu-id="1fdbc-111">**✓ CONSIDER** using extension methods in any of the following scenarios:</span></span>  
  
-   <span data-ttu-id="1fdbc-112">若要提供的帮助器功能相关的每个实现的接口，如果功能可以编写在核心接口方面。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="1fdbc-113">这是因为具体实现否则不能分配到接口。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="1fdbc-114">例如，`LINQ to Objects`运算符作为扩展方法实现所有<xref:System.Collections.Generic.IEnumerable%601>类型。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="1fdbc-115">因此，任何`IEnumerable<>`实现是自动启用 LINQ 的。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>  
  
-   <span data-ttu-id="1fdbc-116">依赖于某个类型，但这种相关性的实例方法将会带来时将会破坏依赖关系管理规则。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="1fdbc-117">例如，依赖项从<xref:System.String>到<xref:System.Uri?displayProperty=nameWithType>可能是不可取，因此`String.ToUri()`返回的实例方法`System.Uri`依赖项管理角度错误设计非常。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="1fdbc-118">静态的扩展方法`Uri.ToUri(this string str)`返回`System.Uri`将多更好的设计。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>  
  
 <span data-ttu-id="1fdbc-119">**请避免 x**上定义的扩展方法<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-119">**X AVOID** defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="1fdbc-120">VB 用户不能调用使用扩展方法语法的对象引用此类方法。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-120">VB users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="1fdbc-121">VB 不支持调用此类方法，因为在 VB 中将引用声明为对象将强制所有方法调用，它是后期绑定 （名为的实际成员确定在运行时），而在 （尽早编译时确定绑定到扩展方法绑定）。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-121">VB does not support calling such methods because, in VB, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>  
  
 <span data-ttu-id="1fdbc-122">请注意，那么准则适用于其他语言相同的绑定行为是存在，或不支持扩展方法。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>  
  
 <span data-ttu-id="1fdbc-123">**X 不**置于扩展的类型相同的命名空间的扩展方法，除非它是为添加到接口的方法或依赖关系管理。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-123">**X DO NOT** put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>  
  
 <span data-ttu-id="1fdbc-124">**请避免 x**定义两个或多个具有相同签名的扩展方法，即使它们驻留在不同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-124">**X AVOID** defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>  
  
 <span data-ttu-id="1fdbc-125">**请考虑 ✓**在扩展的类型相同的命名空间中定义的扩展方法，如果类型是接口，并且扩展方法为了在大多数或所有情况下使用。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-125">**✓ CONSIDER** defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>  
  
 <span data-ttu-id="1fdbc-126">**X 不**定义在与其他功能正常关联的命名空间中实现功能的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-126">**X DO NOT** define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="1fdbc-127">相反，在它们所属的功能与关联的命名空间中定义它们。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>  
  
 <span data-ttu-id="1fdbc-128">**请避免 x**泛型命名的命名空间专用于扩展方法 （例如，"扩展"）。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-128">**X AVOID** generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="1fdbc-129">使用描述性的名称 （例如，"路由"） 相反。</span><span class="sxs-lookup"><span data-stu-id="1fdbc-129">Use a descriptive name (e.g., "Routing") instead.</span></span>  
  
 <span data-ttu-id="1fdbc-130">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="1fdbc-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="1fdbc-131">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="1fdbc-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fdbc-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1fdbc-132">See Also</span></span>  
 [<span data-ttu-id="1fdbc-133">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="1fdbc-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
 [<span data-ttu-id="1fdbc-134">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="1fdbc-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
