---
title: 如何：查找具有特定名称的同级属性 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: c3133d64-523f-422d-8838-73d36b945ca0
ms.openlocfilehash: 562f3a40e1670a76778a64570f980326d946a4c2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584670"
---
# <a name="how-to-find-attributes-of-siblings-with-a-specific-name-xpath-linq-to-xml-c"></a><span data-ttu-id="9af33-102">如何：查找具有特定名称的同级属性 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="9af33-102">How to: Find Attributes of Siblings with a Specific Name (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="9af33-103">本主题演示如何查找上下文节点的同级的所有属性。</span><span class="sxs-lookup"><span data-stu-id="9af33-103">This topic shows how to find all attributes of the siblings of the context node.</span></span> <span data-ttu-id="9af33-104">只返回集合中具有特定名称的属性。</span><span class="sxs-lookup"><span data-stu-id="9af33-104">Only attributes with a specific name are returned in the collection.</span></span>  
  
 <span data-ttu-id="9af33-105">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="9af33-105">The XPath expression is:</span></span>  
  
 `../Book/@id`  
  
## <a name="example"></a><span data-ttu-id="9af33-106">示例</span><span class="sxs-lookup"><span data-stu-id="9af33-106">Example</span></span>  
 <span data-ttu-id="9af33-107">本示例首先查找 `Book` 元素，然后查找名为 `Book` 的所有同级元素，再查找名为 `id` 的所有属性。</span><span class="sxs-lookup"><span data-stu-id="9af33-107">This example first finds a `Book` element, and then finds all sibling elements named `Book`, and then finds all attributes named `id`.</span></span> <span data-ttu-id="9af33-108">结果是一个属性集合。</span><span class="sxs-lookup"><span data-stu-id="9af33-108">The result is a collection of attributes.</span></span>  
  
 <span data-ttu-id="9af33-109">本示例使用下面的 XML 文档：[示例 XML 文件：图书 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="9af33-109">This example uses the following XML document: [Sample XML File: Books (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-books-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument books = XDocument.Load("Books.xml");  
  
XElement book =   
    books  
    .Root  
    .Element("Book");  
  
// LINQ to XML query  
IEnumerable<XAttribute> list1 =  
    from el in book.Parent.Elements("Book")  
    select el.Attribute("id");  
  
// XPath expression  
IEnumerable<XAttribute> list2 =  
  ((IEnumerable)book.XPathEvaluate("../Book/@id")).Cast<XAttribute>();  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XAttribute el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="9af33-110">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="9af33-110">This example produces the following output:</span></span>  
  
```  
Results are identical  
id="bk101"  
id="bk102"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9af33-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="9af33-111">See also</span></span>

- [<span data-ttu-id="9af33-112">针对 XPath 用户的 LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="9af33-112">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
