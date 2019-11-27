---
title: 如何：访问 XML 子元素
ms.date: 07/20/2015
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
ms.openlocfilehash: af5ea809cb0777b16230f20e133764dd5f1f86d9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74332343"
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>如何：访问 XML 子元素 (Visual Basic)
此示例演示如何使用子轴属性访问 XML 元素中具有指定名称的所有 XML 子元素。 具体而言，它使用 <xref:System.Xml.Linq.XElement.Value%2A> 属性获取 `name` 子轴属性返回的集合中第一个元素的值。 `name` 子轴属性获取 `contact` 对象中名为 `phone` 的所有子元素。 此示例还使用 `phone` 子轴属性访问 `contact` 对象中包含的所有名为 `phone` 的子元素。  
  
## <a name="example"></a>示例  
 [!code-vb[VbXMLSamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples4.vb#10)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System.Xml.Linq> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- [XML 子轴属性](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [XML 值属性](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
