---
title: 如何：对元素进行排序 (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 074428413fa57d8f0e5ae94970c2aeeeb9e4cc7c
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/19/2019
ms.locfileid: "69592455"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="d80b7-102">如何：对元素进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="d80b7-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="d80b7-103">本示例演示如何编写对查询结果进行排序的查询。</span><span class="sxs-lookup"><span data-stu-id="d80b7-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d80b7-104">示例</span><span class="sxs-lookup"><span data-stu-id="d80b7-104">Example</span></span>  
 <span data-ttu-id="d80b7-105">此示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="d80b7-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("Data.xml");  
IEnumerable<decimal> prices =  
    from el in root.Elements("Data")  
    let price = (decimal)el.Element("Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d80b7-106">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d80b7-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="d80b7-107">示例</span><span class="sxs-lookup"><span data-stu-id="d80b7-107">Example</span></span>  
 <span data-ttu-id="d80b7-108">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="d80b7-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d80b7-109">有关详细信息，请参阅[命名空间概述(LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="d80b7-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="d80b7-110">此示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的数值数据](./sample-xml-file-numerical-data-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="d80b7-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```csharp  
XElement root = XElement.Load("DataInNamespace.xml");  
XNamespace aw = "http://www.adatum.com";  
IEnumerable<decimal> prices =  
    from el in root.Elements(aw + "Data")  
    let price = (decimal)el.Element(aw + "Price")  
    orderby price  
    select price;  
foreach (decimal el in prices)  
    Console.WriteLine(el);  
```  
  
 <span data-ttu-id="d80b7-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d80b7-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="d80b7-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="d80b7-112">See also</span></span>

- [<span data-ttu-id="d80b7-113">对数据进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="d80b7-113">Sorting Data (C#)</span></span>](./sorting-data.md)
