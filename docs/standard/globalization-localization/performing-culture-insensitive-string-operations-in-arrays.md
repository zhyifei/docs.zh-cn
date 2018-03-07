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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: d273fbaa792092f5ea56bfa59392794b6728ed67
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a><span data-ttu-id="6adcf-102">在数组中执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="6adcf-102">Performing Culture-Insensitive String Operations in Arrays</span></span>
<span data-ttu-id="6adcf-103">默认情况下，<xref:System.Array.Sort%2A?displayProperty=nameWithType> 和 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 方法重载使用 <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> 属性执行区域性敏感型排序。</span><span class="sxs-lookup"><span data-stu-id="6adcf-103">Overloads of the <xref:System.Array.Sort%2A?displayProperty=nameWithType> and <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> methods perform culture-sensitive sorts by default using the <xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="6adcf-104">由于排序顺序不同，因此这些方法返回的区域性敏感型结果可能会因区域性而异。</span><span class="sxs-lookup"><span data-stu-id="6adcf-104">Culture-sensitive results returned by these methods can vary by culture due to differences in sort orders.</span></span> <span data-ttu-id="6adcf-105">若要消除区域性敏感型行为，请使用需要使用 `comparer` 参数的此方法重载之一。</span><span class="sxs-lookup"><span data-stu-id="6adcf-105">To eliminate culture-sensitive behavior, use one of the overloads of this method that accepts a `comparer` parameter.</span></span> <span data-ttu-id="6adcf-106">`comparer` 参数指定要在比较数组元素时使用的 <xref:System.Collections.IComparer> 实现。</span><span class="sxs-lookup"><span data-stu-id="6adcf-106">The `comparer` parameter specifies the <xref:System.Collections.IComparer> implementation to use when comparing elements in the array.</span></span> <span data-ttu-id="6adcf-107">对于参数，指定使用 <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType> 的自定义固定比较器类。</span><span class="sxs-lookup"><span data-stu-id="6adcf-107">For the parameter, specify a custom invariant comparer class that uses <xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="6adcf-108">[在集合中执行非区域性敏感型字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)主题的“使用 SortedList 类”子主题提供了自定义固定比较器类的示例。</span><span class="sxs-lookup"><span data-stu-id="6adcf-108">An example of a custom invariant comparer class is provided in the "Using the SortedList Class" subtopic of the [Performing Culture-Insensitive String Operations in Collections](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md) topic.</span></span>  
  
 <span data-ttu-id="6adcf-109">**注意**：向比较方法传递 CultureInfo.InvariantCulture 确实会执行非区域性敏感型比较。</span><span class="sxs-lookup"><span data-stu-id="6adcf-109">**Note** Passing **CultureInfo.InvariantCulture** to a comparison method does perform a culture-insensitive comparison.</span></span> <span data-ttu-id="6adcf-110">但是，这不会导致对文件路径、注册表项、环境变量等进行非语义比较。</span><span class="sxs-lookup"><span data-stu-id="6adcf-110">However, it does not cause a non-linguistic comparison, for example, for file paths, registry keys, and environment variables.</span></span> <span data-ttu-id="6adcf-111">也不支持基于比较结果的安全决策。</span><span class="sxs-lookup"><span data-stu-id="6adcf-111">Neither does it support security decisions based on the comparison result.</span></span> <span data-ttu-id="6adcf-112">若要进行非语义比较或支持基于结果的安全决策，应用应使用接受 <xref:System.StringComparison> 值的比较方法。</span><span class="sxs-lookup"><span data-stu-id="6adcf-112">For a non-linguistic comparison or support for result-based security decisions, the application should use a comparison method that accepts a <xref:System.StringComparison> value.</span></span> <span data-ttu-id="6adcf-113">然后，应用应传递 <xref:System.StringComparison.Ordinal>。</span><span class="sxs-lookup"><span data-stu-id="6adcf-113">The application should then pass <xref:System.StringComparison.Ordinal>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6adcf-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="6adcf-114">See Also</span></span>  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [<span data-ttu-id="6adcf-115">执行不区分区域性的字符串操作</span><span class="sxs-lookup"><span data-stu-id="6adcf-115">Performing Culture-Insensitive String Operations</span></span>](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
