---
title: 命名空间的名称
ms.date: 03/30/2017
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e0b6c5ac60474cfe984b3802e880eb58b017722
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576427"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="78a65-102">命名空间的名称</span><span class="sxs-lookup"><span data-stu-id="78a65-102">Names of Namespaces</span></span>
<span data-ttu-id="78a65-103">作为与其他命名准则命名命名空间时的目标足够清楚起见为创建使用 framework 立即知道的内容的命名空间是什么，可能需要程序员。</span><span class="sxs-lookup"><span data-stu-id="78a65-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="78a65-104">以下模板指定命名命名空间的一般规则：</span><span class="sxs-lookup"><span data-stu-id="78a65-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="78a65-105">示例如下：</span><span class="sxs-lookup"><span data-stu-id="78a65-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="78a65-106">**✓ 务必** 使用一个公司名作为命名空间的前缀，以防止不同公司的命名空间具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="78a65-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="78a65-107">**✓ DO** 命名空间名称的第二个级别使用的稳定、 独立于版本的产品名称。</span><span class="sxs-lookup"><span data-stu-id="78a65-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="78a65-108">**X DO NOT** 作为基础命名空间层次结构中的名称使用组织的层次结构，因为公司内的组名称可能会改变。</span><span class="sxs-lookup"><span data-stu-id="78a65-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="78a65-109">将组织的相关技术的组周围的命名空间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="78a65-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="78a65-110">**✓ DO** 与期使用 PascalCasing 和单独的命名空间组件 (例如， `Microsoft.Office.PowerPoint`)。</span><span class="sxs-lookup"><span data-stu-id="78a65-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="78a65-111">如果你的品牌采用非传统的大小写，则应遵循由您的品牌、 定义的大小写，即使背离常用的命名空间的大小写。</span><span class="sxs-lookup"><span data-stu-id="78a65-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="78a65-112">**✓ CONSIDER** 使用复数形式的命名空间名称，在适当的位置。</span><span class="sxs-lookup"><span data-stu-id="78a65-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="78a65-113">例如，使用`System.Collections`而不是`System.Collection`。</span><span class="sxs-lookup"><span data-stu-id="78a65-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="78a65-114">品牌名称和首字母缩写词但是是此规则的例外情况。</span><span class="sxs-lookup"><span data-stu-id="78a65-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="78a65-115">例如，使用`System.IO`而不是`System.IOs`。</span><span class="sxs-lookup"><span data-stu-id="78a65-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="78a65-116">**X DO NOT** 使用该命名空间中的命名空间和类型相同的名称。</span><span class="sxs-lookup"><span data-stu-id="78a65-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="78a65-117">例如，不要使用`Debug`与命名空间名称，然后还提供一个名为类`Debug`同一命名空间中。</span><span class="sxs-lookup"><span data-stu-id="78a65-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="78a65-118">多个编译器要求是完全限定的此类类型。</span><span class="sxs-lookup"><span data-stu-id="78a65-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="78a65-119">命名空间和类型名称冲突</span><span class="sxs-lookup"><span data-stu-id="78a65-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="78a65-120">**X DO NOT** 如引入泛型类型名称`Element`， `Node`， `Log`，和`Message`。</span><span class="sxs-lookup"><span data-stu-id="78a65-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="78a65-121">没有这样做将导致类型名称共同点冲突方案非常高概率。</span><span class="sxs-lookup"><span data-stu-id="78a65-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="78a65-122">你应限定泛型类型名称 (`FormElement`， `XmlNode`， `EventLog`， `SoapMessage`)。</span><span class="sxs-lookup"><span data-stu-id="78a65-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="78a65-123">有用于避免显示为不同类别的命名空间的类型名称冲突的特定准则。</span><span class="sxs-lookup"><span data-stu-id="78a65-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="78a65-124">**应用程序模型命名空间**</span><span class="sxs-lookup"><span data-stu-id="78a65-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="78a65-125">命名空间属于单个应用程序模型非常通常用于在一起，但几乎从未与其他应用程序模型的命名空间使用它们。</span><span class="sxs-lookup"><span data-stu-id="78a65-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="78a65-126">例如，<xref:System.Windows.Forms?displayProperty=nameWithType>连同极少数情况下使用命名空间<xref:System.Web.UI?displayProperty=nameWithType>命名空间。</span><span class="sxs-lookup"><span data-stu-id="78a65-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="78a65-127">下面是一个已知应用程序模型命名空间组的列表：</span><span class="sxs-lookup"><span data-stu-id="78a65-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="78a65-128">**X DO NOT** 为单个应用程序模型中的命名空间中的类型提供相同的名称。</span><span class="sxs-lookup"><span data-stu-id="78a65-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="78a65-129">例如，不要添加名为的类型`Page`到<xref:System.Web.UI.Adapters?displayProperty=nameWithType>命名空间，因为<xref:System.Web.UI?displayProperty=nameWithType>命名空间已包含名为的类型`Page`。</span><span class="sxs-lookup"><span data-stu-id="78a65-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="78a65-130">**基础结构命名空间**</span><span class="sxs-lookup"><span data-stu-id="78a65-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="78a65-131">此组包含在常见的应用程序开发过程中很少导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="78a65-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="78a65-132">例如，`.Design`时开发编程工具主要使用命名空间。</span><span class="sxs-lookup"><span data-stu-id="78a65-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="78a65-133">避免使用这些命名空间中的类型的冲突并不重要。</span><span class="sxs-lookup"><span data-stu-id="78a65-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="78a65-134">**核心命名空间**</span><span class="sxs-lookup"><span data-stu-id="78a65-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="78a65-135">核心命名空间包括所有`System`命名空间，不包括命名空间中的，应用程序模型和基础结构命名空间。</span><span class="sxs-lookup"><span data-stu-id="78a65-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="78a65-136">核心命名空间包含，及其他`System`， `System.IO`， `System.Xml`，和`System.Net`。</span><span class="sxs-lookup"><span data-stu-id="78a65-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="78a65-137">**X DO NOT** 给予类型会冲突的名称与核心命名空间中的任何类型。</span><span class="sxs-lookup"><span data-stu-id="78a65-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="78a65-138">例如，永远不会使用`Stream`为类型名称。</span><span class="sxs-lookup"><span data-stu-id="78a65-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="78a65-139">它将与冲突<xref:System.IO.Stream?displayProperty=nameWithType>、 一个非常常用的类型。</span><span class="sxs-lookup"><span data-stu-id="78a65-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="78a65-140">**技术命名空间组**</span><span class="sxs-lookup"><span data-stu-id="78a65-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="78a65-141">此类别包括具有相同的前两个命名空间节点的所有命名空间`(<Company>.<Technology>*`)，如`Microsoft.Build.Utilities`和`Microsoft.Build.Tasks`。</span><span class="sxs-lookup"><span data-stu-id="78a65-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="78a65-142">很重要属于某个单一技术类型不会彼此发生冲突。</span><span class="sxs-lookup"><span data-stu-id="78a65-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="78a65-143">**X DO NOT** 分配会冲突的类型名称与某个单一技术中其他类型。</span><span class="sxs-lookup"><span data-stu-id="78a65-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="78a65-144">**X DO NOT** （除非该技术不应与应用程序模型一起使用） 引入技术命名空间中的类型和应用程序模型命名空间之间的类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="78a65-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="78a65-145">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="78a65-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="78a65-146">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="78a65-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="78a65-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="78a65-147">See Also</span></span>  
 [<span data-ttu-id="78a65-148">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="78a65-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="78a65-149">命名规则</span><span class="sxs-lookup"><span data-stu-id="78a65-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
