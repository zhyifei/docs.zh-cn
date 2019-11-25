---
title: 扩展索引器属性
ms.date: 07/20/2015
f1_keywords:
- vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
ms.openlocfilehash: 5f91dc8a6b1a0d82daa4891cf826c16e2716839f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352697"
---
# <a name="extension-indexer-property-visual-basic"></a>扩展索引器属性 (Visual Basic)
提供对集合中各个元素的访问。  
  
## <a name="syntax"></a>语法  
  
```vb  
object(index)  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`object`|必须的。 A queryable collection. That is, a collection that implements <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>.|  
|(|必须的。 Denotes the start of the indexer property.|  
|`index`|必须的。 An integer expression that specifies the zero-based position of an element of the collection.|  
|)|必须的。 Denotes the end of the indexer property.|  
  
## <a name="return-value"></a>返回值  
 The object from the specified location in the collection, or `Nothing` if the index is out of range.  
  
## <a name="remarks"></a>备注  
 You can use the extension indexer property to access individual elements in a collection. This indexer property is typically used on the output of XML axis properties. The XML child and XML descendent axis properties return collections of <xref:System.Xml.Linq.XElement> objects or an attribute value.  
  
 The Visual Basic compiler converts extension indexer properties to calls to the `ElementAtOrDefault` method. Unlike an array indexer, the `ElementAtOrDefault` method returns `Nothing` if the index is out of range. This behavior is useful when you cannot easily determine the number of elements in a collection.  
  
 This indexer property is like an extension property for collections that implement <xref:System.Collections.Generic.IEnumerable%601> or <xref:System.Linq.IQueryable%601>: it is used only if the collection does not have an indexer or a default property.  
  
 To access the value of the first element in a collection of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects, you can use the XML `Value` property. For more information, see [XML Value Property](../../../visual-basic/language-reference/xml-axis/xml-value-property.md).  
  
## <a name="example"></a>示例  
 The following example shows how to use the extension indexer to access the second child node in a collection of <xref:System.Xml.Linq.XElement> objects. The collection is accessed by using the child axis property, which gets all child elements named `phone` in the `contact` object.  
  
 [!code-vb[VbXMLSamples#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#24)]  
  
 此代码显示以下文本：  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>请参阅

- <xref:System.Xml.Linq.XElement>
- [XML 轴属性](../../../visual-basic/language-reference/xml-axis/index.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
- [XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
