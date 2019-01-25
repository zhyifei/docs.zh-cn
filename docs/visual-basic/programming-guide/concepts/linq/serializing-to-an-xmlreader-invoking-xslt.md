---
title: 序列化为 XmlReader (调用 XSLT) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 8b64f95a-e8f6-40f7-99f9-a8002c63af96
ms.openlocfilehash: 8cdb5e55738c14792c0628319fb937aa95a7e58d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54549728"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-visual-basic"></a><span data-ttu-id="8f58c-102">序列化为 XmlReader (调用 XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f58c-102">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>
<span data-ttu-id="8f58c-103">在使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的 <xref:System.Xml?displayProperty=nameWithType> 互操作性功能时，可以使用 <xref:System.Xml.Linq.XNode.CreateReader%2A> 来创建 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="8f58c-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8f58c-104">从该 <xref:System.Xml.XmlReader> 进行读取的模块从 XML 树读取节点，并对它们进行相应的处理。</span><span class="sxs-lookup"><span data-stu-id="8f58c-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="8f58c-105">调用 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="8f58c-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="8f58c-106">此方法可能在调用 XSLT 转换时使用。</span><span class="sxs-lookup"><span data-stu-id="8f58c-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="8f58c-107">可以创建 XML 树，从 XML 树创建 <xref:System.Xml.XmlReader>，创建新文档，然后创建 <xref:System.Xml.XmlWriter> 以写入新文档。</span><span class="sxs-lookup"><span data-stu-id="8f58c-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="8f58c-108">接着，可以调用 XSLT 转换，传入 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="8f58c-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="8f58c-109">在转换成功完成后，使用转换的结果，填充新的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="8f58c-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
  
Dim xmlTree As XDocument = _  
    <?xml version='1.0'?>  
    <Parent>  
        <Child1>Child1 data</Child1>  
        <Child2>Child2 data</Child2>  
    </Parent>  
  
Dim newTree As XDocument = New XDocument()  
Using writer As XmlWriter = newTree.CreateWriter()  
    ' Load the style sheet.  
    Dim xslt As XslCompiledTransform = New XslCompiledTransform()  
    xslt.Load(xslMarkup.CreateReader())  
  
    ' Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer)  
End Using  
  
Console.WriteLine(newTree)  
```  
  
 <span data-ttu-id="8f58c-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="8f58c-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="8f58c-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="8f58c-111">See also</span></span>
- [<span data-ttu-id="8f58c-112">序列化 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f58c-112">Serializing XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-xml-trees.md)
