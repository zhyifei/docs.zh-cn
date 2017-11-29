---
title: "如何： 检索单个子元素 (LINQ to XML) (Visual Basic)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0033e258-d9c4-4569-86f6-79b7c06d1204
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 580315fda6ef6f1919f7f2aabc0cf3604a5c4337
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-retrieve-a-single-child-element-linq-to-xml-visual-basic"></a>如何： 检索单个子元素 (LINQ to XML) (Visual Basic)
本主题说明如何在给定子元素名称的情况下检索单个子元素。 如果知道子元素的名称并且只有一个元素具有此名称，则只检索一个元素而不是一个集合会很方便。  
  
 <xref:System.Xml.Linq.XContainer.Element%2A> 方法返回具有指定 <xref:System.Xml.Linq.XElement> 的第一个子 <xref:System.Xml.Linq.XName>。  
  
 如果想要在 Visual Basic 中检索单个子元素，常用的方法是使用 XML 属性，然后使用数组索引器表示法检索第一个元素。  
  
## <a name="example"></a>示例  
 下面的示例演示 <xref:System.Xml.Linq.XContainer.Element%2A> 方法的用法。 本示例采用名为 `po` 的 XML 树并查找名为 `Comment` 的第一个元素。  
  
 Visual Basic 示例演示如何使用数组索引器表示法来检索单个元素。  
  
 本示例使用以下 XML 文档：[示例 XML 文件：典型采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-linq-to-xml.md)。  
  
```vb  
Dim po As XElement = XElement.Load("PurchaseOrder.xml")  
Dim e As XElement = po.<DeliveryNotes>(0)  
Console.WriteLine(e)  
```  
  
 该示例产生下面的输出：  
  
```xml  
<DeliveryNotes>Please leave packages in shed by driveway.</DeliveryNotes>  
```  
  
## <a name="example"></a>示例  
 下面的示例演示如何对命名空间中的 XML 使用相同的代码。 有关详细信息，请参阅[处理 XML 命名空间 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。  
  
 本示例使用以下 XML 文档：[示例 XML 文件：命名空间中的典型采购订单](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-typical-purchase-order-in-a-namespace.md)。  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim po As XElement = XElement.Load("PurchaseOrderInNamespace.xml")  
        Dim e As XElement = po.<aw:DeliveryNotes>(0)  
        Console.WriteLine(e)  
    End Sub  
End Module  
```  
  
 该示例产生下面的输出：  
  
```xml  
<aw:DeliveryNotes xmlns:aw="http://www.adventure-works.com">Please leave packages in shed by driveway.</aw:DeliveryNotes>  
```  
  
## <a name="see-also"></a>另请参阅  
 [LINQ to XML 轴 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
