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
# <a name="names-of-namespaces"></a><span data-ttu-id="96073-102">命名空间的名称</span><span class="sxs-lookup"><span data-stu-id="96073-102">Names of Namespaces</span></span>
<span data-ttu-id="96073-103">与其他命名准则一样，为命名空间命名的目的是为了让使用该框架的程序员能够通过名称快速了解命名空间所涉及的内容。</span><span class="sxs-lookup"><span data-stu-id="96073-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="96073-104">以下模板指定了为命名空间命名的一般规则：</span><span class="sxs-lookup"><span data-stu-id="96073-104">The following template specifies the general rule for naming namespaces:</span></span>  
  
 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`  
  
 <span data-ttu-id="96073-105">示例如下：</span><span class="sxs-lookup"><span data-stu-id="96073-105">The following are examples:</span></span>  
  
 `Fabrikam.Math`  
 `Litware.Security`  
  
 <span data-ttu-id="96073-106">**✓ 务必** 使用一个公司名作为命名空间的前缀，以防止不同公司的命名空间具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="96073-106">**✓ DO** prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>  
  
 <span data-ttu-id="96073-107">**✓ 务必**在命名空间名称的第二级名称中使用稳定的、与版本无关的产品名称。</span><span class="sxs-lookup"><span data-stu-id="96073-107">**✓ DO** use a stable, version-independent product name at the second level of a namespace name.</span></span>  
  
 <span data-ttu-id="96073-108">**X 不要**使用企业组织的层次结构作为命名空间层次结构中名称的基础，因为公司内的群组名称往往是短期的。应围绕相关技术的群组来组织命名空间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="96073-108">**X DO NOT** use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="96073-109">将组织的相关技术的组周围的命名空间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="96073-109">Organize the hierarchy of namespaces around groups of related technologies.</span></span>  
  
 <span data-ttu-id="96073-110">**✓ 务必**使用 PascalCasing，并使用句点分隔命名空间组件（例如，`Microsoft.Office.PowerPoint`）。</span><span class="sxs-lookup"><span data-stu-id="96073-110">**✓ DO** use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="96073-111">如果品牌使用非传统的大小写形式，则应遵循由品牌定义的大小写，即使与通常的命名空间大小写不符也是如此。</span><span class="sxs-lookup"><span data-stu-id="96073-111">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>  
  
 <span data-ttu-id="96073-112">**✓ 考虑**在适当时使用复数形式的命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="96073-112">**✓ CONSIDER** using plural namespace names where appropriate.</span></span>  
  
 <span data-ttu-id="96073-113">例如，使用 `System.Collections` 而不是 `System.Collection`。</span><span class="sxs-lookup"><span data-stu-id="96073-113">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="96073-114">但此规则不适用于品牌名称和首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="96073-114">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="96073-115">例如，使用 `System.IO` 而不是 `System.IOs`。</span><span class="sxs-lookup"><span data-stu-id="96073-115">For example, use `System.IO` instead of `System.IOs`.</span></span>  
  
 <span data-ttu-id="96073-116">**X 不要**对命名空间和该命名空间中的类型使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="96073-116">**X DO NOT** use the same name for a namespace and a type in that namespace.</span></span>  
  
 <span data-ttu-id="96073-117">例如，如果将命名空间命名为 `Debug`，就不应在该命名空间中提供一个名为 `Debug` 的类。</span><span class="sxs-lookup"><span data-stu-id="96073-117">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="96073-118">某些编译器要求这些类型为完全限定类型。</span><span class="sxs-lookup"><span data-stu-id="96073-118">Several compilers require such types to be fully qualified.</span></span>  
  
### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="96073-119">命名空间和类型名称冲突</span><span class="sxs-lookup"><span data-stu-id="96073-119">Namespaces and Type Name Conflicts</span></span>  
 <span data-ttu-id="96073-120">**X 不要**引入泛型类型名称，如 `Element`、`Node`、`Log` 和 `Message` 等。</span><span class="sxs-lookup"><span data-stu-id="96073-120">**X DO NOT** introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>  
  
 <span data-ttu-id="96073-121">没有这样做将导致类型名称共同点冲突方案非常高概率。</span><span class="sxs-lookup"><span data-stu-id="96073-121">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="96073-122">一般情况下，这样做很可能会导致类型名称冲突。应限定泛型类型名称（`FormElement`、`XmlNode`、`EventLog`、`SoapMessage`）。</span><span class="sxs-lookup"><span data-stu-id="96073-122">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>  
  
 <span data-ttu-id="96073-123">针对不同类别的命名空间，存在避免类型名称冲突的特定准则。</span><span class="sxs-lookup"><span data-stu-id="96073-123">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>  
  
-   <span data-ttu-id="96073-124">**应用程序模型命名空间**</span><span class="sxs-lookup"><span data-stu-id="96073-124">**Application model namespaces**</span></span>  
  
     <span data-ttu-id="96073-125">属于同一应用程序模型的命名空间经常一起使用，但它们几乎从不与其他应用程序模型的命名空间一起使用。</span><span class="sxs-lookup"><span data-stu-id="96073-125">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="96073-126">例如，<xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间很少与 <xref:System.Web.UI?displayProperty=nameWithType> 命名空间一起使用。以下是一个常见的应用程序模型命名空间组的列表：</span><span class="sxs-lookup"><span data-stu-id="96073-126">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="96073-127">下面是一个已知应用程序模型命名空间组的列表：</span><span class="sxs-lookup"><span data-stu-id="96073-127">The following is a list of well-known application model namespace groups:</span></span>  
  
     `System.Windows*`   
     `System.Web.UI*`  
  
     <span data-ttu-id="96073-128">**X 不要**在单个应用程序模型中为名称空间中的类型指定相同的名称。</span><span class="sxs-lookup"><span data-stu-id="96073-128">**X DO NOT** give the same name to types in namespaces within a single application model.</span></span>  
  
     <span data-ttu-id="96073-129">例如，不要在 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 命名空间中添加名为 `Page` 的类型，因为 <xref:System.Web.UI?displayProperty=nameWithType> 命名空间已包含名为 `Page` 的类型。</span><span class="sxs-lookup"><span data-stu-id="96073-129">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>  
  
-   <span data-ttu-id="96073-130">**基础结构命名空间**</span><span class="sxs-lookup"><span data-stu-id="96073-130">**Infrastructure namespaces**</span></span>  
  
     <span data-ttu-id="96073-131">该组包含在开发常见应用程序期间鲜少导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="96073-131">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="96073-132">例如，`.Design` 命名空间主要用于开发编程工具。</span><span class="sxs-lookup"><span data-stu-id="96073-132">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="96073-133">避免与这些命名空间中的类型发生冲突并不重要。</span><span class="sxs-lookup"><span data-stu-id="96073-133">Avoiding conflicts with types in these namespaces is not critical.</span></span>  
  
-   <span data-ttu-id="96073-134">**核心命名空间**</span><span class="sxs-lookup"><span data-stu-id="96073-134">**Core namespaces**</span></span>  
  
     <span data-ttu-id="96073-135">核心命名空间包括所有 `System` 命名空间，不包括应用程序模型命名空间和基础结构命名空间。</span><span class="sxs-lookup"><span data-stu-id="96073-135">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="96073-136">核心命名空间包括 `System`、`System.IO`、`System.Xml` 和 `System.Net` 等。</span><span class="sxs-lookup"><span data-stu-id="96073-136">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>  
  
     <span data-ttu-id="96073-137">**X 不要**指定与核心命名空间中任何类型相冲突的类型名称。</span><span class="sxs-lookup"><span data-stu-id="96073-137">**X DO NOT** give types names that would conflict with any type in the Core namespaces.</span></span>  
  
     <span data-ttu-id="96073-138">例如，永远不要将 `Stream` 用作类型名称。</span><span class="sxs-lookup"><span data-stu-id="96073-138">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="96073-139">它会与十分常用的类型 <xref:System.IO.Stream?displayProperty=nameWithType> 相冲突。</span><span class="sxs-lookup"><span data-stu-id="96073-139">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>  
  
-   <span data-ttu-id="96073-140">**技术命名空间组**</span><span class="sxs-lookup"><span data-stu-id="96073-140">**Technology namespace groups**</span></span>  
  
     <span data-ttu-id="96073-141">此类别包括前两个命名空间节点一致 (`(<Company>.<Technology>*`) 的所有命名空间，例如 `Microsoft.Build.Utilities` 和 `Microsoft.Build.Tasks`。</span><span class="sxs-lookup"><span data-stu-id="96073-141">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="96073-142">属于同一单一技术的类型之间不能相互冲突，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="96073-142">It is important that types belonging to a single technology do not conflict with each other.</span></span>  
  
     <span data-ttu-id="96073-143">**X 不要**指定与单一技术中任何其他类型相冲突的类型名称。</span><span class="sxs-lookup"><span data-stu-id="96073-143">**X DO NOT** assign type names that would conflict with other types within a single technology.</span></span>  
  
     <span data-ttu-id="96073-144">**X 不要**让技术命名空间和应用程序模型命名空间中的类型之间产生类型名称冲突（除非不打算将该技术与该应用程序模型一起使用）。</span><span class="sxs-lookup"><span data-stu-id="96073-144">**X DO NOT** introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>  
  
 <span data-ttu-id="96073-145">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="96073-145">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="96073-146">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="96073-146">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="96073-147">请参阅</span><span class="sxs-lookup"><span data-stu-id="96073-147">See Also</span></span>  
 [<span data-ttu-id="96073-148">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="96073-148">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="96073-149">命名规则</span><span class="sxs-lookup"><span data-stu-id="96073-149">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
