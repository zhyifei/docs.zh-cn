---
title: "如何：查找具有特定属性的元素 (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: b92591aa-3cfb-490e-99f6-da8de335e362
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4fc7fd7986b79109038bb4f653131d5256c14f04
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-an-element-with-a-specific-attribute-c"></a><span data-ttu-id="cd8e1-102">如何：查找具有特定属性的元素 (C#)</span><span class="sxs-lookup"><span data-stu-id="cd8e1-102">How to: Find an Element with a Specific Attribute (C#)</span></span>
<span data-ttu-id="cd8e1-103">本主题演示如何查找其属性具有特定值的元素。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-103">This topic shows how to find an element that has an attribute that has a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cd8e1-104">示例</span><span class="sxs-lookup"><span data-stu-id="cd8e1-104">Example</span></span>  
 <span data-ttu-id="cd8e1-105">本示例演示如何查找具有值为“Billing”的 `Address` 属性的 `Type` 元素。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-105">The example shows how to find the `Address` element that has a `Type` attribute with a value of "Billing".</span></span>  
  
 <span data-ttu-id="cd8e1-106">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-106">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> address =  
    from el in root.Elements("Address")  
    where (string)el.Attribute("Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cd8e1-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="cd8e1-107">This code produces the following output:</span></span>  
  
```xml  
<Address Type="Billing">  
  <Name>Tai Yee</Name>  
  <Street>8 Oak Avenue</Street>  
  <City>Old Town</City>  
  <State>PA</State>  
  <Zip>95819</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="example"></a><span data-ttu-id="cd8e1-108">示例</span><span class="sxs-lookup"><span data-stu-id="cd8e1-108">Example</span></span>  
 <span data-ttu-id="cd8e1-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="cd8e1-110">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-110">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="cd8e1-111">本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的典型采购订单](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="cd8e1-111">This example uses the following XML document: [Sample XML File: Typical Purchase Order in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("PurchaseOrderInNamespace.xml");  
XNamespace aw = "http://www.adventure-works.com";  
IEnumerable<XElement> address =  
    from el in root.Elements(aw + "Address")  
    where (string)el.Attribute(aw + "Type") == "Billing"  
    select el;  
foreach (XElement el in address)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="cd8e1-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="cd8e1-112">This code produces the following output:</span></span>  
  
```xml  
<aw:Address aw:Type="Billing" xmlns:aw="http://www.adventure-works.com">  
  <aw:Name>Tai Yee</aw:Name>  
  <aw:Street>8 Oak Avenue</aw:Street>  
  <aw:City>Old Town</aw:City>  
  <aw:State>PA</aw:State>  
  <aw:Zip>95819</aw:Zip>  
  <aw:Country>USA</aw:Country>  
</aw:Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="cd8e1-113">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cd8e1-113">See Also</span></span>  
 <xref:System.Xml.Linq.XElement.Attribute%2A>  
 <xref:System.Xml.Linq.XContainer.Elements%2A>  
 [<span data-ttu-id="cd8e1-114">基本查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="cd8e1-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)  
 [<span data-ttu-id="cd8e1-115">标准查询运算符概述 (C#)</span><span class="sxs-lookup"><span data-stu-id="cd8e1-115">Standard Query Operators Overview (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)  
 [<span data-ttu-id="cd8e1-116">投影运算 (C#)</span><span class="sxs-lookup"><span data-stu-id="cd8e1-116">Projection Operations (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projection-operations.md)
