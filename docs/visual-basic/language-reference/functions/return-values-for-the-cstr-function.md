---
title: 返回 CStr 函数的值
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
ms.openlocfilehash: 4a40777c7290ec6d8c0d032f2edca5d889e20f04
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349990"
---
# <a name="return-values-for-the-cstr-function-visual-basic"></a>返回 CStr 函数的值 (Visual Basic)
下表描述了 `expression`的不同数据类型 `CStr` 的返回值。  
  
|如果 `expression` 类型为|`CStr` 返回|  
|-----------------------------|--------------------|  
|[Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|包含 "True" 或 "False" 的字符串。|  
|[Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)|一个字符串，包含系统的短日期格式的 `Date` 值（日期和时间）。|  
|[数值数据类型](../../../visual-basic/programming-guide/language-features/data-types/numeric-data-types.md)|表示数字的字符串。|  
  
## <a name="cstr-and-date"></a>CStr 和日期  
 `Date` 类型始终包含日期和时间信息。 出于类型转换的目的，Visual Basic 将1/1/0001 （第1年1月1日）视为日期的*非特定值*，00:00:00 （午夜）为时间的非特定值。 `CStr` 不会在生成的字符串中包含非特定值。 例如，如果将 `#January 1, 0001 9:30:00#` 转换为字符串，则结果为 "9:30:00 AM";禁止显示日期信息。 但是，日期信息仍以原始 `Date` 值形式存在，可以通过 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>等功能进行恢复。  
  
> [!NOTE]
> `CStr` 函数根据应用程序的当前区域性设置来执行转换。 若要获取特定区域性中的数字的字符串表示形式，请使用该数字的 `ToString(IFormatProvider)` 方法。 例如，在将 `Double` 类型的值转换为 `String`时，使用 <xref:System.Double.ToString%2A?displayProperty=nameWithType>。  
  
## <a name="see-also"></a>另请参阅

- <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A>
- [Type Conversion Functions](../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [Boolean 数据类型](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [Date 数据类型](../../../visual-basic/language-reference/data-types/date-data-type.md)
