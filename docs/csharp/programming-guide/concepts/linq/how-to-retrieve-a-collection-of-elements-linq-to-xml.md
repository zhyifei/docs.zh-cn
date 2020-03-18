---
title: 如何检索元素集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: 89799b17115fb56a93bda5fbc144b21b334a6974
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2020
ms.locfileid: "75345009"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a><span data-ttu-id="580aa-102">如何检索元素集合 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="580aa-102">How to retrieve a collection of elements (LINQ to XML) (C#)</span></span>
<span data-ttu-id="580aa-103">本主题演示 <xref:System.Xml.Linq.XContainer.Elements%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="580aa-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="580aa-104">此方法检索元素的子元素集合。</span><span class="sxs-lookup"><span data-stu-id="580aa-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="580aa-105">示例</span><span class="sxs-lookup"><span data-stu-id="580aa-105">Example</span></span>  
 <span data-ttu-id="580aa-106">本示例循环访问 `purchaseOrder` 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="580aa-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="580aa-107">本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。</span><span class="sxs-lookup"><span data-stu-id="580aa-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md).</span></span>  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 <span data-ttu-id="580aa-108">本示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="580aa-108">This example produces the following output.</span></span>  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="580aa-109">另请参阅</span><span class="sxs-lookup"><span data-stu-id="580aa-109">See also</span></span>

- [<span data-ttu-id="580aa-110">LINQ to XML 轴 (C#)</span><span class="sxs-lookup"><span data-stu-id="580aa-110">LINQ to XML Axes (C#)</span></span>](./linq-to-xml-axes-overview.md)
