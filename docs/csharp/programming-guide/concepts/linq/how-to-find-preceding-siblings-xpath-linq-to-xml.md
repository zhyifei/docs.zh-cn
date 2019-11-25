---
title: 如何查找前面的同级 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: b281ff99-d08a-43d0-bea1-eff831b2f8ae
ms.openlocfilehash: 08fc2073f76f37bd0381a05a7969d1c7748d6252
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141058"
---
# <a name="how-to-find-preceding-siblings-xpath-linq-to-xml-c"></a><span data-ttu-id="0e48c-102">如何查找前面的同级 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="0e48c-102">How to find preceding siblings (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="0e48c-103">本主题将 XPath `preceding-sibling` 轴与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 子 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> 轴进行比较。</span><span class="sxs-lookup"><span data-stu-id="0e48c-103">This topic compares the XPath `preceding-sibling` axis to the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] child <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> axis.</span></span>  
  
 <span data-ttu-id="0e48c-104">XPath 表达式为：</span><span class="sxs-lookup"><span data-stu-id="0e48c-104">The XPath expression is:</span></span>  
  
 `preceding-sibling::*`  
  
 <span data-ttu-id="0e48c-105">请注意，<xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> 和 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> 的结果都遵循文档顺序。</span><span class="sxs-lookup"><span data-stu-id="0e48c-105">Note that the results of both <xref:System.Xml.XPath.Extensions.XPathSelectElements%2A> and <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A?displayProperty=nameWithType> are in document order.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0e48c-106">示例</span><span class="sxs-lookup"><span data-stu-id="0e48c-106">Example</span></span>  
 <span data-ttu-id="0e48c-107">下面的示例查找 `FullAddress` 元素，然后使用 `preceding-sibling` 轴检索前面的元素。</span><span class="sxs-lookup"><span data-stu-id="0e48c-107">The following example finds the `FullAddress` element, and then retrieves the previous elements using the `preceding-sibling` axis.</span></span>  
  
 <span data-ttu-id="0e48c-108">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md)。</span><span class="sxs-lookup"><span data-stu-id="0e48c-108">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](./sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement co = XElement.Load("CustomersOrders.xml");  
  
XElement add = co.Element("Customers").Element("Customer").Element("FullAddress");  
  
// LINQ to XML query  
IEnumerable<XElement> list1 = add.ElementsBeforeSelf();  
  
// XPath expression  
IEnumerable<XElement> list2 = add.XPathSelectElements("preceding-sibling::*");  
  
if (list1.Count() == list2.Count() &&  
        list1.Intersect(list2).Count() == list1.Count())  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
foreach (XElement el in list2)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="0e48c-109">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="0e48c-109">This example produces the following output:</span></span>  
  
```output  
Results are identical  
<CompanyName>Great Lakes Food Market</CompanyName>  
<ContactName>Howard Snyder</ContactName>  
<ContactTitle>Marketing Manager</ContactTitle>  
<Phone>(503) 555-7555</Phone>  
```  
