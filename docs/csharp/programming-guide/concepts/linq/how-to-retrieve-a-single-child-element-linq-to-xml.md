---
title: "如何：检索单个子元素 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: ce37db9e-76fa-46eb-b4cc-e8f32d22ad90
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 722a6b6630fd08a328a26dcef4d72a8cdd817924
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-c"></a><span data-ttu-id="a4268-102">如何：检索单个子元素 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="a4268-102">How to: Retrieve a Single Child Element (LINQ to XML) (C#)</span></span>
<span data-ttu-id="a4268-103">本主题说明如何在给定子元素名称的情况下检索单个子元素。</span><span class="sxs-lookup"><span data-stu-id="a4268-103">This topic explains how to retrieve a single child element, given the name of the child element.</span></span> <span data-ttu-id="a4268-104">如果知道子元素的名称并且只有一个元素具有此名称，则只检索一个元素而不是一个集合会很方便。</span><span class="sxs-lookup"><span data-stu-id="a4268-104">When you know the name of the child element and that there is only one element that has this name, it can be convenient to retrieve just one element, instead of a collection.</span></span>  
  
 <span data-ttu-id="a4268-105"><xref:System.Xml.Linq.XContainer.Element%2A> 方法返回具有指定 <xref:System.Xml.Linq.XElement> 的第一个子 <xref:System.Xml.Linq.XName>。</span><span class="sxs-lookup"><span data-stu-id="a4268-105">The <xref:System.Xml.Linq.XContainer.Element%2A> method returns the first child <xref:System.Xml.Linq.XElement> with the specified <xref:System.Xml.Linq.XName>.</span></span>  
  
 <span data-ttu-id="a4268-106">如果想要在 Visual Basic 中检索单个子元素，常用的方法是使用 XML 属性，然后使用数组索引器表示法检索第一个元素。</span><span class="sxs-lookup"><span data-stu-id="a4268-106">If you want to retrieve a single child element in Visual Basic, a common approach is to use the XML property, and then retrieve the first element using array indexer notation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a4268-107">示例</span><span class="sxs-lookup"><span data-stu-id="a4268-107">Example</span></span>  
 <span data-ttu-id="a4268-108">下面的示例演示 <xref:System.Xml.Linq.XContainer.Element%2A> 方法的用法。</span><span class="sxs-lookup"><span data-stu-id="a4268-108">The following example demonstrates the use of the <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span> <span data-ttu-id="a4268-109">本示例采用名为 `po` 的 XML 树并查找名为 `Comment` 的第一个元素。</span><span class="sxs-lookup"><span data-stu-id="a4268-109">This example takes the XML tree named `po` and finds the first element named `Comment`.</span></span>  
  
 <span data-ttu-id="a4268-110">Visual Basic 示例演示如何使用数组索引器表示法来检索单个元素。</span><span class="sxs-lookup"><span data-stu-id="a4268-110">The Visual Basic example shows using array indexer notation to retrieve a single element.</span></span>  
  
 <span data-ttu-id="a4268-111">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="a4268-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
XElement e = po.Element("DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="a4268-112">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="a4268-112">This example produces the following output:</span></span>  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a><span data-ttu-id="a4268-113">示例</span><span class="sxs-lookup"><span data-stu-id="a4268-113">Example</span></span>  
 <span data-ttu-id="a4268-114">下面的示例演示如何对命名空间中的 XML 使用相同的代码。</span><span class="sxs-lookup"><span data-stu-id="a4268-114">The following example shows the same code for XML that is in a namespace.</span></span> <span data-ttu-id="a4268-115">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="a4268-115">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="a4268-116">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的典型采购订单](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="a4268-116">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
XElement e = po.Element(aw + "DeliveryNotes");  
Console.WriteLine(e);  
```  
  
 <span data-ttu-id="a4268-117">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="a4268-117">This example produces the following output:</span></span>  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a4268-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a4268-118">See Also</span></span>  
 [<span data-ttu-id="a4268-119">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="a4268-119">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
