---
title: "XML 值属性 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionValue
helpviewer_keywords:
- Value property [Visual Basic]
- Visual Basic code, accessing XML
- XML axis [Visual Basic], Value
- XML Value property [Visual Basic]
ms.assetid: 7ddd057a-a195-4e9b-ad8b-2ee0e615a20f
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d9294c2d1d83dce3bca2abc22ee9c70296fc8014
ms.sourcegitcommit: 8ed4ebc15b5ef89d06a7507dc9d5e306e30accf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2017
---
# <a name="xml-value-property-visual-basic"></a>XML 值属性 (Visual Basic)
提供对的集合的第一个元素的值的访问<xref:System.Xml.Linq.XElement>对象。  
  
## <a name="syntax"></a>语法  
  
```  
object.Value  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`object`|必需。 <xref:System.Xml.Linq.XElement> 对象的集合。|  
  
## <a name="return-value"></a>返回值  
 A`String`包含值的集合，第一个元素或`Nothing`如果该集合为空。  
  
## <a name="remarks"></a>备注  
 <xref:System.Xml.Linq.XElement.Value%2A>属性，则可以轻松访问的集合中的第一个元素的值<xref:System.Xml.Linq.XElement>对象。 此属性首先检查集合是否包含至少一个对象。 如果该集合为空，则此属性返回`Nothing`。 否则，此属性返回的值<xref:System.Xml.Linq.XElement.Value%2A>集合中的第一个元素的属性。  
  
> [!NOTE]
>  当你访问的 XML 属性使用值 @ 标识符，则返回属性值为`String`并且不需要显式指定<xref:System.Xml.Linq.XAttribute.Value%2A>属性。  
  
 若要访问集合中的其他元素，可以使用 XML 扩展索引器属性。 有关详细信息，请参阅[扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)。  
  
## <a name="inheritance"></a>继承  
 大多数用户不需要实现<xref:System.Collections.Generic.IEnumerable%601>，因此可以忽略此部分。  
  
 <xref:System.Xml.Linq.XElement.Value%2A>属性是实现的类型的扩展属性`IEnumerable(Of XElement)`。 此扩展属性的绑定就像绑定的扩展方法是： 如果某个类型实现的接口之一，定义具有名称"Value"的属性，该属性的优先级高于扩展属性。 换而言之，这<xref:System.Xml.Linq.XElement.Value%2A>可以通过定义新属性的类中实现重写属性`IEnumerable(Of XElement)`。  
  
## <a name="example"></a>示例  
 下面的示例演示如何使用<xref:System.Xml.Linq.XElement.Value%2A>属性来访问的集合中的第一个节点<xref:System.Xml.Linq.XElement>对象。 该示例使用子轴属性来获取名为的所有子节点集合`phone`中`contact`对象。  
  
 [!code-vb[VbXMLSamples#15](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_1.vb)]  
  
 此代码显示以下文本：  
  
 `Phone number: 206-555-0144`  
  
## <a name="example"></a>示例  
 下面的示例演示如何从集合中获取 XML 属性的值<xref:System.Xml.Linq.XAttribute>对象。 该示例使用特性轴属性来显示的值`type`的所有属性`phone`元素。  
  
 [!code-vb[VbXMLSamples#16](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-value-property_2.vb)]  
  
 此代码显示以下文本：  
  
 `home`  
  
 `work`  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.Linq.XElement>  
 <xref:System.Collections.Generic.IEnumerable%601>  
 [XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [扩展方法](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md)  
 [扩展索引器属性](../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)  
 [XML 子轴属性](../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [XML 特性轴属性](../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
