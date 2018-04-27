---
title: XML 文本中的空白 (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
caps.latest.revision: 14
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e6d23aa54b150748aac9aa955f4bd86ee88358ea
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 文本中的空白 (Visual Basic)
Visual Basic 编译器创建时包含的有意义的空白字符将从 XML 文本[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。 它不会合并无意义的空白字符。  
  
## <a name="significant-and-insignificant-white-space"></a>有效空白和无关紧要的空白区域  
 只有三个区域中，XML 文本中的空格字符是有意义：  
  
-   当它们位于属性值。  
  
-   当它们是元素的文本内容的一部分，并且该文本还包含其他字符。  
  
-   当它们位于元素的文本内容的嵌入式表达式。  
  
 否则为编译器将视为无意义的空白字符，且不包括然后中[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]文本的对象。  
  
 若要在 XML 文本中包括无关紧要的空白区域，使用嵌入式的表达式包含具有空白区域的字符串文本。  
  
> [!NOTE]
>  如果`xml:space`特性随即显示 XML 元素文本中，Visual Basic 编译器包含中的属性<xref:System.Xml.Linq.XElement>对象，但添加此属性不会更改编译器如何处理空白区域。  
  
## <a name="examples"></a>示例  
 下面的示例包含两个 XML 元素，外部和内部。 这两个元素包含文本内容中的空白区域。 中的外部元素的空白区域是无意义，因为它只包含空格和一个 XML 元素。 中元素的内部的空白区域很重要，因为它包含空格和文本。  
  
 [!code-vb[VbXMLSamples#29](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/white-space-in-xml-literals_1.vb)]  
  
 运行时，此代码将显示以下文本。  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>请参阅  
 [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
