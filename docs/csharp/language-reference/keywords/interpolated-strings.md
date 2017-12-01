---
title: "内插字符串 (C#)"
ms.date: 10/18/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: "9"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a>内插字符串（C# 参考）

用于构造字符串。  内插字符串类似于包含内插表达式的模板字符串。  内插字符串返回的字符串可替换内插表达式并且包含其字符串表示形式。 此功能是在 C# 6 和更高版本中可用。

与[复合格式字符串](../../../standard/base-types/composite-formatting.md#composite-format-string)相比，内插字符串的参数更易于理解。  例如，内插字符串  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
包含两个相比内, 插的表达式，{name} 和 {小时： hh}。 等效复合格式字符串为：

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

内插字符串的结构为：  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

其中： 

- *field-width* 是一个带符号整数，表示字段中的字符数。 如果为正数，则字段右对齐；如果为负数，则左对齐。 

- “格式字符串”是适合正在设置格式的对象类型的格式字符串。 例如，对于 <xref:System.DateTime> 值，它可能是标准的日期和时间格式字符串，例如“D”或“d”。

> [!IMPORTANT]
> 不能具有之间的所有空白`$`和`"`开头的字符串。 这样做会导致编译时错误。

 可以在可使用字符串的任何位置使用内插字符串。  每次执行带内插字符串的代码时，都会计算内插字符串。 这有助于分隔内插字符串的定义和计算结果。  
  
 若要在内插字符串中包含大括号（“{”或“}”），请使用两个大括号，即“{{”或“}}”。  请参阅“隐式转换”部分以获取详细信息。  

如果内插字符串包含在内插字符串中具有特殊意义的其他字符，例如引号 (")、冒号 (:) 或逗号 (,)，则出现在文本中时应转义这些字符；如果它们是内插表达式中随附的语言元素，则应将其包括在由括号分隔的表达式内。 以下示例转义了引号以将其包括在结果字符串中，并使用括号来分隔表达式 `(age == 1 ? "" : "s")`，以防冒号被解读为格式字符串的开头。

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

按原义内插字符串使用`$`字符跟`@`字符。 有关原义字符串的详细信息，请参阅[字符串](string.md)主题。 下面的代码是使用原义相比内, 插的字符串的上一个代码段的修改的版本：

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

格式设置的更改是必需的因为不遵循原义字符串`\`转义序列。

> [!IMPORTANT]
> `$`令牌必须之前出现`@`令牌原义相比内, 插字符串中。


## <a name="implicit-conversions"></a>隐式转换  

内插字符串有 3 种隐式类型转换：  

1. 将内插字符串转换为 <xref:System.String>。 下例返回一个字符串，其内插字符串表达式已替换为字符串表示形式。 例如: 

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   这是字符串解释的最终结果。 出现的所有双大括号（“{{”和“}}”）都转换为单大括号。 

2. 将内插字符串转换为 <xref:System.IFormattable> 变量，使用此变量可通过单个 <xref:System.IFormattable> 实例创建多个包含区域性特定内容的结果字符串。 对于包括诸如各区域性的正确数字和日期格式之类的内容，这种转换很有用。  出现的所有双大括号（“{{”和“}}”）仍保留为双大括号，直至通过显式或隐式调用 <xref:System.Object.ToString> 方法格式化字符串。  包含的所有内插表达式都转换为 {0}、{1} 等等。  

   以下示例使用反射来显示内插字符串中所创建的 <xref:System.IFormattable> 变量的成员以及字段和属性值。 它还将传递<xref:System.IFormattable>变量<xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType>方法。

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   请注意，只能通过使用反射来检查内插字符串。 如果它将传递到格式设置方法，如字符串<xref:System.Console.WriteLine(System.String)>，其格式项已解决并且返回的结果字符串。 

3. 将内插字符串转换为表示复合格式字符串的 <xref:System.FormattableString> 变量。 例如，检查复合格式字符串及其呈现为结果字符串的方式可能有助于在生成查询时防止注入攻击。 <xref:System.FormattableString> 还包括 <xref:System.FormattableString.ToString> 重载，可为 <xref:System.Globalization.CultureInfo.InvariantCulture> 和 <xref:System.Globalization.CultureInfo.CurrentCulture> 生成结果字符串。  出现的所有双大括号（“{{”和“}}”）都保留为双大括号，直至格式化。  包含的所有内插表达式都转换为 {0}、{1} 等等。  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a>语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)
