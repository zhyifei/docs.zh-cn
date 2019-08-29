---
title: XML 值属性 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
ms.openlocfilehash: 9edf95c7cedced55ab2441baf51b7c2052e4654c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69942977"
---
# <a name="xml-value-property-visual-basic"></a>XML 值属性 (Visual Basic)
提供对<xref:System.Xml.Linq.XElement>对象集合中第一个元素的值的访问。  
  
## <a name="syntax"></a>语法  
  
```  
object.Value  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`object`|必需。 <xref:System.Xml.Linq.XElement> 对象的集合。|  
  
## <a name="return-value"></a>返回值  
 一个`String` , 它包含集合`Nothing`中第一个元素的值; 如果集合为空, 则为。  
  
## <a name="remarks"></a>备注  
 使用<xref:System.Xml.Linq.XElement.Value%2A>属性可以轻松访问<xref:System.Xml.Linq.XElement>对象集合中第一个元素的值。 此属性首先检查集合是否包含至少一个对象。 如果集合为空, 则此属性返回`Nothing`。 否则, 此属性将返回集合中第<xref:System.Xml.Linq.XElement.Value%2A>一个元素的属性的值。  
  
> [!NOTE]
> 使用 "\@" 标识符访问 XML 特性的值时, 特性值`String`作为返回, 无<xref:System.Xml.Linq.XAttribute.Value%2A>需显式指定属性。  
  
 若要访问集合中的其他元素, 可以使用 XML 扩展索引器属性。 有关详细信息, 请参阅[扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)。  
  
## <a name="inheritance"></a>继承  
 大多数用户将不必实现<xref:System.Collections.Generic.IEnumerable%601>, 因此可以忽略此部分。  
  
 属性是实现`IEnumerable(Of XElement)`的类型的扩展属性。 <xref:System.Xml.Linq.XElement.Value%2A> 此扩展属性的绑定类似于扩展方法的绑定: 如果某个类型实现了一个接口, 并定义了一个名称为 "Value" 的属性, 则该属性的优先级高于扩展属性。 换言之, 可以通过在<xref:System.Xml.Linq.XElement.Value%2A>实现`IEnumerable(Of XElement)`的类中定义一个新属性来重写此属性。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用<xref:System.Xml.Linq.XElement.Value%2A>属性访问<xref:System.Xml.Linq.XElement>对象集合中的第一个节点。 该示例使用子轴属性来获取`phone` `contact`对象中名为的所有子节点的集合。  
  
 [!code-vb[VbXMLSamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#15)]  
  
 此代码显示以下文本：  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>示例  
 下面的示例演示如何从<xref:System.Xml.Linq.XAttribute>对象的集合中获取 XML 特性的值。 该示例使用 "属性轴" 属性显示所有`type` `phone`元素的属性值。  
  
 [!code-vb[VbXMLSamples#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples7.vb#16)]  
  
 此代码显示以下文本：  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.Linq.XElement>
- <xref:System.Collections.Generic.IEnumerable%601>
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)
- [扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)
- [XML 子轴属性](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML 特性轴属性](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
