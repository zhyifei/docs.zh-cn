---
title: 使用准则
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- class library design guidelines [.NET Framework], usage guidelines
ms.assetid: 42215ffa-a099-4a26-b14e-fb2bdb6f95b7
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 99feaa5a250b7a5890ca90b40061700677da8708
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2018
---
# <a name="usage-guidelines"></a>使用准则
本部分包含在可公开访问的 Api 中使用公共类型的指导原则。 它涉及到直接使用内置的 Framework 类型 （例如，序列化属性） 和重载常用的运算符。  
  
 <xref:System.IDisposable?displayProperty=nameWithType>接口在此部分中，不会对其进行介绍，但已在[释放模式](../../../docs/standard/design-guidelines/dispose-pattern.md)部分。  
  
> [!NOTE]
>  准则和其他常见有关其他信息，内置的.NET Framework 类型，请参阅以下参考主题： <xref:System.DateTime?displayProperty=nameWithType>， <xref:System.DateTimeOffset?displayProperty=nameWithType>， <xref:System.ICloneable?displayProperty=nameWithType>， <xref:System.IComparable%601?displayProperty=nameWithType>， <xref:System.IEquatable%601?displayProperty=nameWithType>， <xref:System.Nullable%601?displayProperty=nameWithType>， <xref:System.Object?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>.  
  
## <a name="in-this-section"></a>本节内容  
 [数组](../../../docs/standard/design-guidelines/arrays.md)  
 [特性](../../../docs/standard/design-guidelines/attributes.md)  
 [集合](/cpp/mfc/collections)  
 [序列化](../../../docs/standard/design-guidelines/serialization.md)  
 [System.Xml 使用情况](../../../docs/standard/design-guidelines/system-xml-usage.md)  
 [相等运算符](../../../docs/standard/design-guidelines/equality-operators.md)  
 *部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*  
  
 *通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*  
  
## <a name="see-also"></a>请参阅  
 [框架设计指南](../../../docs/standard/design-guidelines/index.md)
