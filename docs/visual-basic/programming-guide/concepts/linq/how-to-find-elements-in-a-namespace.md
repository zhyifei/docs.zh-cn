---
title: "如何︰ 查找 Namespace (XPATH-LINQ to XML) 中的元素 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: c7cb3b77-3424-4b54-9efa-4dc715948e41
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9efa99c1b8cffa6d02a40ee8f302a6e1ad0b6b6e
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="how-to-find-elements-in-a-namespace-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="82093-102">如何︰ 查找 Namespace (XPATH-LINQ to XML) 中的元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82093-102">How to: Find Elements in a Namespace (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="82093-103">XPath 表达式可以在特定命名空间中查找节点。</span><span class="sxs-lookup"><span data-stu-id="82093-103">XPath expressions can find nodes in a particular namespace.</span></span> <span data-ttu-id="82093-104">XPath 表达式使用命名空间前缀来指定命名空间。</span><span class="sxs-lookup"><span data-stu-id="82093-104">XPath expressions use namespace prefixes for specifying namespaces.</span></span> <span data-ttu-id="82093-105">若要分析包含命名空间前缀的 XPath 表达式，必须将对象传递给实现<xref:System.Xml.IXmlNamespaceResolver>。</xref:System.Xml.IXmlNamespaceResolver>的 XPath 方法</span><span class="sxs-lookup"><span data-stu-id="82093-105">To parse an XPath expression that contains namespace prefixes, you must pass an object to the XPath methods that implements <xref:System.Xml.IXmlNamespaceResolver>.</span></span> <span data-ttu-id="82093-106">此示例使用<xref:System.Xml.XmlNamespaceManager>。</xref:System.Xml.XmlNamespaceManager></span><span class="sxs-lookup"><span data-stu-id="82093-106">This example uses <xref:System.Xml.XmlNamespaceManager>.</span></span>  
  
 <span data-ttu-id="82093-107">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="82093-107">The XPath expression is:</span></span>  
  
 `./aw:*`  
  
## <a name="example"></a><span data-ttu-id="82093-108">示例</span><span class="sxs-lookup"><span data-stu-id="82093-108">Example</span></span>  
 <span data-ttu-id="82093-109">下面的示例读取包含两个命名空间的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="82093-109">The following example reads an XML tree that contains two namespaces.</span></span> <span data-ttu-id="82093-110">它使用<xref:System.Xml.XmlReader>来读取 XML 文档。</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="82093-110">It uses an <xref:System.Xml.XmlReader> to read the XML document.</span></span> <span data-ttu-id="82093-111">然后，它获取<xref:System.Xml.XmlNameTable>从<xref:System.Xml.XmlReader>，以及<xref:System.Xml.XmlNamespaceManager>从<xref:System.Xml.XmlNameTable>。</xref:System.Xml.XmlNameTable> </xref:System.Xml.XmlNamespaceManager> </xref:System.Xml.XmlReader> </xref:System.Xml.XmlNameTable></span><span class="sxs-lookup"><span data-stu-id="82093-111">It then gets an <xref:System.Xml.XmlNameTable> from the <xref:System.Xml.XmlReader>, and an <xref:System.Xml.XmlNamespaceManager> from the <xref:System.Xml.XmlNameTable>.</span></span> <span data-ttu-id="82093-112">它使用<xref:System.Xml.XmlNamespaceManager>时选择的元素。</xref:System.Xml.XmlNamespaceManager></span><span class="sxs-lookup"><span data-stu-id="82093-112">It uses the <xref:System.Xml.XmlNamespaceManager> when selecting elements.</span></span>  
  
```vb  
Dim reader As XmlReader = _  
        XmlReader.Create("ConsolidatedPurchaseOrders.xml")  
Dim root As XElement = XElement.Load(reader)  
Dim nameTable As XmlNameTable = reader.NameTable  
Dim namespaceManager As XmlNamespaceManager = New XmlNamespaceManager(nameTable)  
namespaceManager.AddNamespace("aw", "http://www.adventure-works.com")  
  
Dim list1 As IEnumerable(Of XElement) = _  
        root.XPathSelectElements("./aw:*", namespaceManager)  
Dim list2 As IEnumerable(Of XElement) = _  
    From el In root.Elements() _  
    Where el.Name.Namespace = "http://www.adventure-works.com" _  
    Select el  
  
If list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count() Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list2  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="82093-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="82093-113">This example produces the following output:</span></span>  
  
```  
Results are identical  
<aw:PurchaseOrder PONumber="11223" Date="2000-01-15" xmlns:aw="http://www.adventure-works.com">  
    <aw:ShippingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:ShippingAddress>  
    <aw:BillingAddress>  
      <aw:Name>Chris Preston</aw:Name>  
      <aw:Street>123 Main St.</aw:Street>  
      <aw:City>Seattle</aw:City>  
      <aw:State>WA</aw:State>  
      <aw:Zip>98113</aw:Zip>  
      <aw:Country>USA</aw:Country>  
    </aw:BillingAddress>  
    <aw:DeliveryInstructions>Ship only complete order.</aw:DeliveryInstructions>  
    <aw:Item PartNum="LIT-01">  
      <aw:ProductID>Litware Networking Card</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>20.99</aw:Price>  
    </aw:Item>  
    <aw:Item PartNum="LIT-25">  
      <aw:ProductID>Litware 17in LCD Monitor</aw:ProductID>  
      <aw:Qty>1</aw:Qty>  
      <aw:Price>199.99</aw:Price>  
    </aw:Item>  
  </aw:PurchaseOrder>  
```  
  
## <a name="see-also"></a><span data-ttu-id="82093-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="82093-114">See Also</span></span>  
 [<span data-ttu-id="82093-115">LINQ to XML 针对 XPath 用户 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="82093-115">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
