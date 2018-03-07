---
title: "执行不区分区域性的字符串操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 62aa839d2dae2f6dc84d529a8abf5061367f221f
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations"></a><span data-ttu-id="d7974-102">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="d7974-102">Performing Culture-Insensitive String Operations</span></span>
<span data-ttu-id="d7974-103">默认情况下，大多数执行区域性敏感型字符串操作的 .NET Framework 方法提供方法重载，以便于通过传递 <xref:System.Globalization.CultureInfo> 参数来显式指定要使用的区域性。</span><span class="sxs-lookup"><span data-stu-id="d7974-103">Most .NET Framework methods that perform culture-sensitive string operations by default provide method overloads that allow you to explicitly specify the culture to use by passing a <xref:System.Globalization.CultureInfo> parameter.</span></span> <span data-ttu-id="d7974-104">这些重载允许消除大小写映射和排序规则中的区域性差异，保证获得不区分区域性的结果。</span><span class="sxs-lookup"><span data-stu-id="d7974-104">These overloads allow you to eliminate cultural variations in case mappings and sorting rules and guarantee culture-insensitive results.</span></span>  
  
 <span data-ttu-id="d7974-105">本节提供以下主题，用以说明如何使用默认区分区域性的 .NET Framework 方法执行不区分区域性的字符串操作。</span><span class="sxs-lookup"><span data-stu-id="d7974-105">This section provides the following topics to demonstrate how to perform culture-insensitive string operations using .NET Framework methods that are culture-sensitive by default.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d7974-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="d7974-106">In This Section</span></span>  
 [<span data-ttu-id="d7974-107">执行不区分区域性的字符串比较</span><span class="sxs-lookup"><span data-stu-id="d7974-107">Performing Culture-Insensitive String Comparisons</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 <span data-ttu-id="d7974-108">介绍了如何使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 和 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法执行非区域性敏感型字符串比较。</span><span class="sxs-lookup"><span data-stu-id="d7974-108">Describes how to use the <xref:System.String.Compare%2A?displayProperty=nameWithType> and <xref:System.String.CompareTo%2A?displayProperty=nameWithType> methods to perform culture-insensitive string comparisons.</span></span>  
  
 [<span data-ttu-id="d7974-109">执行不区分区域性的大小写更改</span><span class="sxs-lookup"><span data-stu-id="d7974-109">Performing Culture-Insensitive Case Changes</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 <span data-ttu-id="d7974-110">介绍了如何使用 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>、<xref:System.String.ToLower%2A?displayProperty=nameWithType>、<xref:System.Char.ToUpper%2A?displayProperty=nameWithType> 和 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 方法执行非区域性敏感型大小写更改。</span><span class="sxs-lookup"><span data-stu-id="d7974-110">Describes how to use the <xref:System.String.ToUpper%2A?displayProperty=nameWithType>, <xref:System.String.ToLower%2A?displayProperty=nameWithType>, <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>, and <xref:System.Char.ToLower%2A?displayProperty=nameWithType> methods to perform culture-insensitive case changes.</span></span>  
  
 [<span data-ttu-id="d7974-111">在集合中执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="d7974-111">Performing Culture-Insensitive String Operations in Collections</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 <span data-ttu-id="d7974-112">介绍了如何使用 <xref:System.Collections.CaseInsensitiveComparer>、<xref:System.Collections.CaseInsensitiveHashCodeProvider> 类、<xref:System.Collections.SortedList>、<xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> 和 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> 在集合中执行非区域性敏感型操作。</span><span class="sxs-lookup"><span data-stu-id="d7974-112">Describes how to use the <xref:System.Collections.CaseInsensitiveComparer>, <xref:System.Collections.CaseInsensitiveHashCodeProvider> class, <xref:System.Collections.SortedList>, <xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> and <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> to perform culture-insensitive operations in collections.</span></span>  
  
 [<span data-ttu-id="d7974-113">在数组中执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="d7974-113">Performing Culture-Insensitive String Operations in Arrays</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 <span data-ttu-id="d7974-114">介绍了如何使用 <xref:System.Array.Sort%2A?displayProperty=nameWithType> 和 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 方法在数组中执行非区域性敏感型操作。</span><span class="sxs-lookup"><span data-stu-id="d7974-114">Describes how to use the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods to perform culture-insensitive operations in arrays.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d7974-115">相关章节</span><span class="sxs-lookup"><span data-stu-id="d7974-115">Related Sections</span></span>  
 [<span data-ttu-id="d7974-116">不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="d7974-116">Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 <span data-ttu-id="d7974-117">介绍对字符串执行操作时应了解区域性的原因，并为何时执行区分区域性的操作、何时执行不区分区域性的操作提供了指南。</span><span class="sxs-lookup"><span data-stu-id="d7974-117">Describes why you should be aware of culture when performing operations on strings and provides guidelines for when to perform culture-sensitive operations and when to perform culture-insensitive operations.</span></span>
