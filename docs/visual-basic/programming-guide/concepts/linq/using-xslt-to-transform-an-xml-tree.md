---
title: "使用 XSLT 转换 XML 树 (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3390ca68-c270-4e1d-b64b-6a063a77017c
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 18637ecf786c3e44e7a07b5a1ca48cf3c8a4ae35
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="using-xslt-to-transform-an-xml-tree-visual-basic"></a>使用 XSLT 转换 XML 树 (Visual Basic)
可以创建 XML 树，从 XML 树创建 <xref:System.Xml.XmlReader>，创建新文档，然后创建 <xref:System.Xml.XmlWriter>，以写入新文档。 然后，您可以调用 XSLT 转换，并可以将 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter> 传递到转换中。 在转换成功完成后，使用转换的结果，填充新的 XML 树。  
  
## <a name="example"></a>示例  
  
```vb  
Dim xslMarkup As XDocument = _   
    <?xml version='1.0'?>  
    <xsl:stylesheet xmlns:xsl='http://www.w3.org/1999/XSL/Transform' version='1.0'>  
        <xsl:template match='/Parent'>  
            <Root>  
                <C1>  
                    <xsl:value-of select='Child1'/>  
                </C1>  
                <C2>  
                    <xsl:value-of select='Child2'/>  
                </C2>  
            </Root>  
        </xsl:template>  
    </xsl:stylesheet>  
  
Dim xmlTree As XElement = _   
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = _  
        New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transform and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 该示例产生下面的输出：  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A?displayProperty=nameWithType>  
 <xref:System.Xml.Linq.XNode.CreateReader%2A?displayProperty=nameWithType>  
 [高级的 LINQ to XML 编程 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/advanced-linq-to-xml-programming.md)
