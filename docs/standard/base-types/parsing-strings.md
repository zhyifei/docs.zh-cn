---
title: 分析 .NET 中的字符串
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- parsing strings, about parsing strings
- IFormatProvider interface, parsing strings
- base types, parsing strings
- Parse method
- parsing strings
ms.assetid: 5e758b41-db93-456b-8999-99b7304b090d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a6e0e7e69affd93320ec3f3d73e6254befaf6ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="parsing-strings-in-net"></a>分析 .NET 中的字符串
分析操作将表示某种 .NET 基类型的字符串转换为该基类型。 例如，分析操作用于将字符串转换为浮点数字或日期和时间值。 最常用于执行分析操作的方法是 `Parse` 方法。 因为分析是格式设置（涉及将基类型转换为其字符串表示形式）的反向操作，所以有许多相同规则和约定适用。 就像格式设置使用对象来实现 <xref:System.IFormatProvider> 接口以提供区域性敏感型格式设置信息一样，分析也使用对象来实现 <xref:System.IFormatProvider> 接口，以确定如何解释字符串表示形式。 有关详细信息，请参阅[类型格式设置](../../../docs/standard/base-types/formatting-types.md)。  
  
## <a name="in-this-section"></a>本节内容  
 [分析数值字符串](../../../docs/standard/base-types/parsing-numeric.md)  
 介绍了如何将字符串转换为 .NET 数字类型。  
  
 [分析日期和时间字符串](../../../docs/standard/base-types/parsing-datetime.md)  
 介绍了如何将字符串转换为 .NET DateTime 类型。  
  
 [分析其他字符串](../../../docs/standard/base-types/parsing-other.md)  
 介绍了如何将字符串转换为 Char、Boolean 和 Enum 类型。  
  
## <a name="related-sections"></a>相关章节  
 [格式设置类型](../../../docs/standard/base-types/formatting-types.md)  
 介绍了基本格式设置概念，如格式说明符和格式提供程序。  
  
 [.NET 中的类型转换](../../../docs/standard/base-types/type-conversion.md)  
 介绍了如何转换类型。  
  
 [基类型](../../../docs/standard/base-types/index.md)  
 介绍了可以对 .NET 基类型执行的常见操作。
