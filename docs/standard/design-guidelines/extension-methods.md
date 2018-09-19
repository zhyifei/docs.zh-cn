---
title: 扩展方法
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: f513a91160b3fec289dd06646d0d6f81f8fcf910
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2018
ms.locfileid: "46287460"
---
# <a name="extension-methods"></a><span data-ttu-id="ddac4-102">扩展方法</span><span class="sxs-lookup"><span data-stu-id="ddac4-102">Extension Methods</span></span>
<span data-ttu-id="ddac4-103">扩展方法是一种语言功能，允许使用实例方法调用语法来调用静态方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-103">Extension methods are a language feature that allows static methods to be called using instance method call syntax.</span></span> <span data-ttu-id="ddac4-104">这些方法必须采用至少一个参数，它表示的方法是在上运行的实例。</span><span class="sxs-lookup"><span data-stu-id="ddac4-104">These methods must take at least one parameter, which represents the instance the method is to operate on.</span></span>  
  
 <span data-ttu-id="ddac4-105">定义此类扩展方法的类称为"发起人"类，并且它必须声明为静态。</span><span class="sxs-lookup"><span data-stu-id="ddac4-105">The class that defines such extension methods is referred to as the "sponsor" class, and it must be declared as static.</span></span> <span data-ttu-id="ddac4-106">若要使用的扩展方法，其中一个必须导入定义主办方类的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddac4-106">To use extension methods, one must import the namespace defining the sponsor class.</span></span>  
  
 <span data-ttu-id="ddac4-107">**X AVOID** frivolously 尤其是在你拥有的类型上定义扩展方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-107">**X AVOID** frivolously defining extension methods, especially on types you don’t own.</span></span>  
  
 <span data-ttu-id="ddac4-108">如果您是一种类型的源代码，请考虑改为使用常规的实例方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-108">If you do own source code of a type, consider using regular instance methods instead.</span></span> <span data-ttu-id="ddac4-109">如果你拥有，并且你想要添加一个方法，要非常小心。</span><span class="sxs-lookup"><span data-stu-id="ddac4-109">If you don’t own, and you want to add a method, be very careful.</span></span> <span data-ttu-id="ddac4-110">扩展方法的自由使用有可能会干扰 Api 旨在不具有这些方法的类型。</span><span class="sxs-lookup"><span data-stu-id="ddac4-110">Liberal use of extension methods has the potential of cluttering APIs of types that were not designed to have these methods.</span></span>  
  
 <span data-ttu-id="ddac4-111">**✓ CONSIDER** 任何以下方案中使用扩展方法：</span><span class="sxs-lookup"><span data-stu-id="ddac4-111">**✓ CONSIDER** using extension methods in any of the following scenarios:</span></span>  
  
-   <span data-ttu-id="ddac4-112">若要提供的帮助器功能与每个接口的实现，如果说是功能可以编写方面的核心接口。</span><span class="sxs-lookup"><span data-stu-id="ddac4-112">To provide helper functionality relevant to every implementation of an interface, if said functionality can be written in terms of the core interface.</span></span> <span data-ttu-id="ddac4-113">这是因为具体实现否则不能分配给接口。</span><span class="sxs-lookup"><span data-stu-id="ddac4-113">This is because concrete implementations cannot otherwise be assigned to interfaces.</span></span> <span data-ttu-id="ddac4-114">例如，`LINQ to Objects`运算符作为扩展方法实现所有<xref:System.Collections.Generic.IEnumerable%601>类型。</span><span class="sxs-lookup"><span data-stu-id="ddac4-114">For example, the `LINQ to Objects` operators are implemented as extension methods for all <xref:System.Collections.Generic.IEnumerable%601> types.</span></span> <span data-ttu-id="ddac4-115">因此，任何`IEnumerable<>`实现是自动启用 LINQ 的。</span><span class="sxs-lookup"><span data-stu-id="ddac4-115">Thus, any `IEnumerable<>` implementation is automatically LINQ-enabled.</span></span>  
  
-   <span data-ttu-id="ddac4-116">实例方法时将引入依赖于某些类型，但此类依赖项将会破坏依赖项管理规则。</span><span class="sxs-lookup"><span data-stu-id="ddac4-116">When an instance method would introduce a dependency on some type, but such a dependency would break dependency management rules.</span></span> <span data-ttu-id="ddac4-117">例如，依赖项从<xref:System.String>到<xref:System.Uri?displayProperty=nameWithType>可能是不可取，，因此`String.ToUri()`返回的实例方法`System.Uri`会从依赖关系管理角度来看了错误的设计。</span><span class="sxs-lookup"><span data-stu-id="ddac4-117">For example, a dependency from <xref:System.String> to <xref:System.Uri?displayProperty=nameWithType> is probably not desirable, and so `String.ToUri()` instance method returning `System.Uri` would be the wrong design from a dependency management perspective.</span></span> <span data-ttu-id="ddac4-118">静态扩展方法`Uri.ToUri(this string str)`返回`System.Uri`是多更好的设计。</span><span class="sxs-lookup"><span data-stu-id="ddac4-118">A static extension method `Uri.ToUri(this string str)` returning `System.Uri` would be a much better design.</span></span>  
  
 <span data-ttu-id="ddac4-119">**X AVOID** 上定义的扩展方法<xref:System.Object?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="ddac4-119">**X AVOID** defining extension methods on <xref:System.Object?displayProperty=nameWithType>.</span></span>  
  
 <span data-ttu-id="ddac4-120">VB 用户不能使用扩展方法语法的对象引用上调用此类方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-120">VB users will not be able to call such methods on object references using the extension method syntax.</span></span> <span data-ttu-id="ddac4-121">VB 不支持调用此类方法，因为在 VB 中声明一个引用，因为对象会强制其将晚上的所有方法调用绑定 （名为的实际成员确定在运行时），而在 （提前编译时确定绑定到扩展方法绑定到的）。</span><span class="sxs-lookup"><span data-stu-id="ddac4-121">VB does not support calling such methods because, in VB, declaring a reference as Object forces all method invocations on it to be late bound (actual member called is determined at runtime), while bindings to extension methods are determined at compile-time (early bound).</span></span>  
  
 <span data-ttu-id="ddac4-122">请注意，该原则适用于其他语言相同的绑定行为是存在，或不支持的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-122">Note that the guideline applies to other languages where the same binding behavior is present, or where extension methods are not supported.</span></span>  
  
 <span data-ttu-id="ddac4-123">**X DO NOT** 置于扩展的类型相同的命名空间的扩展方法，除非它是为添加到接口的方法或依赖关系管理。</span><span class="sxs-lookup"><span data-stu-id="ddac4-123">**X DO NOT** put extension methods in the same namespace as the extended type unless it is for adding methods to interfaces or for dependency management.</span></span>  
  
 <span data-ttu-id="ddac4-124">**X AVOID** 定义两个或多个具有相同签名的扩展方法，即使它们驻留在不同的命名空间。</span><span class="sxs-lookup"><span data-stu-id="ddac4-124">**X AVOID** defining two or more extension methods with the same signature, even if they reside in different namespaces.</span></span>  
  
 <span data-ttu-id="ddac4-125">**✓ CONSIDER** 在扩展的类型相同的命名空间中定义的扩展方法，如果类型是接口，并且扩展方法为了在大多数或所有情况下使用。</span><span class="sxs-lookup"><span data-stu-id="ddac4-125">**✓ CONSIDER** defining extension methods in the same namespace as the extended type if the type is an interface and if the extension methods are meant to be used in most or all cases.</span></span>  
  
 <span data-ttu-id="ddac4-126">**X DO NOT** 定义在与其他功能正常关联的命名空间中实现功能的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="ddac4-126">**X DO NOT** define extension methods implementing a feature in namespaces normally associated with other features.</span></span> <span data-ttu-id="ddac4-127">相反，它们属于该功能关联的命名空间中定义它们。</span><span class="sxs-lookup"><span data-stu-id="ddac4-127">Instead, define them in the namespace associated with the feature they belong to.</span></span>  
  
 <span data-ttu-id="ddac4-128">**X AVOID** 泛型命名的命名空间专用于扩展方法 （例如，"扩展"）。</span><span class="sxs-lookup"><span data-stu-id="ddac4-128">**X AVOID** generic naming of namespaces dedicated to extension methods (e.g., "Extensions").</span></span> <span data-ttu-id="ddac4-129">使用描述性的名称 （例如，"路由"） 相反。</span><span class="sxs-lookup"><span data-stu-id="ddac4-129">Use a descriptive name (e.g., "Routing") instead.</span></span>  
  
 <span data-ttu-id="ddac4-130">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="ddac4-130">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="ddac4-131">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="ddac4-131">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ddac4-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="ddac4-132">See also</span></span>

- [<span data-ttu-id="ddac4-133">成员设计准则</span><span class="sxs-lookup"><span data-stu-id="ddac4-133">Member Design Guidelines</span></span>](../../../docs/standard/design-guidelines/member.md)  
- [<span data-ttu-id="ddac4-134">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="ddac4-134">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
