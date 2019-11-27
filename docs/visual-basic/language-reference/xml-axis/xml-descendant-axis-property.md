---
title: XML Descendant Axis Property
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyDescendantsAxis
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML descendant axis property [Visual Basic]
- descendant axis property [Visual Basic]
- XML axis [Visual Basic], descendant
- XML [Visual Basic], accessing
ms.assetid: a178f85b-5d54-438f-8479-40b62af6fe76
ms.openlocfilehash: b2bf524214fa8ecca215d50c198b23d127e3b400
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349449"
---
# <a name="xml-descendant-axis-property-visual-basic"></a>XML 后代轴属性 (Visual Basic)

提供对以下各项的后代的访问：一个 <xref:System.Xml.Linq.XElement> 对象、一个 <xref:System.Xml.Linq.XDocument> 对象、一个 <xref:System.Xml.Linq.XElement> 对象的集合或 <xref:System.Xml.Linq.XDocument> 对象的集合。

## <a name="syntax"></a>语法

```vb
object...<descendant>
```

## <a name="parts"></a>部件

`object`（必需）。 <xref:System.Xml.Linq.XElement> 对象、<xref:System.Xml.Linq.XDocument> 对象、<xref:System.Xml.Linq.XElement> 对象的集合或 <xref:System.Xml.Linq.XDocument> 对象的集合。

`...<`（必需）。 表示子代轴属性的开头。

`descendant`（必需）。 要访问的子代节点的名称，格式为 [`prefix:]name`。

|部件|说明|
|----------|-----------------|
|`prefix`|可选。 子代节点的 XML 命名空间前缀。 必须是使用 `Imports` 语句定义的全局 XML 命名空间。|
|`name`|必需。 子代节点的本地名称。 请参阅已[声明的 XML 元素和属性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)。|

`>`（必需）。 表示子代轴属性的结尾。

## <a name="return-value"></a>返回值

<xref:System.Xml.Linq.XElement> 对象的集合。

## <a name="remarks"></a>备注

您可以使用 XML 子代轴属性，按名称从 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 对象或 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument> 对象的集合访问子代节点。 使用 XML `Value` 属性访问返回的集合中第一个子代节点的值。 有关详细信息，请参阅[XML Value 属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。

Visual Basic 编译器将子代轴属性转换为对 <xref:System.Xml.Linq.XContainer.Descendants%2A> 方法的调用。

## <a name="xml-namespaces"></a>XML 命名空间

子代轴属性中的名称只能使用 `Imports` 语句全局声明的 XML 命名空间。 它不能使用在 XML 元素文本中本地声明的 XML 命名空间。 有关详细信息，请参阅[Imports 语句（XML 命名空间）](../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)。

## <a name="example"></a>示例

下面的示例演示如何从 `contacts` 对象访问名为 `name` 的第一个子代节点的值以及名为 `phone` 的所有子代节点的值。

[!code-vb[VbXMLSamples#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#25)]

此代码显示以下文本：

`Name: Patrick Hines`

`Home Phone = 206-555-0144`

## <a name="example"></a>示例

下面的示例声明 `ns` 作为 XML 命名空间前缀。 然后，它使用命名空间的前缀创建 XML 文本，并访问具有限定名 `ns:name`的第一个子节点的值。

[!code-vb[VbXMLSamples#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples12.vb#26)]

此代码显示以下文本：

`Name: Patrick Hines`

## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XElement>
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [已声明的 XML 元素和特性的名称](../../../visual-basic/programming-guide/language-features/xml/names-of-declared-xml-elements-and-attributes.md)
