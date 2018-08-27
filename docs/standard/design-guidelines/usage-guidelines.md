---
title: 使用准则
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7bd54a2325c9721ad17943ba663e7ec0c300632e
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2018
ms.locfileid: "42925071"
---
# <a name="usage-guidelines"></a><span data-ttu-id="58e6a-102">使用准则</span><span class="sxs-lookup"><span data-stu-id="58e6a-102">Usage guidelines</span></span>

<span data-ttu-id="58e6a-103">本部分包含在可公开访问的 Api 中使用公共类型的指导原则。</span><span class="sxs-lookup"><span data-stu-id="58e6a-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="58e6a-104">它可以处理直接使用内置的框架类型 （例如，序列化属性） 和重载常见的运算符。</span><span class="sxs-lookup"><span data-stu-id="58e6a-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="58e6a-105"><xref:System.IDisposable?displayProperty=nameWithType>接口未涵盖在此部分中，但在讨论[Dispose 模式](../../../docs/standard/design-guidelines/dispose-pattern.md)部分。</span><span class="sxs-lookup"><span data-stu-id="58e6a-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="58e6a-106">有关指导原则和其他常见有关其他信息，内置的.NET Framework 类型，请参阅以下参考主题： <xref:System.DateTime?displayProperty=nameWithType>， <xref:System.DateTimeOffset?displayProperty=nameWithType>， <xref:System.ICloneable?displayProperty=nameWithType>， <xref:System.IComparable%601?displayProperty=nameWithType>， <xref:System.IEquatable%601?displayProperty=nameWithType>， <xref:System.Nullable%601?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="58e6a-106">For guidelines and additional information about about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="58e6a-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="58e6a-107">In this section</span></span>

[<span data-ttu-id="58e6a-108">数组</span><span class="sxs-lookup"><span data-stu-id="58e6a-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="58e6a-109">特性</span><span class="sxs-lookup"><span data-stu-id="58e6a-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="58e6a-110">集合</span><span class="sxs-lookup"><span data-stu-id="58e6a-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="58e6a-111">序列化</span><span class="sxs-lookup"><span data-stu-id="58e6a-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="58e6a-112">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="58e6a-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="58e6a-113">相等运算符</span><span class="sxs-lookup"><span data-stu-id="58e6a-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="58e6a-114">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="58e6a-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="58e6a-115">*经 Pearson Education, Inc 授权，转载自[框架设计准则：可重用的 .NET 库的约定、习惯用语和模式，第2版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) 作者：Krzysztof Cwalina 和 Brad Abrams，由 Addison Wesley Professional 于 2008 年 10 月 22 日印发，作为 Microsoft Windows 开发系列的一部分。*</span><span class="sxs-lookup"><span data-stu-id="58e6a-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="58e6a-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="58e6a-116">See also</span></span>

[<span data-ttu-id="58e6a-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="58e6a-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
