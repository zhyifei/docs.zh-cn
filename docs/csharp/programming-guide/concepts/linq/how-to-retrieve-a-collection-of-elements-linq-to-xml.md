---
title: 如何：检索元素集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 9ad75ce4d3ca113ed432d2b2351067babe33a74f
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43857059"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="64441-102">如何：检索元素集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="64441-102">How to: Retrieve a Collection of Elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="64441-103">本主题演示 <xref:System.Xml.Linq.XContainer.Elements%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="64441-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="64441-104">此方法检索元素的子元素集合。</span><span class="sxs-lookup"><span data-stu-id="64441-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="64441-105">示例</span><span class="sxs-lookup"><span data-stu-id="64441-105">Example</span></span>  
 <span data-ttu-id="64441-106">本示例循环访问 `purchaseOrder` 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="64441-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="64441-107">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="64441-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="64441-108">本示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="64441-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="64441-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="64441-109">See Also</span></span>

- [<span data-ttu-id="64441-110">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="64441-110">LINQ to XML Axes (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-axes.md)
