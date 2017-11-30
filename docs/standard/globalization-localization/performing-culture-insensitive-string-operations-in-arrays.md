---
title: "在数组中执行不区分区域性的字符串操作"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- culture-insensitive string operations, in arrays
- arrays [.NET Framework], culture-insensitive string operations
- comparer parameter
ms.assetid: f12922e1-6234-4165-8896-63f0653ab478
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1b4e040ed379cdbf43fbe8b2c4379fdd4dc781f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="aa8d6-102">在数组中执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="aa8d6-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="aa8d6-103">重载的<xref:System.Array.Sort%2A?displayProperty=nameWithType>和<xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>方法执行区分区域性的排序通过默认使用<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>属性。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="aa8d6-104">返回由这些方法的区分区域性的结果可能会因由于排序顺序不同的区域性。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="aa8d6-105">若要消除区分区域性的行为，请使用接受此方法的重载之一`comparer`参数。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="aa8d6-106">`comparer`参数指定<xref:System.Collections.IComparer>比较数组中的元素时要使用的实现。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="aa8d6-107">对于参数，指定使用的自定义固定的比较器类<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="aa8d6-108">中的"使用 SortedList 类"子主题提供自定义固定的比较器类的一个示例[集合中的执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)主题。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="aa8d6-109">**请注意**传递**CultureInfo.InvariantCulture**与比较方法并执行不区分区域性的比较。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="aa8d6-110">但是，这不会导致对文件路径、注册表项、环境变量等进行非语义比较。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="aa8d6-111">也不支持基于比较结果的安全决策。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="aa8d6-112">对于非语言比较或结果基于安全决策的支持，应用程序应使用的比较方法，接受<xref:System.StringComparison>值。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="aa8d6-113">应用程序应传递<xref:System.StringComparison.Ordinal>。</span><span class="sxs-lookup"><span data-stu-id="aa8d6-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa8d6-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aa8d6-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="aa8d6-115">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="aa8d6-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
