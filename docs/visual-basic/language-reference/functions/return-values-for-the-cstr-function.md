---
title: 返回 CStr 函数的值 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- times [Visual Basic], CStr Function return values
- type conversion [Visual Basic]
- dates [Visual Basic], CStr Function return values
- CStr function
- strings [Visual Basic], return value
- Date data type [Visual Basic], converting
- dates [Visual Basic]
- String data type [Visual Basic], converting
ms.assetid: 3aa744e7-1419-45d5-85e3-e5abc2953673
ms.openlocfilehash: cd525ea5a295411e509f3bc37285675d15a8c4f4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930048"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>返回 CStr 函数的值 (Visual Basic)
下表描述了的不同数据`CStr` `expression`类型的返回值。  
  
|如果`expression`类型为|`CStr` 返回|  
|-----------------------------|--------------------|  
|[Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|包含 "True" 或 "False" 的字符串。|  
|[Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)|一个字符串, 包含`Date`系统的短日期格式的值 (日期和时间)。|  
|[数值数据类型](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|表示数字的字符串。|  
  
## <a name="cstr-and-date"></a>CStr 和日期  
 `Date`类型始终包含日期和时间信息。 出于类型转换的目的, Visual Basic 将 1/1/0001 (第1年1月1日) 视为日期的*非特定值*, 00:00:00 (午夜) 为时间的非特定值。 `CStr`不会在生成的字符串中包含非特定值。 例如, 如果转换`#January 1, 0001 9:30:00#`为字符串, 则结果为 "9:30:00 AM"; 日期信息将被取消。 但是, 日期信息仍以原始`Date`值的形式<xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>存在, 可以通过等函数进行恢复。  
  
> [!NOTE]
> `CStr`函数根据应用程序的当前区域性设置来执行转换。 若要获取特定区域性中的数字的字符串表示形式, 请使用数字的`ToString(IFormatProvider)`方法。 例如, 在将<xref:System.Double.ToString%2A?displayProperty=nameWithType>类型`Double`的值转换为`String`时使用。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [类型转换函数](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)
