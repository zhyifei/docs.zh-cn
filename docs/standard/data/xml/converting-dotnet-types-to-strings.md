---
title: 将 .NET Framework 类型转换为字符串
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
ms.openlocfilehash: a63e0175f6660967eb4aa678c6731d353e44e2d5
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/07/2020
ms.locfileid: "75711072"
---
# <a name="converting-net-framework-types-to-strings"></a>将 .NET Framework 类型转换为字符串
若要将 .NET Framework 类型转换为字符串，请使用 ToString 方法。 ToString 方法返回传入的类型的字符串表示形式。 下表列出了以映射到 XML 架构 (XSD) 规范的格式返回字符串的 .NET Framework 类型。  
  
|.NET Framework 类型|返回的字符串类型|  
|-------------------------|--------------------------|  
|Boolean|“true”、“false”|  
|Single.PositiveInfinity|“INF”|  
|Single.NegativeInfinity|“-INF”|  
|Double.PositiveInfinity|“INF”|  
|Double.NegativeInfinity|“-INF”|  
|DateTime|格式为 yyyy-MM-ddTHH:mm:sszzzzzz 及其子集。|  
|Timespan|格式是 PnYnMnTnHnMnS，例如，`P2Y10M15DT10H30M20S` 表示长 2 年 10 个月 15 天 10 小时 30 分钟 20 秒的持续时间。|  
  
## <a name="see-also"></a>另请参阅

- [XML 数据类型转换](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)
- [将字符串转换为 .NET Framework 数据类型](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
