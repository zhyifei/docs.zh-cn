---
title: 命名空间的名称
ms.date: 10/22/2008
helpviewer_keywords:
- names [.NET Framework], conflicts
- names [.NET Framework], namespaces
- type names, conflicts
- namespaces [.NET Framework], names
- names [.NET Framework], type names
ms.assetid: a49058d2-0276-43a7-9502-04adddf857b2
ms.openlocfilehash: 52fee0dfaff284c2c1a6afcb8aa7530c28a60d65
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744138"
---
# <a name="names-of-namespaces"></a><span data-ttu-id="11b94-102">命名空间的名称</span><span class="sxs-lookup"><span data-stu-id="11b94-102">Names of Namespaces</span></span>
<span data-ttu-id="11b94-103">与其他命名准则一样，为命名空间命名的目的是为了让使用该框架的程序员能够通过名称快速了解命名空间所涉及的内容。</span><span class="sxs-lookup"><span data-stu-id="11b94-103">As with other naming guidelines, the goal when naming namespaces is creating sufficient clarity for the programmer using the framework to immediately know what the content of the namespace is likely to be.</span></span> <span data-ttu-id="11b94-104">以下模板指定了为命名空间命名的一般规则：</span><span class="sxs-lookup"><span data-stu-id="11b94-104">The following template specifies the general rule for naming namespaces:</span></span>

 `<Company>.(<Product>|<Technology>)[.<Feature>][.<Subnamespace>]`

 <span data-ttu-id="11b94-105">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="11b94-105">The following are examples:</span></span>

 <span data-ttu-id="11b94-106">`Fabrikam.Math` `Litware.Security`</span><span class="sxs-lookup"><span data-stu-id="11b94-106">`Fabrikam.Math` `Litware.Security`</span></span>

 <span data-ttu-id="11b94-107">✔️使用公司名称作为命名空间名称的前缀，以防不同公司的命名空间具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-107">✔️ DO prefix namespace names with a company name to prevent namespaces from different companies from having the same name.</span></span>

 <span data-ttu-id="11b94-108">✔️在命名空间名称的第二级使用稳定的独立于版本的产品名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-108">✔️ DO use a stable, version-independent product name at the second level of a namespace name.</span></span>

 <span data-ttu-id="11b94-109">❌ 不要使用组织层次结构作为命名空间层次结构中的名称的基础，因为公司内的组名通常是短期的。</span><span class="sxs-lookup"><span data-stu-id="11b94-109">❌ DO NOT use organizational hierarchies as the basis for names in namespace hierarchies, because group names within corporations tend to be short-lived.</span></span> <span data-ttu-id="11b94-110">围绕一组相关技术组织命名空间的层次结构。</span><span class="sxs-lookup"><span data-stu-id="11b94-110">Organize the hierarchy of namespaces around groups of related technologies.</span></span>

 <span data-ttu-id="11b94-111">✔️使用 PascalCasing，并使用句点（如 `Microsoft.Office.PowerPoint`）分隔命名空间组件。</span><span class="sxs-lookup"><span data-stu-id="11b94-111">✔️ DO use PascalCasing, and separate namespace components with periods (e.g., `Microsoft.Office.PowerPoint`).</span></span> <span data-ttu-id="11b94-112">如果品牌使用非传统的大小写形式，则应遵循由品牌定义的大小写，即使与通常的命名空间大小写不符也是如此。</span><span class="sxs-lookup"><span data-stu-id="11b94-112">If your brand employs nontraditional casing, you should follow the casing defined by your brand, even if it deviates from normal namespace casing.</span></span>

 <span data-ttu-id="11b94-113">✔️考虑在适当的情况下使用复数命名空间名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-113">✔️ CONSIDER using plural namespace names where appropriate.</span></span>

 <span data-ttu-id="11b94-114">例如，使用 `System.Collections` 而不是 `System.Collection`。</span><span class="sxs-lookup"><span data-stu-id="11b94-114">For example, use `System.Collections` instead of `System.Collection`.</span></span> <span data-ttu-id="11b94-115">但此规则不适用于品牌名称和首字母缩写词。</span><span class="sxs-lookup"><span data-stu-id="11b94-115">Brand names and acronyms are exceptions to this rule, however.</span></span> <span data-ttu-id="11b94-116">例如，使用 `System.IO` 而不是 `System.IOs`。</span><span class="sxs-lookup"><span data-stu-id="11b94-116">For example, use `System.IO` instead of `System.IOs`.</span></span>

 <span data-ttu-id="11b94-117">对于命名空间和该命名空间中的类型，❌ 不要使用相同的名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-117">❌ DO NOT use the same name for a namespace and a type in that namespace.</span></span>

 <span data-ttu-id="11b94-118">例如，不要将 `Debug` 用作命名空间名称，然后在相同的命名空间中提供名为 `Debug` 的类。</span><span class="sxs-lookup"><span data-stu-id="11b94-118">For example, do not use `Debug` as a namespace name and then also provide a class named `Debug` in the same namespace.</span></span> <span data-ttu-id="11b94-119">某些编译器要求这些类型为完全限定类型。</span><span class="sxs-lookup"><span data-stu-id="11b94-119">Several compilers require such types to be fully qualified.</span></span>

### <a name="namespaces-and-type-name-conflicts"></a><span data-ttu-id="11b94-120">命名空间和类型名称冲突</span><span class="sxs-lookup"><span data-stu-id="11b94-120">Namespaces and Type Name Conflicts</span></span>
 <span data-ttu-id="11b94-121">❌ 不会引入泛型类型名称，如 `Element`、`Node`、`Log`和 `Message`。</span><span class="sxs-lookup"><span data-stu-id="11b94-121">❌ DO NOT introduce generic type names such as `Element`, `Node`, `Log`, and `Message`.</span></span>

 <span data-ttu-id="11b94-122">很多情况下，这样做会导致在常见方案中发生类型名称冲突。</span><span class="sxs-lookup"><span data-stu-id="11b94-122">There is a very high probability that doing so will lead to type name conflicts in common scenarios.</span></span> <span data-ttu-id="11b94-123">应限定泛型类型名称（`FormElement`、`XmlNode`、`EventLog``SoapMessage`）。</span><span class="sxs-lookup"><span data-stu-id="11b94-123">You should qualify the generic type names (`FormElement`, `XmlNode`, `EventLog`, `SoapMessage`).</span></span>

 <span data-ttu-id="11b94-124">针对不同类别的命名空间，存在避免类型名称冲突的特定准则。</span><span class="sxs-lookup"><span data-stu-id="11b94-124">There are specific guidelines for avoiding type name conflicts for different categories of namespaces.</span></span>

- <span data-ttu-id="11b94-125">**应用程序模型命名空间**</span><span class="sxs-lookup"><span data-stu-id="11b94-125">**Application model namespaces**</span></span>

     <span data-ttu-id="11b94-126">属于同一应用程序模型的命名空间经常一起使用，但它们几乎从不与其他应用程序模型的命名空间一起使用。</span><span class="sxs-lookup"><span data-stu-id="11b94-126">Namespaces belonging to a single application model are very often used together, but they are almost never used with namespaces of other application models.</span></span> <span data-ttu-id="11b94-127">例如，<xref:System.Windows.Forms?displayProperty=nameWithType> 命名空间非常少与 <xref:System.Web.UI?displayProperty=nameWithType> 命名空间一起使用。</span><span class="sxs-lookup"><span data-stu-id="11b94-127">For example, the <xref:System.Windows.Forms?displayProperty=nameWithType> namespace is very rarely used together with the <xref:System.Web.UI?displayProperty=nameWithType> namespace.</span></span> <span data-ttu-id="11b94-128">下面列出了众所周知的应用程序模型命名空间组：</span><span class="sxs-lookup"><span data-stu-id="11b94-128">The following is a list of well-known application model namespace groups:</span></span>

     <span data-ttu-id="11b94-129">`System.Windows*` `System.Web.UI*`</span><span class="sxs-lookup"><span data-stu-id="11b94-129">`System.Windows*` `System.Web.UI*`</span></span>

     <span data-ttu-id="11b94-130">❌ 不要为单个应用程序模型中的命名空间中的类型指定相同的名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-130">❌ DO NOT give the same name to types in namespaces within a single application model.</span></span>

     <span data-ttu-id="11b94-131">例如，不要将名为 `Page` 的类型添加到 <xref:System.Web.UI.Adapters?displayProperty=nameWithType> 命名空间，因为 <xref:System.Web.UI?displayProperty=nameWithType> 命名空间已经包含名为 `Page`的类型。</span><span class="sxs-lookup"><span data-stu-id="11b94-131">For example, do not add a type named `Page` to the <xref:System.Web.UI.Adapters?displayProperty=nameWithType> namespace, because the <xref:System.Web.UI?displayProperty=nameWithType> namespace already contains a type named `Page`.</span></span>

- <span data-ttu-id="11b94-132">**基础结构命名空间**</span><span class="sxs-lookup"><span data-stu-id="11b94-132">**Infrastructure namespaces**</span></span>

     <span data-ttu-id="11b94-133">该组包含在开发常见应用程序期间鲜少导入的命名空间。</span><span class="sxs-lookup"><span data-stu-id="11b94-133">This group contains namespaces that are rarely imported during development of common applications.</span></span> <span data-ttu-id="11b94-134">例如，`.Design` 命名空间主要在开发编程工具时使用。</span><span class="sxs-lookup"><span data-stu-id="11b94-134">For example, `.Design` namespaces are mainly used when developing programming tools.</span></span> <span data-ttu-id="11b94-135">避免与这些命名空间中的类型发生冲突并不重要。</span><span class="sxs-lookup"><span data-stu-id="11b94-135">Avoiding conflicts with types in these namespaces is not critical.</span></span>

- <span data-ttu-id="11b94-136">**核心命名空间**</span><span class="sxs-lookup"><span data-stu-id="11b94-136">**Core namespaces**</span></span>

     <span data-ttu-id="11b94-137">核心命名空间包括所有 `System` 命名空间（不包括应用程序模型的命名空间和基础结构命名空间）。</span><span class="sxs-lookup"><span data-stu-id="11b94-137">Core namespaces include all `System` namespaces, excluding namespaces of the application models and the Infrastructure namespaces.</span></span> <span data-ttu-id="11b94-138">核心命名空间包括其他 `System`、`System.IO`、`System.Xml`和 `System.Net`。</span><span class="sxs-lookup"><span data-stu-id="11b94-138">Core namespaces include, among others, `System`, `System.IO`, `System.Xml`, and `System.Net`.</span></span>

     <span data-ttu-id="11b94-139">❌ 不要提供会与核心命名空间中的任何类型发生冲突的类型名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-139">❌ DO NOT give types names that would conflict with any type in the Core namespaces.</span></span>

     <span data-ttu-id="11b94-140">例如，切勿将 `Stream` 用作类型名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-140">For example, never use `Stream` as a type name.</span></span> <span data-ttu-id="11b94-141">它会与 <xref:System.IO.Stream?displayProperty=nameWithType>（一种非常常用的类型）冲突。</span><span class="sxs-lookup"><span data-stu-id="11b94-141">It would conflict with <xref:System.IO.Stream?displayProperty=nameWithType>, a very commonly used type.</span></span>

- <span data-ttu-id="11b94-142">**技术命名空间组**</span><span class="sxs-lookup"><span data-stu-id="11b94-142">**Technology namespace groups**</span></span>

     <span data-ttu-id="11b94-143">此类别包括 `(<Company>.<Technology>*`的前两个命名空间节点相同的所有命名空间，如 `Microsoft.Build.Utilities` 和 `Microsoft.Build.Tasks`。</span><span class="sxs-lookup"><span data-stu-id="11b94-143">This category includes all namespaces with the same first two namespace nodes `(<Company>.<Technology>*`), such as `Microsoft.Build.Utilities` and `Microsoft.Build.Tasks`.</span></span> <span data-ttu-id="11b94-144">属于同一单一技术的类型之间不能相互冲突，这一点很重要。</span><span class="sxs-lookup"><span data-stu-id="11b94-144">It is important that types belonging to a single technology do not conflict with each other.</span></span>

     <span data-ttu-id="11b94-145">❌ 不分配与单个技术中的其他类型冲突的类型名称。</span><span class="sxs-lookup"><span data-stu-id="11b94-145">❌ DO NOT assign type names that would conflict with other types within a single technology.</span></span>

     <span data-ttu-id="11b94-146">❌ 不会引入技术命名空间中的类型和应用程序模型命名空间中的类型之间的类型名称冲突（除非该技术不应与应用程序模型一起使用）。</span><span class="sxs-lookup"><span data-stu-id="11b94-146">❌ DO NOT introduce type name conflicts between types in technology namespaces and an application model namespace (unless the technology is not intended to be used with the application model).</span></span>

 <span data-ttu-id="11b94-147">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="11b94-147">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

 <span data-ttu-id="11b94-148">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="11b94-148">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>

## <a name="see-also"></a><span data-ttu-id="11b94-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11b94-149">See also</span></span>

- [<span data-ttu-id="11b94-150">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="11b94-150">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
- [<span data-ttu-id="11b94-151">命名规则</span><span class="sxs-lookup"><span data-stu-id="11b94-151">Naming Guidelines</span></span>](../../../docs/standard/design-guidelines/naming-guidelines.md)
