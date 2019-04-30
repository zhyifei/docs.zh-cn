---
title: 如何：检索集合的元素 (LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2269f9de-8fb9-4666-b8a1-a4e754fa6a81
ms.openlocfilehash: 53572ac3c80e012b95527d32da28c8685cd8cfd3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62021370"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-visual-basic"></a><span data-ttu-id="4a6e5-102">如何：检索集合的元素 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a6e5-102">How to: Retrieve a Collection of Elements (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4a6e5-103">本主题演示 <xref:System.Xml.Linq.XContainer.Elements%2A> 方法。</span><span class="sxs-lookup"><span data-stu-id="4a6e5-103">This topic demonstrates the <xref:System.Xml.Linq.XContainer.Elements%2A> method.</span></span> <span data-ttu-id="4a6e5-104">此方法检索元素的子元素集合。</span><span class="sxs-lookup"><span data-stu-id="4a6e5-104">This method retrieves a collection of the child elements of an element.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a6e5-105">示例</span><span class="sxs-lookup"><span data-stu-id="4a6e5-105">Example</span></span>  
 <span data-ttu-id="4a6e5-106">本示例循环访问 `purchaseOrder` 元素的子元素。</span><span class="sxs-lookup"><span data-stu-id="4a6e5-106">This example iterates through the child elements of the `purchaseOrder` element.</span></span>  
  
 <span data-ttu-id="4a6e5-107">此示例使用下面的 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="4a6e5-107">This example uses the following XML document: [Sample XML File: Typical Purchase Order (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim childElements As IEnumerable(Of XElement)  
childElements = _  
    From el In po.Elements() _  
    Select el  
For Each el As XElement In childElements  
    Console.WriteLine("Name: " & el.Name.ToString())  
Next  
```  
  
 <span data-ttu-id="4a6e5-108">本示例生成以下输出。</span><span class="sxs-lookup"><span data-stu-id="4a6e5-108">This example produces the following output.</span></span>  
  
```  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a><span data-ttu-id="4a6e5-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="4a6e5-109">See also</span></span>

- [<span data-ttu-id="4a6e5-110">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4a6e5-110">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
