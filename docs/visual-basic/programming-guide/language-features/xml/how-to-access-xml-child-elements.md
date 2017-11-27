---
title: "如何：访问 XML 子元素 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- XML axis [Visual Basic], child
- child axis property [Visual Basic]
- XML child axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: 6689eb36-c471-469f-a82d-099ab8197b25
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5d3a708b787ad38f08d4673d4003db839f6cf6a9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-xml-child-elements-visual-basic"></a>如何：访问 XML 子元素 (Visual Basic)
此示例演示如何使用子轴属性来访问某个 XML 元素中具有指定的名称的所有 XML 子元素。 具体而言，它使用<xref:System.Xml.Linq.XElement.Value%2A>属性集合中获取的第一个元素的值`name`子轴属性返回。 `name`子轴属性可获取名为的所有子元素`phone`中`contact`对象。 此示例还使用`phone`子轴属性来访问名为的所有子元素`phone`中包含`contact`对象。  
  
## <a name="example"></a>示例  
 [!code-vb[VbXMLSamples#10](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-access-xml-child-elements_1.vb)]  
  
## <a name="compiling-the-code"></a>编译代码  
 此示例需要：  
  
-   对 <xref:System.Xml.Linq> 命名空间的引用。  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>  
 [XML 子轴属性](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)  
 [XML 值属性](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)  
 [在 Visual Basic 中访问 XML](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)
