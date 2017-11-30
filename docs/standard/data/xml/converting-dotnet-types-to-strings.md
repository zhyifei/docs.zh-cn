---
title: "将 .NET Framework 类型转换为字符串"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dc2e2b65-f623-4dc3-938b-d2a054d6832c
caps.latest.revision: "3"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3abe140e62f112a15a1ad1b1b2a79c14364b26d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="converting-net-framework-types-to-strings"></a>将 .NET Framework 类型转换为字符串
如果你想要将.NET Framework 类型转换为字符串，使用**ToString**方法。 **ToString**方法返回的字符串表示形式中传递的类型。 下表列出了以映射到 XML 架构 (XSD) 规范的格式返回字符串的 .NET Framework 类型。  
  
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
 [XML 数据类型的转换](../../../../docs/standard/data/xml/conversion-of-xml-data-types.md)  
 [将字符串转换为.NET Framework 数据类型](../../../../docs/standard/data/xml/converting-strings-to-dotnet-data-types.md)
