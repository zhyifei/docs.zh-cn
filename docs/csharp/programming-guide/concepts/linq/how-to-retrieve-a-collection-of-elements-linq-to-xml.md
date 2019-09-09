---
title: 如何：检索元素集合 (LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b849668c-7976-4974-b8e1-1cd587d34258
ms.openlocfilehash: fef12745bd608622f071f72049f242405d17ed7d
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70253424"
---
# <a name="how-to-retrieve-a-collection-of-elements-linq-to-xml-c"></a>如何：检索元素集合 (LINQ to XML) (C#)
本主题演示 <xref:System.Xml.Linq.XContainer.Elements%2A> 方法。 此方法检索元素的子元素集合。  
  
## <a name="example"></a>示例  
 本示例循环访问 `purchaseOrder` 元素的子元素。  
  
 此示例使用下面的 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](./sample-xml-file-typical-purchase-order-linq-to-xml-1.md)。  
  
```csharp  
XElement po = XElement.Load("PurchaseOrder.xml");  
IEnumerable<XElement> childElements =  
    from el in po.Elements()  
    select el;  
foreach (XElement el in childElements)  
    Console.WriteLine("Name: " + el.Name);  
```  
  
 本示例生成以下输出。  
  
```output  
Name: Address  
Name: Address  
Name: DeliveryNotes  
Name: Items  
```  
  
## <a name="see-also"></a>请参阅

- [LINQ to XML 轴 (C#)](./linq-to-xml-axes-overview.md)
