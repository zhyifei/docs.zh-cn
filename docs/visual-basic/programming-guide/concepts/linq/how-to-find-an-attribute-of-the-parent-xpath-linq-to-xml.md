---
title: 如何：查找父 (XPATH-LINQ to XML) 的属性 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ded20c173063492d260aee5ba55f3c4c585bd961
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828649"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="4ebcb-102">如何：查找父 (XPATH-LINQ to XML) 的属性 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ebcb-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="4ebcb-103">本主题演示如何定位到父元素并查找其属性。</span><span class="sxs-lookup"><span data-stu-id="4ebcb-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="4ebcb-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="4ebcb-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="4ebcb-105">示例</span><span class="sxs-lookup"><span data-stu-id="4ebcb-105">Example</span></span>  
 <span data-ttu-id="4ebcb-106">此示例首先查找 `Author` 元素。</span><span class="sxs-lookup"><span data-stu-id="4ebcb-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="4ebcb-107">然后，查找父元素的 `id` 属性。</span><span class="sxs-lookup"><span data-stu-id="4ebcb-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="4ebcb-108">此示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="4ebcb-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```vb  
Dim books As XDocument = XDocument.Load("Books.xml")  
Dim author As XElement = books.Root.<Book>.<Author>.FirstOrDefault()  
  
' LINQ to XML query  
Dim att1 As XAttribute = author.Parent.Attribute("id")  
  
' XPath expression  
Dim att2 As XAttribute = DirectCast(author.XPathEvaluate("../@id"),  _  
    IEnumerable).Cast(Of XAttribute)().First()  
  
If att1 Is att2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(att1)  
```  
  
 <span data-ttu-id="4ebcb-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="4ebcb-109">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ebcb-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4ebcb-110">See also</span></span>

- [<span data-ttu-id="4ebcb-111">LINQ to XML 针对 XPath 用户 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4ebcb-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
