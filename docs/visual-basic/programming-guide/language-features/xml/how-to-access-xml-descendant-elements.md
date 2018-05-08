---
title: 如何：访问 XML 后代元素 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: 6d41844b540631df96740ce56818c125cf85e928
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a>如何：访问 XML 后代元素 (Visual Basic)
此示例演示如何使用子代轴属性来访问具有指定的名称且包含的 XML 元素下的所有 XML 元素。 具体而言，它使用`Value`属性集合中获取的第一个元素的值`name`子代轴属性返回。 `name`子代轴属性可获取名为的所有元素`name`中包含`contacts`对象。 此示例还使用`phone`子代轴属性来访问名为的所有后代`phone`中包含`contacts`对象。  
  
## <a name="example"></a>示例  
 [!code-vb[VbXMLSamples#31](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-descendant-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 <xref:System.Xml.Linq> 命名空间的引用。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>  
 [XML 子代轴属性](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)  
 [XML 值属性](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
