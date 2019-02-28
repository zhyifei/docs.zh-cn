---
title: XML CDATA 文本 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
ms.openlocfilehash: 01a505130d566ec88a6d87e5e9ad525e449d7298
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56981239"
---
# <a name="xml-cdata-literal-visual-basic"></a>XML CDATA 文本 (Visual Basic)
一个文本表示<xref:System.Xml.Linq.XCData>对象。  
  
## <a name="syntax"></a>语法  
  
```xml  
<![CDATA[content]]>  
```  
  
## <a name="parts"></a>部件  
 `<![CDATA[`  
 必需。 表示 XML CDATA 节的开头。  
  
 `content`  
 必需。 若要在 XML CDATA 节中显示的文本内容。  
  
 `]]>`  
 必需。 表示部分的结尾。  
  
## <a name="return-value"></a>返回值  
 一个 <xref:System.Xml.Linq.XCData> 对象。  
  
## <a name="remarks"></a>备注  
 XML CDATA 节包含应包含，但未能分析，它包含的 xml 的原始文本。 XML CDATA 节可以包含任何文本。 这包括保留的 XML 字符。 XML CDATA 节结尾序列"]] >"。 这意味着以下几点：  
  
-   因为嵌入的分隔符是有效的 XML CDATA 内容，不能使用嵌入式的表达式中的 XML CDATA 文本。  
  
-   XML CDATA 节无法嵌套，因为`content`不能包含值"]] >"。  
  
 可以将 XML CDATA 文本分配给一个变量，或将其包含在 XML 元素文本。  
  
> [!NOTE]
>  XML 文本可以跨多个行，但不使用行继续符。 这使您可以从 XML 文档中复制内容并将其粘贴到 Visual Basic 程序直接。  
  
 Visual Basic 编译器将 XML CDATA 文本转换为调用<xref:System.Xml.Linq.XCData.%23ctor%2A>构造函数。  
  
## <a name="example"></a>示例  
 下面的示例创建一个包含文本的 CDATA 节"可以包含文字\<XML > 标记"。  
  
 [!code-vb[VbXMLSamples#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples11.vb#23)]  
  
## <a name="see-also"></a>请参阅
- <xref:System.Xml.Linq.XCData>
- [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)
- [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)
- [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
