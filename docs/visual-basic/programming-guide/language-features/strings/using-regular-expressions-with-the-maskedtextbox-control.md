---
title: 在 MaskedTextBox 控件中使用正则表达式 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], regular expressions
- strings [Visual Basic], masked edit
ms.assetid: 2a048fb0-7053-487d-b2c5-ffa5e22ed6f9
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: c72542c05123ef62a8f95afbe1bb19cb823d1f21
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="using-regular-expressions-with-the-maskedtextbox-control-in-visual-basic"></a>在 MaskedTextBox 控件中使用正则表达式 (Visual Basic)
此示例演示如何将简单的正则表达式，用于转换<xref:System.Windows.Forms.MaskedTextBox>控件。  
  
## <a name="description-of-the-masking-language"></a>屏蔽语言的说明  
 标准<xref:System.Windows.Forms.MaskedTextBox>屏蔽语言取决于使用的那个`Masked Edit`控制在 Visual Basic 6.0 中，并且应该为从该平台迁移的用户所熟悉。  
  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性<xref:System.Windows.Forms.MaskedTextBox>控件指定要使用哪些输入的掩码。 掩码必须是组成一个或多个以下表格中的屏蔽元素的字符串。  
  
|屏蔽元素|描述|正则表达式元素|  
|---------------------|-----------------|--------------------------------|  
|0|0 到 9 之间的任何单个数字。 所需的项。|\d|  
|9|数字或空格。 可选的条目。|[\d]？|  
|#|数字或空格。 可选的条目。 如果此位置为空掩码中，它将呈现为一个空格。 加号 （+） 和减号 （-） 允许符号。|[\d+-]？|  
|L|ASCII 字母。 所需的项。|[-zA-A-z]|  
|?|ASCII 字母。 可选的条目。|[-zA-A-z]？|  
|&|字符。 所需的项。|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]|  
|C|字符。 可选的条目。|[\p{Ll}\p{Lu}\p{Lt}\p{Lm}\p{Lo}]？|  
|包含当前请求的 URL 的|字母数字。 可选的条目。|\W|  
|.|相应于区域性的小数点占位符。|不可用。|  
|,|相应数千于区域性的占位符。|不可用。|  
|:|相应于区域性的时间分隔符。|不可用。|  
|/|相应于区域性的日期分隔符。|不可用。|  
|$|相应于区域性的货币符号。|不可用。|  
|\<|将转换为小写后面的所有字符。|不可用。|  
|>|将转换为大写后面的所有字符。|不可用。|  
|&#124;|撤消上一个 shift 向上或向下移动。|不可用。|  
|\|掩码字符，将其转换为原义进行转义。 "\\\\"是反斜杠的转义序列。|\|  
|所有其他字符。|文本。 所有非掩码元素将显示为本身内<xref:System.Windows.Forms.MaskedTextBox>。|所有其他字符。|  
  
 小数点 （.）、 分之几 （，）、 时间 （:）、 日期 （/），而货币 （$） 符号默认为由应用程序的区域性定义时，显示这些符号中。 你可以强制使用显示的另一个区域性符号<xref:System.Windows.Forms.MaskedTextBox.FormatProvider%2A>属性。  
  
## <a name="regular-expressions-and-masks"></a>正则表达式和蒙板  
 你可以使用正则表达式和掩码验证用户输入，但它们并不完全相同。 正则表达式可以表示更复杂的模式，比掩码，但更简洁地采用与区域相关的格式，掩码可以表示相同的信息。  
  
 下表比较了每个四个正则表达式和等效的掩码。  
  
|正则表达式|掩码|说明|  
|------------------------|----------|-----------|  
|`\d{2}/\d{2}/\d{4}`|`00/00/0000`|`/`掩码中的字符是一个逻辑日期分隔符，和它将向用户显示为适合于应用程序的当前区域性的日期分隔符。|  
|`\d{2}-[A-Z][a-z]{2}-\d{4}`|`00->L<LL-0000`|三个字母月份缩写的显示带有两个小写字母后跟一个初始大写字母的美国格式的日期 （日、 月份缩写和年）。|  
|`(\(\d{3}\)-)?\d{3}-d{4}`|`(999)-000-0000`|美国境内电话号码，可选的区域代码。 如果用户不希望输入的可选字符，她可以输入空间，或将鼠标指针放在由第一个 0 表示掩码中的位置直接。|  
|`$\d{6}.00`|`$999,999.00`|0 到 999999 的范围中的货币值。 货币、 千位和十进制字符将替换为在运行时它们特定于区域性的等效项。|  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Forms.MaskedTextBox.Mask%2A>  
 <xref:System.Windows.Forms.MaskedTextBox>  
 [在 Visual Basic 中验证字符串](../../../../visual-basic/programming-guide/language-features/strings/validating-strings.md)  
 [MaskedTextBox 控件](../../../../framework/winforms/controls/maskedtextbox-control-windows-forms.md)
