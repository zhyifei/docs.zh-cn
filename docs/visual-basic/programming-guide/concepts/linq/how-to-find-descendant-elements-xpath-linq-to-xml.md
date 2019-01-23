---
title: 如何：查找子代元素 (XPATH-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: e7e2dc9e-bda9-420d-a5b1-4fabf1cca46b
ms.openlocfilehash: ea92a224ee5cc976b9bd93f8ac8792a67d360fae
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54578674"
---
# <a name="how-to-find-descendant-elements-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="a190e-102">如何：查找子代元素 (XPATH-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a190e-102">How to: Find Descendant Elements (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="a190e-103">本主题演示如何获取具有特定名称的后代元素。</span><span class="sxs-lookup"><span data-stu-id="a190e-103">This topic shows how to get the descendant elements with a particular name.</span></span>  
  
 <span data-ttu-id="a190e-104">XPath 表达式为 `//Name`。</span><span class="sxs-lookup"><span data-stu-id="a190e-104">The XPath expression is `//Name`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a190e-105">示例</span><span class="sxs-lookup"><span data-stu-id="a190e-105">Example</span></span>  
 <span data-ttu-id="a190e-106">本示例查找名为 `Name` 的所有后代。</span><span class="sxs-lookup"><span data-stu-id="a190e-106">This example finds all descendants named `Name`.</span></span>  
  
 <span data-ttu-id="a190e-107">本示例使用下面的 XML 文档：[示例 XML 文件：多个采购订单 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="a190e-107">This example uses the following XML document: [Sample XML File: Multiple Purchase Orders (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-multiple-purchase-orders-linq-to-xml.md).</span></span>  
  
```vb  
      Dim po As XDocument = XDocument.Load("PurchaseOrders.xml")  
  
' LINQ to XML query  
Dim list1 As IEnumerable(Of XElement) = po...<Name>  
  
' XPath expression  
Dim list2 As IEnumerable(Of XElement) = po.XPathSelectElements("//Name")  
  
If (list1.Count() = list2.Count() And _  
        list1.Intersect(list2).Count() = list1.Count()) Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
For Each el As XElement In list1  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="a190e-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="a190e-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Name>Ellen Adams</Name>  
<Name>Tai Yee</Name>  
<Name>Cristian Osorio</Name>  
<Name>Cristian Osorio</Name>  
<Name>Jessica Arnold</Name>  
<Name>Jessica Arnold</Name>  
```  
  
## <a name="see-also"></a><span data-ttu-id="a190e-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="a190e-109">See also</span></span>
- [<span data-ttu-id="a190e-110">LINQ to XML 针对 XPath 用户 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a190e-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
