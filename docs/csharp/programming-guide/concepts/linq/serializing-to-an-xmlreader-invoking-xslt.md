---
title: 序列化为 XmlReader（调用 XSLT）(C#)
ms.date: 07/20/2015
ms.assetid: 4cc3ee03-ef4c-429b-a408-fedd10b728cd
ms.openlocfilehash: b079fe05fa8c230f644e011dcb62ec54f55cae60
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66487188"
---
# <a name="serializing-to-an-xmlreader-invoking-xslt-c"></a><span data-ttu-id="d7f32-102">序列化为 XmlReader（调用 XSLT）(C#)</span><span class="sxs-lookup"><span data-stu-id="d7f32-102">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>
<span data-ttu-id="d7f32-103">在使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的 <xref:System.Xml?displayProperty=nameWithType> 互操作性功能时，可以使用 <xref:System.Xml.Linq.XNode.CreateReader%2A> 来创建 <xref:System.Xml.XmlReader>。</span><span class="sxs-lookup"><span data-stu-id="d7f32-103">When you use the <xref:System.Xml?displayProperty=nameWithType> interoperability capabilities of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], you can use <xref:System.Xml.Linq.XNode.CreateReader%2A> to create an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="d7f32-104">从该 <xref:System.Xml.XmlReader> 进行读取的模块从 XML 树读取节点，并对它们进行相应的处理。</span><span class="sxs-lookup"><span data-stu-id="d7f32-104">The module that reads from this <xref:System.Xml.XmlReader> reads the nodes from the XML tree and processes them accordingly.</span></span>  
  
## <a name="invoking-an-xslt-transformation"></a><span data-ttu-id="d7f32-105">调用 XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="d7f32-105">Invoking an XSLT Transformation</span></span>  
 <span data-ttu-id="d7f32-106">此方法可能在调用 XSLT 转换时使用。</span><span class="sxs-lookup"><span data-stu-id="d7f32-106">One possible use for this method is when invoking an XSLT transformation.</span></span> <span data-ttu-id="d7f32-107">可以创建 XML 树，从 XML 树创建 <xref:System.Xml.XmlReader>，创建新文档，然后创建 <xref:System.Xml.XmlWriter> 以写入新文档。</span><span class="sxs-lookup"><span data-stu-id="d7f32-107">You can create an XML tree, create an <xref:System.Xml.XmlReader> from the XML tree, create a new document, and then create an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="d7f32-108">接着，可以调用 XSLT 转换，传入 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="d7f32-108">Then, you can invoke the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="d7f32-109">在转换成功完成后，使用转换的结果，填充新的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="d7f32-109">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
```csharp  
string xslMarkup = @"<?xml version='1.0'?>  
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
</xsl:stylesheet>";  
  
XDocument xmlTree = new XDocument(  
    new XElement("Parent",  
        new XElement("Child1", "Child1 data"),  
        new XElement("Child2", "Child2 data")  
    )  
);  
  
XDocument newTree = new XDocument();  
using (XmlWriter writer = newTree.CreateWriter()) {  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="d7f32-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="d7f32-110">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="d7f32-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="d7f32-111">See also</span></span>

- [<span data-ttu-id="d7f32-112">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="d7f32-112">Serializing XML Trees (C#)</span></span>](serializing-to-files-textwriters-and-xmlwriters.md)
