---
title: 执行不区分区域性的字符串操作
ms.date: 08/22/2018
ms.technology: dotnet-standard
helpviewer_keywords:
- case mappings
- custom case mappings
- culture, custom sorting rules
- custom sorting rules
- culture-insensitive string operations, options for performing
- culture, custom case mappings
- culture-insensitive string operations, method overloads
ms.assetid: 579ef891-1f83-4c63-9ebd-2f40406b5b91
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 748b4170e9e4c0df048c542d06bcb64a56ccf677
ms.sourcegitcommit: fe02afbc39e78afd78cc6050e4a9c12a75f579f8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "43254640"
---
# <a name="performing-culture-insensitive-string-operations"></a>执行不区分区域性的字符串操作
默认情况下，大多数执行区域性敏感型字符串操作的 .NET Framework 方法提供方法重载，以便于通过传递 <xref:System.Globalization.CultureInfo> 参数来显式指定要使用的区域性。 这些重载允许消除大小写映射和排序规则中的区域性差异，保证获得不区分区域性的结果。  
  
 本节提供以下主题，用以说明如何使用默认区分区域性的 .NET Framework 方法执行不区分区域性的字符串操作。  
  
## <a name="in-this-section"></a>本节内容  
 [执行不区分区域性的字符串比较](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 介绍了如何使用 <xref:System.String.Compare%2A?displayProperty=nameWithType> 和 <xref:System.String.CompareTo%2A?displayProperty=nameWithType> 方法执行非区域性敏感型字符串比较。  
  
 [执行不区分区域性的大小写更改](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 介绍了如何使用 <xref:System.String.ToUpper%2A?displayProperty=nameWithType>、<xref:System.String.ToLower%2A?displayProperty=nameWithType>、<xref:System.Char.ToUpper%2A?displayProperty=nameWithType> 和 <xref:System.Char.ToLower%2A?displayProperty=nameWithType> 方法执行非区域性敏感型大小写更改。  
  
 [在集合中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 介绍了如何使用 <xref:System.Collections.CaseInsensitiveComparer>、<xref:System.Collections.CaseInsensitiveHashCodeProvider> 类、<xref:System.Collections.SortedList>、<xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType> 和 <xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType> 在集合中执行非区域性敏感型操作。  
  
 [在数组中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 介绍了如何使用 <xref:System.Array.Sort%2A?displayProperty=nameWithType> 和 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType> 方法在数组中执行非区域性敏感型操作。  
  
## <a name="related-sections"></a>相关章节  
 [不区分区域性的字符串操作](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 介绍对字符串执行操作时应了解区域性的原因，并为何时执行区分区域性的操作、何时执行不区分区域性的操作提供了指南。

## <a name="see-also"></a>请参阅

- [排序权重表](https://www.microsoft.com/en-us/download/details.aspx?id=10921)
