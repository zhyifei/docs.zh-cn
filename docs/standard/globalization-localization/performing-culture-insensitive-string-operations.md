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
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e703e9adc531b7d1695d3e9bbed61a2c0f62ad31
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="performing-culture-insensitive-string-operations"></a>执行不区分区域性的字符串操作
默认情况下执行区分区域性的字符串操作的大多数.NET Framework 方法提供允许你显式指定要使用传递的区域性的方法重载<xref:System.Globalization.CultureInfo>参数。 这些重载允许消除大小写映射和排序规则中的区域性差异，保证获得不区分区域性的结果。  
  
 本节提供以下主题，用以说明如何使用默认区分区域性的 .NET Framework 方法执行不区分区域性的字符串操作。  
  
## <a name="in-this-section"></a>本节内容  
 [执行不区分区域性的字符串比较](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-comparisons.md)  
 介绍如何使用<xref:System.String.Compare%2A?displayProperty=nameWithType>和<xref:System.String.CompareTo%2A?displayProperty=nameWithType>方法执行不区分区域性的字符串比较。  
  
 [执行不区分区域性的大小写更改](../../../docs/standard/globalization-localization/performing-culture-insensitive-case-changes.md)  
 介绍如何使用<xref:System.String.ToUpper%2A?displayProperty=nameWithType>， <xref:System.String.ToLower%2A?displayProperty=nameWithType>， <xref:System.Char.ToUpper%2A?displayProperty=nameWithType>，和<xref:System.Char.ToLower%2A?displayProperty=nameWithType>方法执行不区分区域性的大小写更改。  
  
 [在集合中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)  
 介绍如何使用<xref:System.Collections.CaseInsensitiveComparer>，<xref:System.Collections.CaseInsensitiveHashCodeProvider>类， <xref:System.Collections.SortedList>，<xref:System.Collections.ArrayList.Sort%2A?displayProperty=nameWithType>和<xref:System.Collections.Specialized.CollectionsUtil.CreateCaseInsensitiveHashtable%2A?displayProperty=nameWithType>在集合中执行不区分区域性的操作。  
  
 [在数组中执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-arrays.md)  
 介绍如何使用<xref:System.Array.Sort%2A?displayProperty=nameWithType>和<xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>方法在数组中执行不区分区域性的操作。  
  
## <a name="related-sections"></a>相关章节  
 [不区分区域性的字符串操作](../../../docs/standard/globalization-localization/culture-insensitive-string-operations.md)  
 介绍对字符串执行操作时应了解区域性的原因，并为何时执行区分区域性的操作、何时执行不区分区域性的操作提供了指南。
