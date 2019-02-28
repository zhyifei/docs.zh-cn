---
title: XML 文本中的空白 (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- white space [XML in Visual Basic]
- XML literals [Visual Basic], white space
ms.assetid: dfe3a9ff-d69a-418e-a6b5-476f4ed84219
ms.openlocfilehash: ef371a984d03485ccaf1ee5d61aa3cf39d80ef32
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56979055"
---
# <a name="white-space-in-xml-literals-visual-basic"></a>XML 文本中的空白 (Visual Basic)
Visual Basic 编译器创建时包含的有意义的空白字符将从 XML 文本[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]对象。 它不会合并无意义的空白字符。  
  
## <a name="significant-and-insignificant-white-space"></a>有效空白和无关紧要的空白区域  
 只有三个区域中，XML 文本中的空格字符是有意义：  
  
-   它们的特性值中。  
  
-   当它们都属于某个元素的文本内容和文本中还包含其他字符。  
  
-   它们在嵌入式表达式的元素的文本内容。  
  
 否则为编译器将视为无意义的空白字符，不包括然后中[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]该文字的对象。  
  
 若要在 XML 文本中包括无关紧要的空白区域，使用嵌入式的表达式包含了空白字符串。  
  
> [!NOTE]
>  如果`xml:space`特性出现在 XML 元素文本、 Visual Basic 编译器将该特性中的包含<xref:System.Xml.Linq.XElement>对象，而是添加此属性不会更改编译器如何处理空白区域。  
  
## <a name="examples"></a>示例  
 下面的示例包含两个 XML 元素，外部和内部。 两个元素都包含其文本内容中的空白区域。 外部元素中的空白并不重要，因为它仅包含空格和一个 XML 元素。 内部元素中的空白区域很重要，因为它包含空格和文本。  
  
 [!code-vb[VbXMLSamples#29](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#29)]  
  
 当运行时，此代码将显示以下文本。  
  
```xml  
<outer>  
  <inner>  
                                          Inner text  
                                      </inner>  
</outer>  
```  
  
## <a name="see-also"></a>请参阅
- [在 Visual Basic 中创建 XML](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
