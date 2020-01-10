---
title: 使用准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
ms.openlocfilehash: 57f6600f60e99c72b72c9f82856dc9eb631a9d4b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708992"
---
# <a name="usage-guidelines"></a><span data-ttu-id="57cc0-102">使用准则</span><span class="sxs-lookup"><span data-stu-id="57cc0-102">Usage guidelines</span></span>

<span data-ttu-id="57cc0-103">本部分包含在可公开访问的 API 中使用常见类型的指南。</span><span class="sxs-lookup"><span data-stu-id="57cc0-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="57cc0-104">其中涉及如何直接使用内置框架类型（例如，序列化属性）和重载常用运算符。</span><span class="sxs-lookup"><span data-stu-id="57cc0-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="57cc0-105"><xref:System.IDisposable?displayProperty=nameWithType> 接口不在此部分进行介绍，但在 [Dispose 模式](../garbage-collection/implementing-dispose.md) 部分进行了讨论。</span><span class="sxs-lookup"><span data-stu-id="57cc0-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../garbage-collection/implementing-dispose.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="57cc0-106">有关其他常见内置 .NET Framework 类型的指南和其他信息，请参阅以下内容的参考主题：<xref:System.DateTime?displayProperty=nameWithType>、<xref:System.DateTimeOffset?displayProperty=nameWithType>、<xref:System.ICloneable?displayProperty=nameWithType>、<xref:System.IComparable%601?displayProperty=nameWithType>、<xref:System.IEquatable%601?displayProperty=nameWithType>、<xref:System.Nullable%601?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="57cc0-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="57cc0-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="57cc0-107">In this section</span></span>

[<span data-ttu-id="57cc0-108">数组</span><span class="sxs-lookup"><span data-stu-id="57cc0-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="57cc0-109">特性</span><span class="sxs-lookup"><span data-stu-id="57cc0-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="57cc0-110">集合</span><span class="sxs-lookup"><span data-stu-id="57cc0-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="57cc0-111">序列化</span><span class="sxs-lookup"><span data-stu-id="57cc0-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="57cc0-112">System.Xml 使用情况</span><span class="sxs-lookup"><span data-stu-id="57cc0-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="57cc0-113">相等运算符</span><span class="sxs-lookup"><span data-stu-id="57cc0-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="57cc0-114">*部分©2005，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="57cc0-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="57cc0-115">\*在 Pearson Education, Inc. 授权下，由 Addison-Wesley Professional 作为 Microsoft Windows 开发系列的一部分再版自 [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)（Framework 设计准则：可重用 .NET 库的约定、惯例和模式第 2 版），由 Krzysztof Cwalina 和 Brad Abrams 发布于 2008 年 10 月 22 日。</span><span class="sxs-lookup"><span data-stu-id="57cc0-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57cc0-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57cc0-116">See also</span></span>

- [<span data-ttu-id="57cc0-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="57cc0-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
