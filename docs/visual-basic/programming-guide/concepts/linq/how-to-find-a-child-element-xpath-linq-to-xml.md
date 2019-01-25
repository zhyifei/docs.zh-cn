---
title: 如何：查找子元素 (XPATH-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: adb46c98-a650-42e2-b62d-835920fe8421
ms.openlocfilehash: 8472a3d9e90aa117c936c4314204f70d2ab33487
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54495807"
---
# <a name="how-to-find-a-child-element-xpath-linq-to-xml-visual-basic"></a>如何：查找子元素 (XPATH-LINQ to XML) (Visual Basic)
本主题将 XPath 子元素轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] <xref:System.Xml.Linq.XContainer.Element%2A> 方法进行比较。  
  
 XPath 表达式为 `DeliveryNotes`。  
  
## <a name="example"></a>示例  
 本示例查找子元素 `DeliveryNotes`。  
  
 本示例使用下面的 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。  
  
```vb  
Dim cpo As XDocument = XDocument.Load("PurchaseOrders.xml")  
Dim po As XElement = cpo.Root.<PurchaseOrder>.FirstOrDefault  
  
'LINQ to XML query  
Dim el1 As XElement = po.<DeliveryNotes>.FirstOrDefault  
  
' XPath expression  
Dim el2 As XElement = po.XPathSelectElement("DeliveryNotes")  
' same as "child::DeliveryNotes"  
' same as "./DeliveryNotes"  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 该示例产生下面的输出：  
  
```  
Results are identical  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="see-also"></a>请参阅
- [LINQ to XML 针对 XPath 用户 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
