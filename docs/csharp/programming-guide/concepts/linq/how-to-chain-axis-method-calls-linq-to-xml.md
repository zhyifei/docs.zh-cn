---
title: "如何：链接轴方法调用 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 067e6da2-ee32-486d-803c-e611b328e39a
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 17793e0620969125de202de7edea89d748b98ee7
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-chain-axis-method-calls-linq-to-xml-c"></a><span data-ttu-id="91e3b-102">如何：链接轴方法调用 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="91e3b-102">How to: Chain Axis Method Calls (LINQ to XML) (C#)</span></span>
<span data-ttu-id="91e3b-103">一个在代码中常用的模式是调用轴方法，然后调用一个扩展方法轴。</span><span class="sxs-lookup"><span data-stu-id="91e3b-103">A common pattern that you will use in your code is to call an axis method, then call one of the extension method axes.</span></span>  
  
 <span data-ttu-id="91e3b-104">有两个返回元素集合、名称为 `Elements` 的轴：<xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> 方法和 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="91e3b-104">There are two axes with the name of `Elements` that return a collection of elements: the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method and the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method.</span></span> <span data-ttu-id="91e3b-105">可以合并这两个轴，在树的给定深度，查找具有指定名称的所有元素。</span><span class="sxs-lookup"><span data-stu-id="91e3b-105">You can combine these two axes to find all elements of a specified name at a given depth in the tree.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91e3b-106">示例</span><span class="sxs-lookup"><span data-stu-id="91e3b-106">Example</span></span>  
 <span data-ttu-id="91e3b-107">本示例使用 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> 和 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> 在所有 `Name` 元素中查找所有 `Address` 元素中的所有 `PurchaseOrder` 元素。</span><span class="sxs-lookup"><span data-stu-id="91e3b-107">This example uses <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> and <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> to find all `Name` elements in all `Address` elements in all `PurchaseOrder` elements.</span></span>  
  
 <span data-ttu-id="91e3b-108">本示例使用以下 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="91e3b-108">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XElement purchaseOrders = XElement.Load("PurchaseOrders.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements("PurchaseOrder")  
        .Elements("Address")  
        .Elements("Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="91e3b-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="91e3b-109">This example produces the following output:</span></span>  
  
```xml  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
 <span data-ttu-id="91e3b-110">此方法有效是因为其中有一个 `Elements` 轴实现充当 <xref:System.Collections.Generic.IEnumerable%601> 的 <xref:System.Xml.Linq.XContainer> 的扩展方法。</span><span class="sxs-lookup"><span data-stu-id="91e3b-110">This works because one of the implementations of the `Elements` axis is as an extension method on <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XContainer>.</span></span> <span data-ttu-id="91e3b-111"><xref:System.Xml.Linq.XElement> 是从 <xref:System.Xml.Linq.XContainer> 派生的，因此可以对调用 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> 方法的结果调用 <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> 方法。</span><span class="sxs-lookup"><span data-stu-id="91e3b-111"><xref:System.Xml.Linq.XElement> derives from <xref:System.Xml.Linq.XContainer>, so you can call the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> method on the results of a call to the <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="example"></a><span data-ttu-id="91e3b-112">示例</span><span class="sxs-lookup"><span data-stu-id="91e3b-112">Example</span></span>  
 <span data-ttu-id="91e3b-113">有时，当可能存在或不存在间隔上级时，您希望在特定的元素深度，检索所有的元素。</span><span class="sxs-lookup"><span data-stu-id="91e3b-113">Sometimes you want to retrieve all elements at a particular element depth when there might or might not be intervening ancestors.</span></span> <span data-ttu-id="91e3b-114">例如，在下面的文档中，您可能要检索属于 `ConfigParameter` 元素的子元素的所有 `Customer` 元素，而不是属于 `ConfigParameter` 元素的子元素的 `Root`。</span><span class="sxs-lookup"><span data-stu-id="91e3b-114">For example, in the following document, you might want to retrieve all the `ConfigParameter` elements that are children of the `Customer` element, but not the `ConfigParameter` that is a child of the `Root` element.</span></span>  
  
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
  
 <span data-ttu-id="91e3b-115">若要执行此操作，您可以使用 <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> 轴，如下所示：</span><span class="sxs-lookup"><span data-stu-id="91e3b-115">To do this, you can use the <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=fullName> axis, as follows:</span></span>  
  
```csharp  
XElement root = XElement.Load("Irregular.xml");  
IEnumerable<XElement> configParameters =   
    root.Elements("Customer").Elements("Config").  
    Elements("ConfigParameter");  
foreach (XElement cp in configParameters)  
    Console.WriteLine(cp);  
```  
  
 <span data-ttu-id="91e3b-116">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="91e3b-116">This example produces the following output:</span></span>  
  
```xml  
<ConfigParameter>FirstConfigParameter</ConfigParameter>  
<ConfigParameter>SecondConfigParameter</ConfigParameter>  
```  
  
## <a name="example"></a><span data-ttu-id="91e3b-117">示例</span><span class="sxs-lookup"><span data-stu-id="91e3b-117">Example</span></span>  
 <span data-ttu-id="91e3b-118">下面的示例演示针对命名空间中的 XML 的相同技术。</span><span class="sxs-lookup"><span data-stu-id="91e3b-118">The following example shows the same technique for XML that is in a namespace.</span></span> <span data-ttu-id="91e3b-119">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="91e3b-119">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="91e3b-120">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的多个采购订单](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="91e3b-120">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-in-a-namespace.md).</span></span>  
  
```csharp  
XNamespace aw = "http://www.adventure-works.com";  
XElement purchaseOrders = XElement.Load("PurchaseOrdersInNamespace.xml");  
IEnumerable<XElement> names =  
    from el in purchaseOrders  
        .Elements(aw + "PurchaseOrder")  
        .Elements(aw + "Address")  
        .Elements(aw + "Name")  
    select el;  
foreach (XElement e in names)  
    Console.WriteLine(e);  
```  
  
 <span data-ttu-id="91e3b-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="91e3b-121">This example produces the following output:</span></span>  
  
```xml  
<aw:Name xmlns:aw="http://www.adventure-works.com">Ellen Adams</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Tai Yee</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Cristian Osorio</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
<aw:Name xmlns:aw="http://www.adventure-works.com">Jessica Arnold</aw:Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="91e3b-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="91e3b-122">See Also</span></span>  
 [<span data-ttu-id="91e3b-123">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="91e3b-123">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)

