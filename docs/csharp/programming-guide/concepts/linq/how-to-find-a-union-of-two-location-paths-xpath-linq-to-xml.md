---
title: "如何：查找两个位置路径的并集 (XPath-LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 069622d3-2b58-4919-8903-710a564c0788
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 48c5182a32a78dd7f32f73b8180f90c0787e197a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-find-a-union-of-two-location-paths-xpath-linq-to-xml-c"></a><span data-ttu-id="60bc0-102">如何：查找两个位置路径的并集 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="60bc0-102">How to: Find a Union of Two Location Paths (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="60bc0-103">使用 XPath 可以查找两个 XPath 位置路径结果的联合。</span><span class="sxs-lookup"><span data-stu-id="60bc0-103">XPath allows you to find the union of the results of two XPath location paths.</span></span>  
  
 <span data-ttu-id="60bc0-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="60bc0-104">The XPath expression is:</span></span>  
  
 `//Category|//Price`  
  
 <span data-ttu-id="60bc0-105">通过使用 <xref:System.Linq.Enumerable.Concat%2A> 标准查询运算符可以获得相同的结果。</span><span class="sxs-lookup"><span data-stu-id="60bc0-105">You can achieve the same results by using the <xref:System.Linq.Enumerable.Concat%2A> standard query operator.</span></span>  
  
## <a name="example"></a><span data-ttu-id="60bc0-106">示例</span><span class="sxs-lookup"><span data-stu-id="60bc0-106">Example</span></span>  
 <span data-ttu-id="60bc0-107">本示例查找所有 `Category` 元素和所有 `Price` 元素，并将它们连接到单个集合中。</span><span class="sxs-lookup"><span data-stu-id="60bc0-107">This example finds all of the `Category` elements and all of the `Price` elements, and concatenates them into a single collection.</span></span> <span data-ttu-id="60bc0-108">请注意，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询会调用 <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> 以对结果进行排序。</span><span class="sxs-lookup"><span data-stu-id="60bc0-108">Note that the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query calls <xref:System.Xml.Linq.Extensions.InDocumentOrder%2A> to order the results.</span></span> <span data-ttu-id="60bc0-109">XPath 表达式的计算结果也按文档顺序排列。</span><span class="sxs-lookup"><span data-stu-id="60bc0-109">The results of the XPath expression evaluation are also in document order.</span></span>  
  
 <span data-ttu-id="60bc0-110">本示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="60bc0-110">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XDocument data = XDocument.Load("Data.xml");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 =  
    data  
    .Descendants("Category")  
    .Concat(  
        data  
        .Descendants("Price")  
    )  
    .InDocumentOrder();  
  
// XPath expression  
IEnumerable<XElement> list2 = data.XPathSelectElements("//Category|//Price");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list1)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="60bc0-111">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="60bc0-111">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Category>A</Category>  
<Price>24.50</Price>  
<Category>B</Category>  
<Price>89.99</Price>  
<Category>A</Category>  
<Price>4.95</Price>  
<Category>A</Category>  
<Price>66.00</Price>  
<Category>B</Category>  
<Price>.99</Price>  
<Category>A</Category>  
<Price>29.00</Price>  
<Category>B</Category>  
<Price>6.99</Price>  
```  
  
## <a name="see-also"></a><span data-ttu-id="60bc0-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="60bc0-112">See Also</span></span>  
 [<span data-ttu-id="60bc0-113">针对 XPath 用户的 LINQ to XML (C#)</span><span class="sxs-lookup"><span data-stu-id="60bc0-113">LINQ to XML for XPath Users (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
