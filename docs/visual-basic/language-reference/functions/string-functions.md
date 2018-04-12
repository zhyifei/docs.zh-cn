---
title: 字符串函数 (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0e7672f03cda99aa0e1dcecd79b0358f9d5f16f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="string-functions-visual-basic"></a>字符串函数 (Visual Basic)
下表列出了 Visual Basic 提供搜索和操作字符串的函数。  
  
|.NET framework 方法|描述|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>, <xref:Microsoft.VisualBasic.Strings.AscW%2A>|返回`Integer`值，该值表示为字符相对应的字符代码。|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>, <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|返回与指定的字符代码关联的字符。|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|返回一个从零开始的数组，包含的子集`String`数组基于指定的筛选器条件。|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|返回根据格式中包含的说明设置格式的字符串`String`表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|返回格式设置为使用系统控制面板中定义的货币符号的货币值的表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|返回表示日期/时间值的字符串表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|返回数字形式的格式设置的表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|返回以 % 字符结尾的百分比格式的表达式（即乘以 100）。|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|返回一个整数，指定在另一个字符串的第一个匹配项的开始位置。|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|返回一个字符串在另一个，从字符串右侧开始的第一个匹配项的位置。|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|返回通过联接的多个子数组中包含创建的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|返回的字符串或字符转换为小写形式。|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|返回包含指定的数目的字符串的左侧的字符的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|返回一个整数，包含字符串中的字符数。|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|返回包含调整为指定长度的指定的字符串的左对齐字符串。|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|返回包含没有前导空格的指定字符串的副本的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|返回包含指定的数量的从字符串的字符的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|返回一个字符串，其中指定的子字符串已替换为另一个子字符串指定的次数。|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|返回包含指定的数量的从右侧的字符串的字符的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|返回右对齐的字符串包含调整为指定长度的指定的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|返回包含副本的指定字符串替换不带尾随空格的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|返回一个包含指定数量的空格的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|返回包含指定的数量的子字符串中的从零开始的一维数组。|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|返回-1、 0 或 1，基于字符串比较的结果。|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|返回根据指定进行转换的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|返回字符串或对象包含的指定字符重复指定的次数。|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|返回指定字符串的字符顺序相反顺序的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|返回包含副本的指定字符串替换没有前导空格或尾随空格的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|返回的字符串或字符，其中包含指定的字符串转换为大写形式。|  
  
 你可以使用[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)语句将设置是否使用不区分大小写的文本比较字符串排序顺序由你的系统区域设置 (`Text`) 或内部的二进制表示形式的字符 （`Binary`). 默认的文本比较方法是 `Binary`。  
  
## <a name="example"></a>示例  
 此示例使用`UCase`函数以返回字符串的大写版本。  
  
 [!code-vb[VbVbalrStrings#31](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_1.vb)]  
  
## <a name="example"></a>示例  
 此示例使用`LTrim`函数去除前导空格和`RTrim`函数去除尾随空格的字符串变量。 它使用`Trim`函数以去除这两种类型的空格。  
  
 [!code-vb[VbVbalrStrings#25](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_2.vb)]  
  
## <a name="example"></a>示例  
 此示例使用`Mid`函数从字符串中返回指定的数目的字符。  
  
 [!code-vb[VbVbalrStrings#17](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_3.vb)]  
  
## <a name="example"></a>示例  
 此示例使用`Len`以返回一个字符串中的字符数。  
  
 [!code-vb[VbVbalrStrings#33](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_4.vb)]  
  
## <a name="example"></a>示例  
 此示例使用`InStr`函数以返回一个字符串在另一个字符串的第一个匹配项的位置。  
  
 [!code-vb[VbVbalrStrings#8](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_5.vb)]  
  
## <a name="example"></a>示例  
 此示例演示的各种用法`Format`函数同时使用这二者的格式化数值`String`格式以及用户定义的格式。 对于日期分隔符 (`/`)，时间分隔符 (`:`)，和 AM/PM 指示符 (`t`和`tt`)，显示你的系统的实际格式化的输出取决于代码正在使用的区域设置。 当时间和日期显示在开发环境中，可使用的短时间格式和短日期格式的代码区域设置。  
  
> [!NOTE]
>  对于使用 24 小时制，AM/PM 指示符的区域设置 (`t`和`tt`) 不显示任何内容。  
  
 [!code-vb[VbVbalrStrings#27](../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-functions_6.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [关键字](../../../visual-basic/language-reference/keywords/index.md)  
 [Visual Basic 运行库成员](../../../visual-basic/language-reference/runtime-library-members.md)  
 [字符串操作摘要](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
