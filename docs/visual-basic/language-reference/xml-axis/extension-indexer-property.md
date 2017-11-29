---
title: "扩展索引器属性 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlPropertyExtensionIndexer
helpviewer_keywords:
- Visual Basic code, accessing XML
- XML extension indexer [Visual Basic]
- extension indexer [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: a16a4b13-54be-432c-82b3-a87091464ada
caps.latest.revision: "22"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 99d14b6e54a59ffc904a9e786c22498d23ee8ab6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="extension-indexer-property-visual-basic"></a>扩展索引器属性 (Visual Basic)
提供对集合中各个元素的访问。  
  
## <a name="syntax"></a>语法  
  
```  
object(index)  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`object`|必需。 查询的集合。 也就是说，集合可实现<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>。|  
|(|必需。 表示索引器属性的开头。|  
|`index`|必需。 一个整数表达式，指定集合的某个元素的从零开始的位置。|  
|)|必需。 表示索引器属性的末尾。|  
  
## <a name="return-value"></a>返回值  
 在集合中，指定的位置中的对象或`Nothing`如果索引超出范围。  
  
## <a name="remarks"></a>备注  
 扩展索引器属性可用于访问集合中的各个元素。 XML 轴属性的输出通常用于此索引器属性。 XML 子和 XML 子代轴属性返回的集合<xref:System.Xml.Linq.XElement>对象或属性值。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将扩展索引器属性转换为调用`ElementAtOrDefault`方法。 与数组索引器，不同`ElementAtOrDefault`方法返回`Nothing`如果索引超出范围。 当你将无法轻松确定集合中的元素的数目时，此行为很有用。  
  
 此索引器属性是实现的集合的扩展属性相似<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Linq.IQueryable%601>： 仅当集合不具有一个索引器或默认属性时，才使用它。  
  
 若要访问的集合中的第一个元素的值<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象，你可以使用 XML`Value`属性。 有关详细信息，请参阅[XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。  
  
## <a name="example"></a>示例  
 下面的示例演示如何扩展索引器用于访问集合中的第二个子节点<xref:System.Xml.Linq.XElement>对象。 通过使用子轴属性，它将获取名为的所有子元素属性访问集合`phone`中`contact`对象。  
  
 [!code-vb[VbXMLSamples#24](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/extension-indexer-property_1.vb)]  
  
 此代码显示以下文本：  
  
 `Second phone number: 425-555-0145`  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.Linq.XElement>  
 [XML 轴属性](../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 [XML 值属性](../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
