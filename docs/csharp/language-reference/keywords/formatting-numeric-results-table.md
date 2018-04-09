---
title: 设置数值结果表的格式（C# 参考）
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
helpviewer_keywords:
- formatting [C#]
- numeric formatting [C#]
- String.Format method
- Console.Write method
ms.assetid: 120ba537-4448-4c62-8676-7a8fdd98f496
caps.latest.revision: 14
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: d389703c2d82d74760b99059201cb634849aa433
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="formatting-numeric-results-table-c-reference"></a>设置数值结果表的格式（C# 参考）
要设置数值结果的格式，可以使用 <xref:System.String.Format%2A?displayProperty=nameWithType> 方法、<xref:System.Console.Write%2A?displayProperty=nameWithType> 或 <xref:System.Console.WriteLine%2A?displayProperty=nameWithType> 方法（这两种方法调用 `String.Format`）或者[字符串内插](../tokens/interpolated.md)。 通过使用格式字符串指定格式。 下表包含支持的标准格式字符串。 格式字符串采用以下形式：`Axx`，其中 `A` 是格式说明符，`xx` 是精度说明符。 格式说明符控制应用于数值的格式类型，而精度说明符则控制格式化输出的有效位数或小数位数。 精度说明符值的范围为 0 到 99。  
  
 有关标准格式字符串和自定义格式字符串的详细信息，请参阅[格式设置类型](../../../standard/base-types/formatting-types.md)。
  
|格式说明符|描述|示例|输出|  
|----------------------|-----------------|--------------|------------|  
|C 或 c|货币|Console.Write("{0:C}", 2.5);<br /><br /> Console.Write("{0:C}", -2.5);|$2.50<br /><br /> ($2.50)|  
|D 或 d|Decimal|Console.Write("{0:D5}", 25);|00025|  
|E 或 e|科学记数法|Console.Write("{0:E}", 250000);|2.500000E+005|  
|F 或 f|定点|Console.Write("{0:F2}", 25);<br /><br /> Console.Write("{0:F0}", 25);|25.00<br /><br /> 25|  
|G 或 g|常规|Console.Write("{0:G}", 2.5);|2.5|  
|N 或 n|数字|Console.Write("{0:N}", 2500000);|2,500,000.00|  
|X 或 x|十六进制|Console.Write("{0:X}", 250);<br /><br /> Console.Write("{0:X}", 0xffff);|FA<br /><br /> FFFF|  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [标准数字格式字符串](../../../standard/base-types/standard-numeric-format-strings.md)  
 [类型参考表](../../../csharp/language-reference/keywords/reference-tables-for-types.md)  
 [string](../../../csharp/language-reference/keywords/string.md)
