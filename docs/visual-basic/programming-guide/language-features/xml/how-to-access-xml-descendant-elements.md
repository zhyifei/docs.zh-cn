---
title: 如何：访问 XML 后代元素
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: cc045114c67ee2917ef672e734bc852c40d408ac
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347161"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>如何：访问 XML 后代元素 (Visual Basic)
此示例演示如何使用子代轴属性访问具有指定名称并包含在 XML 元素下的所有 XML 元素。 具体而言，它使用 `Value` 属性获取集合中 `name` 子代轴属性返回的第一个元素的值。 `name` 子代轴属性可获取 `contacts` 对象中包含的所有名为 `name` 的元素。 此示例还使用 `phone` 子代轴属性来访问 `contacts` 对象中包含的所有名为 `phone` 的后代。  
  
## <a name="example"></a>示例  
 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a>编译代码  
 此示例需要：  
  
- 对 <xref:System.Xml.Linq> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [XML 子代轴属性](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)
- [XML 值属性](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)
- [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
