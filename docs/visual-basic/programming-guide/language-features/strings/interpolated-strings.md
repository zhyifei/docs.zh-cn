---
title: "内插的字符串 (Visual Basic)"
ms.date: 10/31/2017
ms.prod: .net
ms.technology: devlang-visual-basic
ms.topic: article
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f865d5a7167847bf869d70a39570413dac271a2c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-visual-basic-reference"></a>内插的字符串 （Visual Basic 参考）

用于构造字符串。  内插字符串类似于包含内插表达式的模板字符串。  内插字符串返回的字符串可替换内插表达式并且包含其字符串表示形式。 此功能是在 Visual Basic 14 和更高版本中可用。

与[复合格式字符串](../../../../standard/base-types/composite-formatting.md#composite-format-string)相比，内插字符串的参数更易于理解。  例如，内插字符串  
  
```vb  
Console.WriteLine($"Name = {name}, hours = {hours:hh}")
```  
包含 2 个内插表达式：“{name}”和“{hours:hh}”。 等效复合格式字符串为：

```vb
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

内插字符串的结构为：  
  
```vb  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

其中： 

- *field-width* 是一个带符号整数，表示字段中的字符数。 如果为正数，则字段右对齐；如果为负数，则左对齐。 

- “格式字符串”是适合正在设置格式的对象类型的格式字符串。 例如，对于<xref:System.DateTime>值，它可以是[标准日期和时间格式字符串](~/docs/standard/base-types/standard-date-and-time-format-strings.md)如"D"或"d"。

> [!IMPORTANT]
> 该字符串开头的`$`和`"`之间不能有任何空白，否则会导致编译时错误。 这样做会导致编译器错误。

 可以在可使用字符串的任何位置使用内插字符串。  每次执行带内插字符串的代码时，都会计算内插字符串。 这有助于分隔内插字符串的定义和计算结果。  
  
 若要在内插字符串中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。  请参阅“隐式转换”部分以获取详细信息。  

如果内插字符串包含在内插字符串中具有特殊意义的其他字符，例如引号 (")、冒号 (:) 或逗号 (,)，则出现在文本中时应转义这些字符；如果它们是内插表达式中随附的语言元素，则应将其包括在由括号分隔的表达式内。 以下示例转义了引号以将其包括在结果字符串中，并使用括号来分隔表达式 `(age == 1 ? "" : "s")`，以防冒号被解读为格式字符串的开头。

[!code-vb[interpolated-strings](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings4.vb)]  

## <a name="implicit-conversions"></a>隐式转换  

内插字符串有 3 种隐式类型转换：  

1. 将内插字符串转换为 <xref:System.String>。 下例返回一个字符串，其内插字符串表达式已替换为字符串表示形式。 例如: 

   [!code-vb[interpolated-strings1](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings1.vb)]  

   这是字符串解释的最终结果。 出现的所有双大括号（“{{”和“}}”）都转换为单大括号。 

2. 将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。 对于包括诸如各区域性的正确数字和日期格式之类的内容，这种转换很有用。  出现的所有双大括号（“{{”和“}}”）仍保留为双大括号，直至通过显式或隐式调用 <xref:System.Object.ToString> 方法格式化字符串。  包含的所有内插表达式都转换为 {0}、{1} 等等。  

   以下示例使用反射来显示内插字符串中所创建的 <xref:System.IFormattable> 变量的成员以及字段和属性值。 它还将传递<xref:System.IFormattable>变量<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>方法。

   [!code-vb[interpolated-strings2](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings2.vb)]  

   请注意，只能通过使用反射来检查内插字符串。 如果它将传递到格式设置方法，如字符串<xref:System.Console.WriteLine(System.String)>，其格式项已解决并且返回的结果字符串。 

3. 转换到相比内, 插字符串的<xref:System.FormattableString>表示复合格式字符串的变量。 例如，检查复合格式字符串及其呈现为结果字符串的方式可能有助于在生成查询时防止注入攻击。 A<xref:System.FormattableString>还包括：

      - A<xref:System.FormattableString.ToString>产生的结果字符串的重载<xref:System.Globalization.CultureInfo.CurrentCulture>。
      
      - A<xref:System.FormattableString.Invariant%2A>要求方法能够生成的字符串<xref:System.Globalization.CultureInfo.InvariantCulture>。
      
      - A<xref:System.FormattableString.ToString(System.IFormatProvider)>产生指定的区域性的结果字符串的方法。 
  
    将出现所有双大括号 ("{{"和"}}") 设置格式之前保持为双大括号。  包含的所有内插表达式都转换为 {0}、{1} 等等。  

   [!code-vb[interpolated-strings3](../../../../../samples/snippets/visualbasic/programming-guide/language-features/strings/interpolated-strings3.vb)]  

## <a name="see-also"></a>另请参阅  
f<xref:System.IFormattable?displayProperty=nameWithType>   
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [Visual Basic 语言参考](index.md)  
 