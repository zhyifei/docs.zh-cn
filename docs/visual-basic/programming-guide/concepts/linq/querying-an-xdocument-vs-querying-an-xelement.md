---
title: "查询 XDocument 与查询 XElement (Visual Basic 中) |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 2d111f84-0ded-4cde-8d93-5440557a726d
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 93f0f7f50ad305540a6afef2374d4b948de48705
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="querying-an-xdocument-vs-querying-an-xelement-visual-basic"></a><span data-ttu-id="c86ef-102">查询 XDocument 与查询 XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c86ef-102">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>
<span data-ttu-id="c86ef-103">通过<xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>，您将注意到，您需要编写查询稍有不同于通过<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>。</xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>负载时，</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>将文档加载时</span><span class="sxs-lookup"><span data-stu-id="c86ef-103">When you load a document via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, you will notice that you have to write queries slightly differently than when you load via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>.</span></span>  
  
## <a name="comparison-of-xdocumentload-and-xelementload"></a><span data-ttu-id="c86ef-104">XDocument.Load 与 XElement.Load 的比较</span><span class="sxs-lookup"><span data-stu-id="c86ef-104">Comparison of XDocument.Load and XElement.Load</span></span>  
 <span data-ttu-id="c86ef-105">当您将 XML 文档加载到<xref:System.Xml.Linq.XElement>通过<xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>、<xref:System.Xml.Linq.XElement>根目录下的 XML 树包含所加载文档的根元素。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c86ef-105">When you load an XML document into an <xref:System.Xml.Linq.XElement> via <xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName>, the <xref:System.Xml.Linq.XElement> at the root of the XML tree contains the root element of the loaded document.</span></span> <span data-ttu-id="c86ef-106">但是，当您加载同一个 XML 文档<xref:System.Xml.Linq.XDocument><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>树的根<xref:System.Xml.Linq.XDocument>节点，然后加载文档的根元素是一个允许的子<xref:System.Xml.Linq.XElement>节点的<xref:System.Xml.Linq.XDocument>。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> ，</xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>通过</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="c86ef-106">However, when you load the same XML document into an <xref:System.Xml.Linq.XDocument> via <xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName>, the root of the tree is an <xref:System.Xml.Linq.XDocument> node, and the root element of the loaded document is the one allowed child <xref:System.Xml.Linq.XElement> node of the <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="c86ef-107">[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 轴相对于根节点进行操作。</span><span class="sxs-lookup"><span data-stu-id="c86ef-107">The [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axes operate relative to the root node.</span></span>  
  
 <span data-ttu-id="c86ef-108">第一个示例加载使用<xref:System.Xml.Linq.XElement.Load%2A>。</xref:System.Xml.Linq.XElement.Load%2A> XML 树</span><span class="sxs-lookup"><span data-stu-id="c86ef-108">This first example loads an XML tree using <xref:System.Xml.Linq.XElement.Load%2A>.</span></span> <span data-ttu-id="c86ef-109">然后它查询树根部的子元素。</span><span class="sxs-lookup"><span data-stu-id="c86ef-109">It then queries for the child elements of the root of the tree.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XElement.Load")  
Console.WriteLine("----")  
Dim doc As XElement = XElement.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c86ef-110">此示例将按预期产生以下输出：</span><span class="sxs-lookup"><span data-stu-id="c86ef-110">As expected, this example produces the following output:</span></span>  
  
```  
Querying tree loaded with XElement.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
 <span data-ttu-id="c86ef-111">下面的示例是一个相同更高版本，与 XML 树加载到<xref:System.Xml.Linq.XDocument>而不是<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></xref:System.Xml.Linq.XDocument>异常</span><span class="sxs-lookup"><span data-stu-id="c86ef-111">The following example is the same as the one above, with the exception that the XML tree is loaded into an <xref:System.Xml.Linq.XDocument> instead of an <xref:System.Xml.Linq.XElement>.</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c86ef-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="c86ef-112">This example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
</Root>  
```  
  
 <span data-ttu-id="c86ef-113">请注意，同样的查询返回一个 `Root` 节点，而不是返回三个子节点。</span><span class="sxs-lookup"><span data-stu-id="c86ef-113">Notice that the same query returned the one `Root` node instead of the three child nodes.</span></span>  
  
 <span data-ttu-id="c86ef-114">处理这一种方法是使用<xref:System.Xml.Linq.XDocument.Root%2A>属性之前访问轴方法，如下所示︰</xref:System.Xml.Linq.XDocument.Root%2A></span><span class="sxs-lookup"><span data-stu-id="c86ef-114">One approach to dealing with this is to use the <xref:System.Xml.Linq.XDocument.Root%2A> property before accessing the axes methods, as follows:</span></span>  
  
```vb  
' Create a simple document and  write it to a file  
File.WriteAllText("Test.xml", "<Root>" + Environment.NewLine + _  
    "    <Child1>1</Child1>" + Environment.NewLine + _  
    "    <Child2>2</Child2>" + Environment.NewLine + _  
    "    <Child3>3</Child3>" + Environment.NewLine + _  
    "</Root>")  
  
Console.WriteLine("Querying tree loaded with XDocument.Load")  
Console.WriteLine("----")  
Dim doc As XDocument = XDocument.Load("Test.xml")  
Dim childList As IEnumerable(Of XElement) = _  
        From el In doc.Root.Elements() _  
        Select el  
For Each e As XElement In childList  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="c86ef-115">此查询现在在相同的执行方式与在树上查询来源于<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="c86ef-115">This query now performs in the same way as the query on the tree rooted in <xref:System.Xml.Linq.XElement>.</span></span> <span data-ttu-id="c86ef-116">此示例产生以下输出：</span><span class="sxs-lookup"><span data-stu-id="c86ef-116">The example produces the following output:</span></span>  
  
```  
Querying tree loaded with XDocument.Load  
----  
<Child1>1</Child1>  
<Child2>2</Child2>  
<Child3>3</Child3>  
```  
  
## <a name="see-also"></a><span data-ttu-id="c86ef-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c86ef-117">See Also</span></span>  
 [<span data-ttu-id="c86ef-118">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c86ef-118">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
