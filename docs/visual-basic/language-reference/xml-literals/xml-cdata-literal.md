---
title: "XML CDATA 文本 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.XmlLiteralCdata
helpviewer_keywords:
- CDATA literal [Visual Basic]
- XML CDATA literal [Visual Basic]
- XML literals [Visual Basic], CDATA
ms.assetid: 9eafb6a4-dd9d-4866-85e8-0654c65abc44
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 906fd2494dd952c08088b9b7e38dba4505780481
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
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
 必需。 若要显示在 XML CDATA 部分中的文本内容。  
  
 `]]>`  
 必需。 表示节的结尾。  
  
## <a name="return-value"></a>返回值  
 一个 <xref:System.Xml.Linq.XCData> 对象。  
  
## <a name="remarks"></a>备注  
 XML CDATA 节包含应包含，但未分析的 xml，包含它的原始文本。 XML CDATA 节可以包含任何文本。 这包括 XML 保留的字符。 XML CDATA 节结束与序列"]] >"。 这意味着以下几点：  
  
-   你无法使用嵌入式的表达式中的 XML CDATA 文本，因为嵌入式的表达式分隔符是有效的 XML CDATA 内容。  
  
-   XML CDATA 节不能嵌套，因为`content`不能包含值"]] >"。  
  
 你可以将 XML CDATA 文本分配给一个变量，或将其包含在 XML 元素文本。  
  
> [!NOTE]
>  XML 文本可以跨多个行，但不使用行继续符。 这使您可以从 XML 文档中复制内容，然后将其粘贴直接到[!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]程序。  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]编译器将 XML CDATA 文本转换为调用<xref:System.Xml.Linq.XCData.%23ctor%2A>构造函数。  
  
## <a name="example"></a>示例  
 下面的示例创建一个包含文本的 CDATA 节"可以包含文本\<XML > 标记"。  
  
 [!code-vb[VbXMLSamples#23](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/xml-cdata-literal_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.Linq.XCData>  
 [XML 元素文本](../../../visual-basic/language-reference/xml-literals/xml-element-literal.md)  
 [XML 文本](../../../visual-basic/language-reference/xml-literals/index.md)  
 [在 Visual Basic 中创建 XML](../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)
