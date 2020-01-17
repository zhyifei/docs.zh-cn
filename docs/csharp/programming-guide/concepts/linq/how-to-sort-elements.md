---
title: 如何对元素进行排序 (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7fad9fcb43905072c88a5704c56672917bfc377c
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347367"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="0b21e-102">如何对元素进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="0b21e-102">How to sort elements (C#)</span></span>
<span data-ttu-id="0b21e-103">本示例演示如何编写对查询结果进行排序的查询。</span><span class="sxs-lookup"><span data-stu-id="0b21e-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0b21e-104">示例</span><span class="sxs-lookup"><span data-stu-id="0b21e-104">Example</span></span>  
 <span data-ttu-id="0b21e-105">本示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="0b21e-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](./sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="0b21e-106">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="0b21e-106">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="0b21e-107">示例</span><span class="sxs-lookup"><span data-stu-id="0b21e-107">Example</span></span>  
 <span data-ttu-id="0b21e-108">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="0b21e-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0b21e-109">有关详细信息，请参阅[命名空间概述(LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="0b21e-109">For more information, see [Namespaces Overview (LINQ to XML) (C#)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="0b21e-110">本示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的数值数据](./sample-xml-file-numerical-data-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="0b21e-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](./sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="0b21e-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="0b21e-111">This code produces the following output:</span></span>  
  
```output  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="0b21e-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b21e-112">See also</span></span>

- [<span data-ttu-id="0b21e-113">对数据进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="0b21e-113">Sorting Data (C#)</span></span>](./sorting-data.md)
