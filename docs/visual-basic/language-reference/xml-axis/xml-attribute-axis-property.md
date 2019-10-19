---
title: XML 特性轴属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyAttributeAxis
helpviewer_keywords:
- attribute axis property [Visual Basic]
- Visual Basic code, accessing XML
- XML attribute axis property [Visual Basic]
- XML axis [Visual Basic], attribute
- XML [Visual Basic], accessing
ms.assetid: 7a4777e1-0618-4de9-9510-fb9ace2bf4db
ms.openlocfilehash: 896081c3dc7ca9e50b4dc4bd87675e957c34b649
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582164"
---
# <a name="xml-attribute-axis-property-visual-basic"></a>XML 特性轴属性 (Visual Basic)
提供对 <xref:System.Xml.Linq.XElement> 对象的特性值或 <xref:System.Xml.Linq.XElement> 对象集合中第一个元素的访问。  
  
## <a name="syntax"></a>语法  
  
```vb  
object.@attribute  
' -or-  
object.@<attribute>  
```  
  
## <a name="parts"></a>部件  
 `object`  
 必须的。 一个 <xref:System.Xml.Linq.XElement> 对象或 <xref:System.Xml.Linq.XElement> 对象的集合。  
  
 .@  
 必须的。 表示属性轴属性的开头。  
  
 <  
 可选。 如果 `attribute` 在 Visual Basic 中不是有效的标识符，则表示属性名称的开头。  
  
 `attribute`  
 必须的。 要访问的属性的名称，格式为 [`prefix`：] `name`。  
  
|部件|描述|  
|----------|-----------------|  
|`prefix`|可选。 特性的 XML 命名空间前缀。 必须是使用 `Imports` 语句定义的全局 XML 命名空间。|  
|`name`|必须的。 本地属性名称。 请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。|  
  
 \>  
 可选。 如果 `attribute` 在 Visual Basic 中不是有效的标识符，则表示属性名称的末尾。  
  
## <a name="return-value"></a>返回值  
 一个字符串，其中包含 `attribute` 的值。 如果属性名不存在，则返回 `Nothing`。  
  
## <a name="remarks"></a>备注  
 您可以使用 XML 特性轴属性，按名称从 <xref:System.Xml.Linq.XElement> 对象或从 <xref:System.Xml.Linq.XElement> 对象集合中的第一个元素访问属性值。 可以按名称检索属性值，也可以通过指定一个新名称（前面带有 @ 标识符）来向元素添加一个新的属性。  
  
 当使用 @ 标识符引用 XML 特性时，属性值将以字符串的形式返回，无需显式指定 <xref:System.Xml.Linq.XAttribute.Value%2A> 属性。  
  
 XML 特性的命名规则不同于 Visual Basic 标识符的命名规则。 若要访问名称不是有效 Visual Basic 标识符的 XML 特性，请将该名称括在尖括号（\< 和 >）中。  
  
## <a name="xml-namespaces"></a>XML 命名空间  
 特性轴属性中的名称只能使用 `Imports` 语句全局声明的 XML 命名空间前缀。 它不能使用在 XML 元素文本中局部声明的 XML 命名空间前缀。 有关详细信息，请参阅[Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何从名为 `phone` 的 XML 元素集合中获取名为 `type` 的 XML 特性的值。  
  
 [!code-vb[VbXMLSamples#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#12)]  
  
 此代码显示以下文本：  
  
 `<phoneTypes>`  
  
 `<type>home</type>`  
  
 `<type>work</type>`  
  
 `</phoneTypes>`  
  
## <a name="example"></a>示例  
 下面的示例演示如何在 XML 中以声明方式同时创建 XML 元素的特性，并通过将特性添加到 <xref:System.Xml.Linq.XElement> 对象的实例来动态创建属性。 @No__t_0 属性以声明方式创建，并动态创建 `owner` 属性。  
  
 [!code-vb[VbXMLSamples#44](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#44)]  
  
 此代码显示以下文本：  
  
```xml  
<phone type="home" owner="Harris, Phyllis">206-555-0144</phone>  
```  
  
## <a name="example"></a>示例  
 下面的示例使用尖括号语法来获取名为 `number-type` 的 XML 属性的值，该属性不是 Visual Basic 中的有效标识符。  
  
 [!code-vb[VbXMLSamples#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples5.vb#13)]  
  
 此代码显示以下文本：  
  
 `Phone type: work`  
  
## <a name="example"></a>示例  
 下面的示例声明 `ns` 作为 XML 命名空间前缀。 然后，它使用命名空间的前缀创建 XML 文本，并访问具有限定名 "`ns:name`" 的第一个子节点。  
  
 [!code-vb[VbXMLSamples#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples6.vb#14)]  
  
 此代码显示以下文本：  
  
 `Phone type: home`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.Linq.XElement>
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
