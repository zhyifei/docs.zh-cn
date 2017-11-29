---
title: "区域性对字符串的影响 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- locale [Visual Basic], effect on strings
- strings [Visual Basic], locale dependence
ms.assetid: c4664444-ee0d-47bf-bef1-eaa3c54bdd7f
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b61f008edc446445fd5873b6138b64f29e0b8b8c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-culture-affects-strings-in-visual-basic"></a>区域性对字符串的影响 (Visual Basic)
此帮助页讨论如何[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]使用区域性信息来执行的字符串转换和比较。  
  
## <a name="when-to-use-culture-specific-strings"></a>何时使用特定于区域性的字符串  
 通常情况下，你应到显示的所有数据使用特定于区域性的字符串，读取用户，并将应用程序的内部数据区域性固定的字符串。  
  
 例如，如果你的应用程序要求用户输入日期作为一个字符串，它应指望用户能以根据其区域性中，字符串的格式和应用程序应适当地转换字符串。 如果你的应用程序然后显示其用户界面中的相应日期，它应将其呈现在用户的区域性。  
  
 但是，如果应用程序将日期上载到中央服务器，它应格式化根据某个特定区域性，以防止可能不同的日期格式之间产生混淆的字符串。  
  
## <a name="culture-sensitive-functions"></a>区分区域性的函数  
 所有[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]字符串转换函数 (除`Str`和`Val`函数) 使用应用程序的区域性信息以确保转换和比较适合于的区域性应用程序的用户。  
  
 已成功在具有不同的区域性设置的计算机运行的应用程序中使用字符串转换函数的关键是了解哪些功能使用特定区域性设置，以及它使用当前区域性设置。 请注意，应用程序的区域性设置，默认情况下，从继承的操作系统的区域性设置。 有关详细信息，请参阅<xref:Microsoft.VisualBasic.Strings.Asc%2A>， <xref:Microsoft.VisualBasic.Strings.AscW%2A>， <xref:Microsoft.VisualBasic.Strings.Chr%2A>， <xref:Microsoft.VisualBasic.Strings.ChrW%2A>， <xref:Microsoft.VisualBasic.Strings.Format%2A>， <xref:Microsoft.VisualBasic.Conversion.Hex%2A>， <xref:Microsoft.VisualBasic.Conversion.Oct%2A>，和[类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)。  
  
 `Str` （将数字转换为字符串） 和`Val`（将字符串转换为数字） 函数字符串和数字之间进行转换时不使用应用程序的区域性信息。 相反，它们将只将句点 （.） 识别为有效的小数点分隔符。 这些函数的已经过区域性感知的类似物是：  
  
-   **使用当前区域性的转换。** `CStr`和`Format`函数将数字转换为字符串，与`CDbl`和`CInt`函数将字符串转换为数字。  
  
-   **使用特定区域性的转换。** 每个数字的对象都有`ToString(IFormatProvider)`将数字转换为字符串，方法和一个`Parse(String, IFormatProvider)`方法将字符串转换为数字。 例如，`Double`类型提供了<xref:System.Double.ToString%28System.IFormatProvider%29>和<xref:System.Double.Parse%28System.String%2CSystem.IFormatProvider%29>方法。  
  
 有关详细信息，请参阅 <xref:Microsoft.VisualBasic.Conversion.Str%2A> 和 <xref:Microsoft.VisualBasic.Conversion.Val%2A>。  
  
## <a name="using-a-specific-culture"></a>使用非特定区域性  
 假设你正在开发的应用程序向 Web 服务发送 （作为字符串设置格式） 的日期。 在这种情况下，你的应用程序必须使用特定区域性的字符串转换。 若要说明原因，请考虑使用的日期的结果<xref:System.DateTime.ToString>方法： 如果你的应用程序使用该方法来设置格式的日期 2005 年 7 月 4 日，它将返回"2005 年 7 月 4 日 12:00:00 AM"与美国英语 (EN-US) 区域性中，运行时，但它将返回"04.07.2005 00:00:00"与德语 (de DE) 区域性运行时。  
  
 如果你需要执行的特定区域性格式的字符串转换，则应使用`CultureInfo`内置于的类[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]。 你可以创建一个新`CultureInfo`对象的区域性将名称传递给由特定区域性<xref:System.Globalization.CultureInfo.%23ctor%2A>构造函数。 中列出了支持的语言名称<xref:System.Globalization.CultureInfo>类帮助页。  
  
 或者，你可以获取其实例*固定区域性*从<xref:System.Globalization.CultureInfo.InvariantCulture%2A?displayProperty=nameWithType>属性。 固定区域性基于英语区域性中，但有一些差异。 例如，固定区域性指定而不是以 12 小时时钟制采用 24 小时制。  
  
 若要将日期转换为区域性的字符串，将传递<xref:System.Globalization.CultureInfo>对象与日期对象<xref:System.DateTime.ToString%28System.IFormatProvider%29>方法。 例如，下面的代码显示"07/04/2005年 00:00:00"，而不管应用程序的区域性设置。  
  
 [!code-vb[VbVbalrConcepts#1](../../../../visual-basic/programming-guide/language-features/operators-and-expressions/codesnippet/VisualBasic/how-culture-affects-strings_1.vb)]  
  
> [!NOTE]
>  根据英语区域性始终解释日期文本。  
  
## <a name="comparing-strings"></a>比较字符串  
 有两个重要的情况下在需要字符串比较：  
  
-   **向用户显示的数据进行排序。** 使用基于当前区域性，因此字符串正确排序的操作。  
  
-   **正在确定是否两个应用程序内部字符串完全匹配 （通常出于安全考虑）。** 使用忽略当前区域性的操作。  
  
 你可以执行这两种类型的比较与[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]<xref:Microsoft.VisualBasic.Strings.StrComp%2A>函数。 指定可选`Compare`参数控制比较的类型：`Text`对于大多数输入和输出`Binary`用于确定完全匹配。  
  
 `StrComp`函数返回一个整数，指示基于排序顺序比较两个字符串之间的关系。 结果为正值指示第一个字符串大于第二个字符串。 负数的结果指示第一个字符串较小，而零表示在字符串之间的相等性。  
  
 [!code-vb[VbVbalrStrings#22](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_2.vb)]  
  
 你还可以使用[!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)]合作伙伴`StrComp`函数，<xref:System.String.Compare%2A?displayProperty=nameWithType>方法。 这是基础字符串类的静态，重载方法。 下面的示例演示如何使用此方法：  
  
 [!code-vb[VbVbalrStrings#48](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/how-culture-affects-strings_3.vb)]  
  
 更好地控制如何执行比较，你可以使用的其他重载<xref:System.String.Compare%2A>方法。 与<xref:System.String.Compare%2A?displayProperty=nameWithType>方法，你可以使用`comparisonType`自变量以指定要使用的比较的类型。  
  
|值，则为`comparisonType`自变量|比较类型|何时使用|  
|---|---|---|  
|`Ordinal`|基于字符串的组成部分字节数进行比较。|比较时使用此值： 区分大小写标识符、 与安全相关的设置或其他非语言标识符字节必须完全匹配。|  
|`OrdinalIgnoreCase`|基于字符串的组成部分字节数进行比较。<br /><br /> `OrdinalIgnoreCase`使用固定区域性信息来确定何时仅在大小写不同的两个字符。|比较时使用此值： 不区分大小写的标识符、 与安全相关的设置和在 Windows 中存储的数据。|  
|`CurrentCulture` 或 `CurrentCultureIgnoreCase`|比较基于当前区域性中的字符串的解释。|比较时使用这些值： 向用户、 大多数用户输入和其他需要语言解释的数据显示的数据。|  
|`InvariantCulture` 或 `InvariantCultureIgnoreCase`|基于字符串的解释在固定区域性的比较。<br /><br /> 此函数不同于`Ordinal`和`OrdinalIgnoreCase`，因为固定区域性将超出其可接受范围内的字符视为等效的固定字符。|仅当比较持久保存数据或显示与语言相关的数据时需要固定的排序顺序，请使用这些值。|  
  
### <a name="security-considerations"></a>安全注意事项  
 如果你的应用程序进行安全决策基于比较或大小写更改操作的结果，则该操作，应使用<xref:System.String.Compare%2A?displayProperty=nameWithType>方法，并传入`Ordinal`或`OrdinalIgnoreCase`为`comparisonType`自变量。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Globalization.CultureInfo>  
 [Visual Basic 中的字符串简介](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [类型转换函数](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
