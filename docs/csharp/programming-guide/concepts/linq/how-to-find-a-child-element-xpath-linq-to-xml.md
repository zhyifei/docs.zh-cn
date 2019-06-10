---
title: 如何：查找子元素 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 4fa6182d-6196-4ed1-9c9e-82949ff89c71
ms.openlocfilehash: 4a6d18c86416f7c54df554bc2f518994446a2a84
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66485723"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-c"></a><span data-ttu-id="ecfc9-102">如何：查找子元素 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="ecfc9-102">How to: Find a Child Element (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="ecfc9-103">本主题将 XPath 子元素轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> 方法进行比较。</span><span class="sxs-lookup"><span data-stu-id="ecfc9-103">This topic compares the XPath child element axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> method.</span></span>  
  
 <span data-ttu-id="ecfc9-104">XPath 表达式为 `DeliveryNotes`。</span><span class="sxs-lookup"><span data-stu-id="ecfc9-104">The XPath expression is `DeliveryNotes`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ecfc9-105">示例</span><span class="sxs-lookup"><span data-stu-id="ecfc9-105">Example</span></span>  
 <span data-ttu-id="ecfc9-106">本示例查找子元素 `DeliveryNotes`。</span><span class="sxs-lookup"><span data-stu-id="ecfc9-106">This example finds the child element `DeliveryNotes`.</span></span>  
  
 <span data-ttu-id="ecfc9-107">此示例使用下面的 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="ecfc9-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument cpo = XDocument.Load("PurchaseOrders.xml");  
XElement po = cpo.Root.Element("PurchaseOrder");  
  
// LINQ to XML query  
XElement el1 = po.Element("DeliveryNotes");  
  
// XPath expression  
XElement el2 = po.XPathSelectElement("DeliveryNotes");  
// same as "child::DeliveryNotes"  
// same as "./DeliveryNotes"  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="ecfc9-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="ecfc9-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  