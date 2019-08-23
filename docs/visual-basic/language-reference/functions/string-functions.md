---
title: 字符串函数 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- string functions
ms.assetid: f1bf9ac2-cbcf-4298-ae51-53182076bdc8
ms.openlocfilehash: 4f6203fd6ae69315e7efaaa3c17bb4132bd175d8
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69930850"
---
# <a name="string-functions-visual-basic"></a>字符串函数 (Visual Basic)
下表列出了 Visual Basic 提供的用于搜索和操作字符串的函数。  
  
|.NET Framework 方法|描述|  
|---------------------------|-----------------|  
|<xref:Microsoft.VisualBasic.Strings.Asc%2A>， <xref:Microsoft.VisualBasic.Strings.AscW%2A>|返回一个`Integer`值, 该值表示与某个字符相对应的字符代码。|  
|<xref:Microsoft.VisualBasic.Strings.Chr%2A>， <xref:Microsoft.VisualBasic.Strings.ChrW%2A>|返回与指定字符代码关联的字符。|  
|<xref:Microsoft.VisualBasic.Strings.Filter%2A>|返回一个从零开始的数组, 其中包含基于`String`指定筛选条件的数组的子集。|  
|<xref:Microsoft.VisualBasic.Strings.Format%2A>|返回根据格式`String`表达式中包含的指令设置格式的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.FormatCurrency%2A>|返回使用系统控制面板中定义的货币符号格式化为货币值的表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatDateTime%2A>|返回表示日期/时间值的字符串表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatNumber%2A>|返回格式化为数字的表达式。|  
|<xref:Microsoft.VisualBasic.Strings.FormatPercent%2A>|返回以 % 字符结尾的百分比格式的表达式（即乘以 100）。|  
|<xref:Microsoft.VisualBasic.Strings.InStr%2A>|返回一个整数, 该整数指定一个字符串在另一个字符串中首次出现的开始位置。|  
|<xref:Microsoft.VisualBasic.Strings.InStrRev%2A>|返回一个字符串在另一个字符串中的第一个匹配项的位置 (从字符串的右侧开始)。|  
|<xref:Microsoft.VisualBasic.Strings.Join%2A>|返回通过联接数组中包含的多个子字符串而创建的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.LCase%2A>|返回转换为小写形式的字符串或字符。|  
|<xref:Microsoft.VisualBasic.Strings.Left%2A>|返回一个字符串, 该字符串包含从字符串左侧开始的指定数量的字符。|  
|<xref:Microsoft.VisualBasic.Strings.Len%2A>|返回一个整数, 该整数包含字符串中的字符数。|  
|<xref:Microsoft.VisualBasic.Strings.LSet%2A>|返回一个左对齐字符串, 该字符串包含调整为指定长度的指定字符串。|  
|<xref:Microsoft.VisualBasic.Strings.LTrim%2A>|返回一个字符串, 该字符串包含不带前导空格的指定字符串的副本。|  
|<xref:Microsoft.VisualBasic.Strings.Mid%2A>|返回一个字符串, 该字符串包含字符串中指定数目的字符。|  
|<xref:Microsoft.VisualBasic.Strings.Replace%2A>|返回一个字符串, 其中指定的子字符串已替换为指定次数的另一个子字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Right%2A>|返回一个字符串, 该字符串包含从字符串的右侧开始的指定数量的字符。|  
|<xref:Microsoft.VisualBasic.Strings.RSet%2A>|返回一个右对齐字符串, 该字符串包含调整为指定长度的指定字符串。|  
|<xref:Microsoft.VisualBasic.Strings.RTrim%2A>|返回一个字符串, 该字符串包含不带尾随空格的指定字符串的副本。|  
|<xref:Microsoft.VisualBasic.Strings.Space%2A>|返回由指定数量的空格组成的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Split%2A>|返回包含指定数量子字符串的从零开始的一维数组。|  
|<xref:Microsoft.VisualBasic.Strings.StrComp%2A>|基于字符串比较的结果, 返回-1、0或1。|  
|<xref:Microsoft.VisualBasic.Strings.StrConv%2A>|返回根据指定进行转换的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.StrDup%2A>|返回由指定字符重复指定次数而构成的字符串或对象。|  
|<xref:Microsoft.VisualBasic.Strings.StrReverse%2A>|返回指定字符串的字符顺序相反的字符串。|  
|<xref:Microsoft.VisualBasic.Strings.Trim%2A>|返回一个字符串, 该字符串包含不带前导空格或尾随空格的指定字符串的副本。|  
|<xref:Microsoft.VisualBasic.Strings.UCase%2A>|返回包含转换为大写的指定字符串的字符串或字符。|  
  
 您可以使用[Option Compare](../../../visual-basic/language-reference/statements/option-compare-statement.md)语句来设置是使用不区分大小写的文本排序顺序 (由系统的区域设置 (`Text`) 决定), 还是通过字符的内部二进制表示形式来比较字符串 (`Binary`)。 默认的文本比较方法是 `Binary`。  
  
## <a name="example"></a>示例  
 此示例使用`UCase`函数返回字符串的大写形式。  
  
 [!code-vb[VbVbalrStrings#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#31)]  
  
## <a name="example"></a>示例  
 此示例使用`LTrim`函数来去除前导空格`RTrim` , 并使用函数去除字符串变量中的尾随空格。 它使用`Trim`函数来去除这两种类型的空格。  
  
 [!code-vb[VbVbalrStrings#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#25)]  
  
## <a name="example"></a>示例  
 此示例使用`Mid`函数从字符串返回指定数目的字符。  
  
 [!code-vb[VbVbalrStrings#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#17)]  
  
## <a name="example"></a>示例  
 此示例使用`Len`返回字符串中的字符数。  
  
 [!code-vb[VbVbalrStrings#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#33)]  
  
## <a name="example"></a>示例  
 此示例使用`InStr`函数返回一个字符串在另一个字符串中的第一个匹配项的位置。  
  
 [!code-vb[VbVbalrStrings#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#8)]  
  
## <a name="example"></a>示例  
 此示例演示`Format`函数使用格式和用户定义格式设置值`String`格式的各种用法。 对于`/`日期分隔符 ()、时间分隔符 (`:`) 以及 AM/PM 指示符 (`t`和`tt`), 系统显示的实际格式化输出取决于代码使用的区域设置。 当在开发环境中显示时间和日期时, 将使用代码区域设置的短时间格式和短日期格式。  
  
> [!NOTE]
> 对于使用24小时制的区域设置, AM/PM 指示符 (`t`和`tt`) 不显示任何内容。  
  
 [!code-vb[VbVbalrStrings#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class1.vb#27)]  
  
## <a name="see-also"></a>请参阅

- [关键字](../../../visual-basic/language-reference/keywords/index.md)
- [Visual Basic 运行库成员](../../../visual-basic/language-reference/runtime-library-members.md)
- [字符串操作摘要](../../../visual-basic/language-reference/keywords/string-manipulation-summary.md)
