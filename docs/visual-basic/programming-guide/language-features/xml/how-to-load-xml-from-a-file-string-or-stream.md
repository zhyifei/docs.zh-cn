---
title: 如何：从文件、字符串或流加载 XML (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- XML [Visual Basic], loading
- LINQ to XML [Visual Basic], loading XML from files
ms.assetid: 2b02dcec-4cca-4575-b4ad-89ceb87b984c
ms.openlocfilehash: 241f6552e46d7689b42a409ba44bc747984773ca
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33647626"
---
# <a name="how-to-load-xml-from-a-file-string-or-stream-visual-basic"></a>如何：从文件、字符串或流加载 XML (Visual Basic)
你可以创建[XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)并通过使用几种方法使用从外部源如文件、 字符串或流的内容填充它们。 在下面的示例演示了这些方法。  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-load-xml-from-a-file"></a>若要从文件加载 XML  
  
-   来填充 XML 文本如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从一个文件，使用`Load`方法。 此方法可以将文件路径、 文本流或 XML 流作为输入。  
  
     下面的代码示例演示了利用<xref:System.Xml.Linq.XDocument.Load%28System.String%29>方法来填充<xref:System.Xml.Linq.XDocument>使用 XML 文本文件中的对象。  
  
     [!code-vb[VbXMLSamples#43](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_1.vb)]  
  
### <a name="to-load-xml-from-a-string"></a>从字符串加载 XML  
  
-   来填充 XML 文本如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从一个字符串，你可以使用`Parse`方法。  
  
     下面的代码示例演示了利用<xref:System.Xml.Linq.XDocument.Parse%28System.String%29?displayProperty=nameWithType>方法来填充<xref:System.Xml.Linq.XDocument>具有 XML 从字符串的对象。  
  
     [!code-vb[VbXMLSamples#47](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_2.vb)]  
  
### <a name="to-load-xml-from-a-stream"></a>从流加载 XML  
  
-   来填充 XML 文本如<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>对象从流中，你可以使用`Load`方法或<xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>方法。  
  
 下面的代码示例演示了利用<xref:System.Xml.Linq.XNode.ReadFrom%2A>方法来填充<xref:System.Xml.Linq.XDocument>具有从 XML 流的 XML 对象。  
  
 [!code-vb[VbXMLSamples#46](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-load-xml-from-a-file-string-or-stream_3.vb)]  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.ReadFrom%2A?displayProperty=nameWithType>  
 [XML 文本](../../../../visual-basic/language-reference/xml-literals/index.md)  
 [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 [在 Visual Basic 中操控 XML](../../../../visual-basic/programming-guide/language-features/xml/manipulating-xml.md)
