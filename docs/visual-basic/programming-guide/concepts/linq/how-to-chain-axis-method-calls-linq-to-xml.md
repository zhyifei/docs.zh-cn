---
title: "如何︰ 链接轴方法调用 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: e4e22942-39bd-460f-b3c0-9f09e53d3aa9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: a32f50ce8a92fa22d9627a1510a4b3ec1087364e
ms.openlocfilehash: 4997f7e91f968f080c22ca9d3a204c748758f832
ms.contentlocale: zh-cn
ms.lasthandoff: 06/01/2017


---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-visual-basic"></a><span data-ttu-id="ae1e6-102">如何︰ 链接轴方法调用 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae1e6-102">How to: Chain Axis Method Calls (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="ae1e6-103">一个在代码中常用的模式是调用轴方法，然后调用一个扩展方法轴。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="ae1e6-104">有两个同名的轴`Elements`返回的元素的集合︰<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>方法和<xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>方法。</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ae1e6-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="ae1e6-105">可以合并这两个轴，在树的给定深度，查找具有指定名称的所有元素。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae1e6-106">示例</span><span class="sxs-lookup"><span data-stu-id="ae1e6-106">Example</span></span>  
 <span data-ttu-id="ae1e6-107">此示例使用<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>和<xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>来查找所有`Name`元素中的所有`Address`元素中的所有`PurchaseOrder`元素。</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ae1e6-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="ae1e6-108">此示例使用下面的 XML 文档︰[示例 XML 文件︰ 多个采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim purchaseOrders As XElement = XElement.Load("PurchaseOrders.xml")  
Dim names As IEnumerable(Of XElement) = _  
    From el In purchaseOrders.<PurchaseOrder>.<Address>.<Name> _  
    Select el  
For Each e As XElement In names  
    Console.WriteLine(e)  
Next  
```  
  
 <span data-ttu-id="ae1e6-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="ae1e6-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="ae1e6-110">这样做的原因的实现之一`Elements`轴是作为<xref:System.Collections.Generic.IEnumerable%601><xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer>的</xref:System.Collections.Generic.IEnumerable%601>扩展方法</span><span class="sxs-lookup"><span data-stu-id="ae1e6-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="ae1e6-111"><xref:System.Xml.Linq.XElement>派生自<xref:System.Xml.Linq.XContainer>，因此您可以调用<xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>方法调用的结果<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName>方法。</xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> </xref:System.Xml.Linq.XContainer></xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="ae1e6-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ae1e6-112">示例</span><span class="sxs-lookup"><span data-stu-id="ae1e6-112">Example</span></span>  
 <span data-ttu-id="ae1e6-113">有时，当可能存在或不存在间隔上级时，您希望在特定的元素深度，检索所有的元素。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="ae1e6-114">例如，在下面的文档中，您可能要检索属于 `ConfigParameter` 元素的子元素的所有 `Customer` 元素，而不是属于 `ConfigParameter` 元素的子元素的 `Root`。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
```xml  
<Root>  
  <ConfigParameter>RootConfigParameter</ConfigParameter>  
  <Customer>  
    <Name>Frank</Name>  
    <Config>  
      <ConfigParameter>FirstConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
  <Customer>  
    <Name>Bob</Name>  
    <!--This customer doesn't have a Config element-->  
  </Customer>  
  <Customer>  
    <Name>Bill</Name>  
    <Config>  
      <ConfigParameter>SecondConfigParameter</ConfigParameter>  
    </Config>  
  </Customer>  
</Root>  
```  
  
 <span data-ttu-id="ae1e6-115">若要执行此操作，可以使用<xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName>轴，如下所示︰</xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="ae1e6-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> axis, as follows:</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Irregular.xml")  
Dim configParameters As IEnumerable(Of XElement) = _  
    root.<Customer>.<Config>.<ConfigParameter>  
For Each cp As XElement In configParameters  
    Console.WriteLine(cp)  
Next  
```  
  
 <span data-ttu-id="ae1e6-116">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="ae1e6-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="ae1e6-117">示例</span><span class="sxs-lookup"><span data-stu-id="ae1e6-117">Example</span></span>  
 <span data-ttu-id="ae1e6-118">下面的示例演示针对命名空间中的 XML 的相同技术。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="ae1e6-119">有关详细信息，请参阅[处理 XML 命名空间 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-119">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="ae1e6-120">此示例使用下面的 XML 文档︰[示例 XML 文件︰ 多个采购订单中 Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="ae1e6-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim purchaseOrders As XElement = XElement.Load("PurchaseOrdersInNamespace.xml")  
        Dim names As IEnumerable(Of XElement) = _  
            From el In purchaseOrders.<aw:PurchaseOrder>.<aw:Address>.<aw:Name> _  
            Select el  
        For Each e As XElement In names  
            Console.WriteLine(e)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="ae1e6-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="ae1e6-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="ae1e6-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ae1e6-122">See Also</span></span>  
 [<span data-ttu-id="ae1e6-123">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ae1e6-123">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
