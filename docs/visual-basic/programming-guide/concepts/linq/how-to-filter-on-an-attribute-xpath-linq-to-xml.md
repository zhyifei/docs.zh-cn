---
title: 如何： 筛选特性 (XPATH-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ffefb9d6-45ec-4677-a396-dd9c2b36298f
ms.openlocfilehash: ed9869045270cdc51388b192e8d6ab38005eba8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33641076"
---
# <a name="how-to-filter-on-an-attribute-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="38bc0-102">如何： 筛选特性 (XPATH-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38bc0-102">How to: Filter on an Attribute (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="38bc0-103">本主题演示如何获取具有指定名称、并具有一个带指定值的属性的子代元素。</span><span class="sxs-lookup"><span data-stu-id="38bc0-103">This topic shows how to get the descendant elements with a specified name, and with an attribute with a specified value.</span></span>  
  
 <span data-ttu-id="38bc0-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="38bc0-104">The XPath expression is:</span></span>  
  
 `.//Address[@Type='Shipping']`  
  
## <a name="example"></a><span data-ttu-id="38bc0-105">示例</span><span class="sxs-lookup"><span data-stu-id="38bc0-105">Example</span></span>  
 <span data-ttu-id="38bc0-106">本示例查找名称为 `Address`，`Type`、并具有一个带“Shipping”值的属性的子代元素。</span><span class="sxs-lookup"><span data-stu-id="38bc0-106">This example finds all descendants elements with the name of `Address`, and with a `Type` attribute with a value of "Shipping".</span></span>  
  
 <span data-ttu-id="38bc0-107">本示例使用以下 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="38bc0-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = _  
    From el In po...<Address> _  
    Where el.@Type = "Shipping" _  
    Select el  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = _  
    po.XPathSelectElements(".//Address[@Type='Shipping']")  
  
If (list1.Count = list2.Count And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="38bc0-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="38bc0-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Address Type="Shipping">  
  <Name>Ellen Adams</Name>  
  <Street>123 Maple Street</Street>  
  <City>Mill Valley</City>  
  <State>CA</State>  
  <Zip>10999</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Cristian Osorio</Name>  
  <Street>456 Main Street</Street>  
  <City>Buffalo</City>  
  <State>NY</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
<Address Type="Shipping">  
  <Name>Jessica Arnold</Name>  
  <Street>4055 Madison Ave</Street>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98112</Zip>  
  <Country>USA</Country>  
</Address>  
```  
  
## <a name="see-also"></a><span data-ttu-id="38bc0-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="38bc0-109">See Also</span></span>  
 [<span data-ttu-id="38bc0-110">LINQ to XML 针对 XPath 用户 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="38bc0-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
