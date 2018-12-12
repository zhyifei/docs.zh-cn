---
title: 使用准则
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
author: KrzysztofCwalina
ms.openlocfilehash: 761570b899a2a36391eb81dc7f42e13fff1f14ef
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53155400"
---
# <a name="usage-guidelines"></a><span data-ttu-id="da55e-102">使用准则</span><span class="sxs-lookup"><span data-stu-id="da55e-102">Usage guidelines</span></span>

<span data-ttu-id="da55e-103">本部分包含在可公开访问的 API 中使用常见类型的指南。</span><span class="sxs-lookup"><span data-stu-id="da55e-103">This section contains guidelines for using common types in publicly accessible APIs.</span></span> <span data-ttu-id="da55e-104">其中涉及如何直接使用内置框架类型（例如，序列化属性）和重载常用运算符。</span><span class="sxs-lookup"><span data-stu-id="da55e-104">It deals with direct usage of built-in Framework types (e.g., serialization attributes) and overloading common operators.</span></span>
  
<span data-ttu-id="da55e-105"><xref:System.IDisposable?displayProperty=nameWithType> 接口不在此部分进行介绍，但在 [Dispose 模式](../../../docs/standard/design-guidelines/dispose-pattern.md) 部分进行了讨论。</span><span class="sxs-lookup"><span data-stu-id="da55e-105">The <xref:System.IDisposable?displayProperty=nameWithType> interface is not covered in this section, but is discussed in the [Dispose Pattern](../../../docs/standard/design-guidelines/dispose-pattern.md) section.</span></span>

> [!NOTE]
> <span data-ttu-id="da55e-106">有关其他常见内置 .NET Framework 类型的指南和其他信息，请参阅以下内容的参考主题：<xref:System.DateTime?displayProperty=nameWithType>、<xref:System.DateTimeOffset?displayProperty=nameWithType>、<xref:System.ICloneable?displayProperty=nameWithType>、<xref:System.IComparable%601?displayProperty=nameWithType>、<xref:System.IEquatable%601?displayProperty=nameWithType>、<xref:System.Nullable%601?displayProperty=nameWithType>、<xref:System.Object?displayProperty=nameWithType>、<xref:System.Uri?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="da55e-106">For guidelines and additional information about other common, built-in .NET Framework types, see the reference topics for the following: <xref:System.DateTime?displayProperty=nameWithType>, <xref:System.DateTimeOffset?displayProperty=nameWithType>, <xref:System.ICloneable?displayProperty=nameWithType>, <xref:System.IComparable%601?displayProperty=nameWithType>, <xref:System.IEquatable%601?displayProperty=nameWithType>, <xref:System.Nullable%601?displayProperty=nameWithType>, <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="da55e-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="da55e-107">In this section</span></span>

[<span data-ttu-id="da55e-108">数组</span><span class="sxs-lookup"><span data-stu-id="da55e-108">Arrays</span></span>](arrays.md)  
[<span data-ttu-id="da55e-109">属性</span><span class="sxs-lookup"><span data-stu-id="da55e-109">Attributes</span></span>](attributes.md)  
[<span data-ttu-id="da55e-110">集合</span><span class="sxs-lookup"><span data-stu-id="da55e-110">Collections</span></span>](guidelines-for-collections.md)  
[<span data-ttu-id="da55e-111">序列化</span><span class="sxs-lookup"><span data-stu-id="da55e-111">Serialization</span></span>](serialization.md)  
[<span data-ttu-id="da55e-112">System.Xml 用法</span><span class="sxs-lookup"><span data-stu-id="da55e-112">System.Xml Usage</span></span>](system-xml-usage.md)  
[<span data-ttu-id="da55e-113">相等运算符</span><span class="sxs-lookup"><span data-stu-id="da55e-113">Equality Operators</span></span>](equality-operators.md)  

<span data-ttu-id="da55e-114">*部分版权 © 2005, 2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="da55e-114">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>

<span data-ttu-id="da55e-115">*通过从 Pearson Education，Inc.的权限重新打印[Framework 设计准则：约定、 语法和模式的可重用.NET 库，第 2 版](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)Krzysztof Cwalina 和 Brad Abrams，作为 Microsoft Windows 开发系列的一部分发布 2008 年 10 月 22 日由 Addison-wesley 专业人员。*</span><span class="sxs-lookup"><span data-stu-id="da55e-115">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>
  
## <a name="see-also"></a><span data-ttu-id="da55e-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="da55e-116">See also</span></span>

- [<span data-ttu-id="da55e-117">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="da55e-117">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)
