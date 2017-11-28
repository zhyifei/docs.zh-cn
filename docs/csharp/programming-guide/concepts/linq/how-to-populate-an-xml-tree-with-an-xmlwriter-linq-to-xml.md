---
title: "如何：使用 XmlWriter 填充 XML 树 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: cd5674d1-5c54-4efc-ba68-e23b2875295f
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 2df0626d0376973aeaa09876c6737c93dd671da4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml-c"></a><span data-ttu-id="c98e5-102">如何：使用 XmlWriter 填充 XML 树 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="c98e5-102">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (C#)</span></span>
<span data-ttu-id="c98e5-103">填充 XML 树的一种方式是使用 <xref:System.Xml.Linq.XContainer.CreateWriter%2A> 创建一个 <xref:System.Xml.XmlWriter>，然后写入 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="c98e5-103">One way to populate an XML tree is to use <xref:System.Xml.Linq.XContainer.CreateWriter%2A> to create an <xref:System.Xml.XmlWriter>, and then write to the <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c98e5-104">XML 树将用写入到 <xref:System.Xml.XmlWriter> 的所有节点进行填充。</span><span class="sxs-lookup"><span data-stu-id="c98e5-104">The XML tree is populated with all nodes that are written to the <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="c98e5-105">在与预期会向 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 写入数据的另一个类（如 <xref:System.Xml.XmlWriter>）一起使用 <xref:System.Xml.Xsl.XslCompiledTransform> 时，通常应使用此方法。</span><span class="sxs-lookup"><span data-stu-id="c98e5-105">You would typically use this method when you use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] with another class that expects to write to an <xref:System.Xml.XmlWriter>, such as <xref:System.Xml.Xsl.XslCompiledTransform>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c98e5-106">示例</span><span class="sxs-lookup"><span data-stu-id="c98e5-106">Example</span></span>  
 <span data-ttu-id="c98e5-107"><xref:System.Xml.Linq.XContainer.CreateWriter%2A> 可能在调用 XSLT 转换时使用。</span><span class="sxs-lookup"><span data-stu-id="c98e5-107">One possible use for <xref:System.Xml.Linq.XContainer.CreateWriter%2A> is when invoking an XSLT transformation.</span></span> <span data-ttu-id="c98e5-108">本示例创建一个 XML 树，从该 XML 树创建一个 <xref:System.Xml.XmlReader>，创建一个新文档，然后创建要写入到新文档的 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="c98e5-108">This example creates an XML tree, creates an <xref:System.Xml.XmlReader> from the XML tree, creates a new document, and then creates an <xref:System.Xml.XmlWriter> to write into the new document.</span></span> <span data-ttu-id="c98e5-109">示例然后调用 XSLT 转换，传入 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="c98e5-109">It then invokes the XSLT transformation, passing in <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="c98e5-110">在转换成功完成后，使用转换的结果，填充新的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="c98e5-110">After the transformation successfully completes, the new XML tree is populated with the results of the transformation.</span></span>  
  
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
using (XmlWriter writer = newTree.CreateWriter())  
{  
    // Load the style sheet.  
    XslCompiledTransform xslt = new XslCompiledTransform();  
    xslt.Load(XmlReader.Create(new StringReader(xslMarkup)));  
  
    // Execute the transformation and output the results to a writer.  
    xslt.Transform(xmlTree.CreateReader(), writer);  
}  
  
Console.WriteLine(newTree);  
```  
  
 <span data-ttu-id="c98e5-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c98e5-111">This example produces the following output:</span></span>  
  
```xml  
<Root>  
  <C1>Child1 data</C1>  
  <C2>Child2 data</C2>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c98e5-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c98e5-112">See Also</span></span>  
 <xref:System.Xml.Linq.XContainer.CreateWriter%2A>  
 <xref:System.Xml.XmlWriter>  
 <xref:System.Xml.Xsl.XslCompiledTransform>  
 [<span data-ttu-id="c98e5-113">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="c98e5-113">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
