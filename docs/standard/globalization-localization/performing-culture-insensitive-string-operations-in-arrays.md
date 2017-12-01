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
# <a name="performing-culture-insensitive-string-operations-in-arrays"></a>在数组中执行不区分区域性的字符串操作
重载的<xref:System.Array.Sort%2A?displayProperty=nameWithType>和<xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>方法执行区分区域性的排序通过默认使用<xref:System.Threading.Thread.CurrentCulture%2A?displayProperty=nameWithType>属性。 返回由这些方法的区分区域性的结果可能会因由于排序顺序不同的区域性。 若要消除区分区域性的行为，请使用接受此方法的重载之一`comparer`参数。 `comparer`参数指定<xref:System.Collections.IComparer>比较数组中的元素时要使用的实现。 对于参数，指定使用的自定义固定的比较器类<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>。 中的"使用 SortedList 类"子主题提供自定义固定的比较器类的一个示例[集合中的执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations-in-collections.md)主题。  
  
 **请注意**传递**CultureInfo.InvariantCulture**与比较方法并执行不区分区域性的比较。 但是，这不会导致对文件路径、注册表项、环境变量等进行非语义比较。 也不支持基于比较结果的安全决策。 对于非语言比较或结果基于安全决策的支持，应用程序应使用的比较方法，接受<xref:System.StringComparison>值。 应用程序应传递<xref:System.StringComparison.Ordinal>。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 <xref:System.Array.BinarySearch%2A?displayProperty=nameWithType>  
 <xref:System.Collections.IComparer>  
 [执行不区分区域性的字符串操作](../../../docs/standard/globalization-localization/performing-culture-insensitive-string-operations.md)
