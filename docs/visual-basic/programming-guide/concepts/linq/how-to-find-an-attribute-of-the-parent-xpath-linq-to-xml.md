---
title: 如何：查找父级的属性（LINQ to XML）（Visual Basic）
ms.date: 07/20/2015
ms.assetid: 9d2572fd-27d4-426c-b079-16854cb9ec7d
ms.openlocfilehash: ce8fbb828a5ea8df79f449d50f1d61702a4e3df2
ms.sourcegitcommit: d7c298f6c2e3aab0c7498bfafc0a0a94ea1fe23e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/10/2019
ms.locfileid: "72249917"
---
# <a name="how-to-find-an-attribute-of-the-parent-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="f1a55-102">如何：查找父级的属性（LINQ to XML）（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="f1a55-102">How to: Find an Attribute of the Parent (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="f1a55-103">本主题演示如何定位到父元素并查找其属性。</span><span class="sxs-lookup"><span data-stu-id="f1a55-103">This topic shows how to navigate to the parent element and find an attribute of it.</span></span>  
  
 <span data-ttu-id="f1a55-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="f1a55-104">The XPath expression is:</span></span>  
  
 `../@id`  
  
## <a name="example"></a><span data-ttu-id="f1a55-105">示例</span><span class="sxs-lookup"><span data-stu-id="f1a55-105">Example</span></span>  
 <span data-ttu-id="f1a55-106">此示例首先查找 `Author` 元素。</span><span class="sxs-lookup"><span data-stu-id="f1a55-106">This example first finds an `Author` element.</span></span> <span data-ttu-id="f1a55-107">然后，查找父元素的 `id` 属性。</span><span class="sxs-lookup"><span data-stu-id="f1a55-107">It then finds the `id` attribute of the parent element.</span></span>  
  
 <span data-ttu-id="f1a55-108">本示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="f1a55-108">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="f1a55-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="f1a55-109">This example produces the following output:</span></span>  
  
```console  
Results are identical  
id="bk101"  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1a55-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="f1a55-110">See also</span></span>

- [<span data-ttu-id="f1a55-111">XPath 用户的 LINQ to XML （Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="f1a55-111">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
