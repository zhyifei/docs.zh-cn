---
title: 使用准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02905c193387f78430ce1885449055060d07bf82
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571028"
---
# <a name="usage-guidelines"></a><span data-ttu-id="0e015-102">使用准则</span><span class="sxs-lookup"><span data-stu-id="0e015-102">Usage Guidelines</span></span>
<span data-ttu-id="0e015-103">本部分包含在可公开访问的 Api 中使用公共类型的指导原则。</span><span class="sxs-lookup"><span data-stu-id="0e015-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="0e015-104">它涉及到直接使用内置的 Framework 类型 （例如，序列化属性） 和重载常用的运算符。</span><span class="sxs-lookup"><span data-stu-id="0e015-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>  
  
 <span data-ttu-id="0e015-105"><xref:System.IDisposable?displayProperty=nameWithType>接口在此部分中，不会对其进行介绍，但已在[释放模式](../../../docs/standard/design-guidelines/dispose-pattern.md)部分。</span><span class="sxs-lookup"><span data-stu-id="0e015-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0e015-106">准则和其他常见有关其他信息，内置的.NET Framework 类型，请参阅以下参考主题： <xref:System.DateTime?displayProperty=nameWithType>， <xref:System.DateTimeOffset?displayProperty=nameWithType>， <xref:System.ICloneable?displayProperty=nameWithType>， <xref:System.IComparable%601?displayProperty=nameWithType>， <xref:System.IEquatable%601?displayProperty=nameWithType>， <xref:System.Nullable%601?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="0e015-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0e015-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="0e015-107">In This Section</span></span>  
 [<span data-ttu-id="0e015-108">数组</span><span class="sxs-lookup"><span data-stu-id="0e015-108">Arrays</span></span>](../../../docs/standard/design-guidelines/arrays.md)  
 [<span data-ttu-id="0e015-109">特性</span><span class="sxs-lookup"><span data-stu-id="0e015-109">Attributes</span></span>](../../../docs/standard/design-guidelines/attributes.md)  
 [<span data-ttu-id="0e015-110">集合</span><span class="sxs-lookup"><span data-stu-id="0e015-110">Collections</span></span>](/cpp/mfc/collections)  
 [<span data-ttu-id="0e015-111">序列化</span><span class="sxs-lookup"><span data-stu-id="0e015-111">Serialization</span></span>](../../../docs/standard/design-guidelines/serialization.md)  
 [<span data-ttu-id="0e015-112">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="0e015-112">System.Xml Usage</span></span>](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [<span data-ttu-id="0e015-113">相等运算符</span><span class="sxs-lookup"><span data-stu-id="0e015-113">Equality Operators</span></span>](../../../docs/standard/design-guidelines/equality-operators.md)  
 <span data-ttu-id="0e015-114">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="0e015-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="0e015-115">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="0e015-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e015-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="0e015-116">See Also</span></span>  
 [<span data-ttu-id="0e015-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="0e015-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
