---
title: XML 中的嵌入式表达式 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlEmbeddedExpression
helpviewer_keywords:
- embedded expressions [Visual Basic]
- LINQ to XML [Visual Basic], embedded expressions
- XML literals [Visual Basic], embedded expressions
ms.assetid: bf2eb779-b751-4b7c-854f-9f2161482352
ms.openlocfilehash: 525fa04db86a299d88e1612aac76d014f35124eb
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69922622"
---
# <a name="embedded-expressions-in-xml-visual-basic"></a>XML 中的嵌入式表达式 (Visual Basic)
使用嵌入式表达式可以创建包含在运行时计算的表达式的 XML 文本。 嵌入式表达式的语法是`<%=` `expression` `%>`, 这与 ASP.NET 中使用的语法相同。  
  
 例如, 可以创建 XML 元素文本, 并将嵌入式表达式与文本内容组合在一起。  
  
 [!code-vb[VbXMLSamples#27](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#27)]  
  
 如果`isbnNumber`包含整数 12345, 并且`modifiedDate`包含日期 3/5/2006, 则在此代码`book`执行时, 的值为:  
  
```xml  
<book category="fiction" isbn="12345">  
  <modifiedDate>3/5/2006</modifiedDate>  
</book>  
```  
  
## <a name="embedded-expression-location-and-validation"></a>嵌入式表达式位置和验证  
 嵌入式表达式只能出现在 XML 文本表达式中的某些位置。 表达式位置控制表达式可以返回的类型以及处理方式`Nothing` 。 下表描述了嵌入表达式的允许位置和类型。  
  
|文本中的位置|表达式的类型|处理`Nothing`|  
|---|---|---|  
|XML 元素名称|<xref:System.Xml.Linq.XName>|Error|  
|XML 元素内容|`Object`或数组`Object`|忽略|  
|XML 元素特性名称|<xref:System.Xml.Linq.XName>|错误, 除非该属性值也为`Nothing`|  
|XML 元素特性值|`Object`|忽略属性声明|  
|XML 元素特性|<xref:System.Xml.Linq.XAttribute>或的集合<xref:System.Xml.Linq.XAttribute>|忽略|  
|XML 文档根元素|<xref:System.Xml.Linq.XElement>或一个<xref:System.Xml.Linq.XElement>对象的集合, 以及任意数量的<xref:System.Xml.Linq.XProcessingInstruction>和<xref:System.Xml.Linq.XComment>对象|忽略|  
  
- XML 元素名称中的嵌入表达式的示例:  
  
     [!code-vb[VbXMLSamples#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#32)]  
  
- XML 元素内容中的嵌入表达式的示例:  
  
     [!code-vb[VbXMLSamples#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#33)]  
  
- XML 元素属性名称中的嵌入式表达式的示例:  
  
     [!code-vb[VbXMLSamples#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#34)]  
  
- XML 元素特性值中的嵌入式表达式的示例:  
  
     [!code-vb[VbXMLSamples#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#35)]  
  
- XML 元素特性中的嵌入式表达式的示例:  
  
     [!code-vb[VbXMLSamples#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#36)]  
  
- XML 文档根元素中的嵌入式表达式的示例:  
  
     [!code-vb[VbXMLSamples#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#37)]  
  
 如果启用`Option Strict`, 编译器会检查每个嵌入式表达式的类型是否扩大到了所需的类型。 唯一的例外是在代码运行时验证的 XML 文档的根元素。 如果在不进行`Option Strict`编译的情况下进行编译, `Object`则可以嵌入类型的表达式, 并在运行时验证其类型。  
  
 在内容可选的位置中, 将忽略包含`Nothing`的嵌入表达式。 这意味着, 在使用 XML 文本`Nothing`之前, 无需检查元素内容、特性值和数组元素。 必需的值 (如元素和属性名称) 不能`Nothing`为。  
  
 有关使用特定类型文本中的嵌入表达式的详细信息, 请参阅[Xml 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)和[xml 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)。  
  
## <a name="scoping-rules"></a>作用域规则  
 编译器将每个 XML 文本转换为相应文本类型的构造函数调用。 XML 文本中的文本内容和嵌入式表达式作为参数传递给构造函数。 这意味着, XML 文本可用的所有 Visual Basic 编程元素也可用于其嵌入式表达式。  
  
 在 xml 文本中, 可以访问用`Imports`语句声明的 xml 命名空间前缀。 您可以使用`xmlns`属性在元素中声明新的 xml 命名空间前缀或隐藏现有的 xml 命名空间前缀。 新命名空间可用于该元素的子节点, 但不适用于嵌入的表达式中的 XML 文本。  
  
> [!NOTE]
> 使用`xmlns` namespace 特性声明 XML 命名空间前缀时, 属性值必须是常量字符串。 在这方面, 使用`xmlns`属性的方式类似于`Imports`使用语句声明 XML 命名空间。 不能使用嵌入的表达式来指定 XML 命名空间值。  
  
## <a name="see-also"></a>请参阅

- [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 文档文本](../../../../visual-basic/language-reference/xml-literals/xml-document-literal.md)
- [XML 元素文本](../../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [Option Strict 语句](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Imports 语句（.NET 命名空间和类型）](../../../../visual-basic/language-reference/statements/imports-statement-net-namespace-and-type.md)
- [XML 文本概述](../../../../visual-basic/programming-guide/language-features/xml/xml-literals-overview.md)
