---
title: 在 MaskedTextBox 控件中使用正则表达式
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
ms.openlocfilehash: b997f6f495fca51e888bb995fee0361d29d68048
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2020
ms.locfileid: "79148279"
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>在 MaskedTextBox 控件中使用正则表达式 (Visual Basic)
此示例演示如何转换简单的正则表达式以使用<xref:System.Windows.Forms.MaskedTextBox>控件。  
  
## <a name="description-of-the-masking-language"></a>掩蔽语言的描述  
 标准<xref:System.Windows.Forms.MaskedTextBox>掩蔽语言基于 Visual Basic 6.0`Masked Edit`中控件所使用的语言，并且对于从该平台迁移的用户应熟悉。  
  
 控件<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>的属性<xref:System.Windows.Forms.MaskedTextBox>指定要使用的输入掩码。 掩码必须是由下表中的一个或多个掩蔽元素组成的字符串。  
  
|遮蔽元素|说明|正则表达式元素|  
|---------------------|-----------------|--------------------------------|  
|0|0 和 9 之间的任何位数字。 需要输入。|\d|  
|9|数字或空格。 条目可选。|[d]？|  
|#|数字或空格。 条目可选。 如果此位置在蒙版中留空，则该位置将呈现为空格。 允许加上 （+） 和减 （-） 标志。|[d]-？|  
|L|ASCII 字母。 需要输入。|[a-zA-Z]|  
|?|ASCII 字母。 条目可选。|[a-zA-Z]？|  
|&|字符。 需要输入。|[p]ll_p_l_p_p_Lo_]|  
|C|字符。 条目可选。|[p]ll_p_l_p_l_p_Lo_？|  
|A|字母。 条目可选。|\W|  
|.|适合区域性的小数位符。|不可用。|  
|,|文化适当的数千个占位符。|不可用。|  
|:|适合区域性的时间分隔符。|不可用。|  
|/|适合区域性的日期分隔符。|不可用。|  
|$|文化适当的货币符号。|不可用。|  
|\<|将以下所有字符转换为小写。|不可用。|  
|>|将随后的所有字符转换为大写。|不可用。|  
|&#124;|撤消上一个移位或向下移动。|不可用。|  
|&#92;|转义蒙版字符，将其转换为文本。 ""\\\\是反斜杠的转义序列。|&#92;|  
|所有其他字符。|文字。 所有非掩码元素都将在 中<xref:System.Windows.Forms.MaskedTextBox>显示为自身。|所有其他字符。|  
  
 十进制 （.）、千分之一 （、时间（:)、日期 （/） 和货币 （$） 符号默认显示应用程序区域性定义的这些符号。 可以使用<xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>属性强制它们显示其他区域性的符号。  
  
## <a name="regular-expressions-and-masks"></a>正则表达式和蒙版  
 尽管可以使用正则表达式和蒙版来验证用户输入，但它们并不完全等效。 正则表达式可以表达比蒙版更复杂的模式，但蒙版可以更简洁地以与文化相关的格式表达相同的信息。  
  
 下表比较了四个正则表达式和每个表达式的等效掩码。  
  
|Regular Expression|Mask|说明|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|掩`/`码中的字符是逻辑日期分隔符，在用户看来，它将显示为适合应用程序当前区域性的日期分隔符。|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|以美国格式显示三个字母的月缩写的日期（天、月缩写和年份），其中以大写字母后跟两个小写字母显示。|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|美国电话号码，区号可选。 如果用户不希望输入可选字符，他们可以输入空格或将鼠标指针直接放在由前 0 表示的蒙版中的位置。|  
|`$\d{6}.00`|`$999,999.00`|0 到 999999 范围内的货币值。 货币、千分之和十进制字符将在运行时替换为特定于区域性的等效字符。|  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>
- <xref:System.Windows.Forms.MaskedTextBox>
- [验证字符串 (Visual Basic)](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)
- [MaskedTextBox 控件](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
