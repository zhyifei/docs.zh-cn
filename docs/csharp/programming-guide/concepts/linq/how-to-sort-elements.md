---
title: 如何：对元素进行排序 (C#)
ms.date: 07/20/2015
ms.assetid: aee6fbbc-81fd-4b3e-b40f-6ed7b3bd3fee
ms.openlocfilehash: 7548f183736ac9ed0ed09d3be775b3ffde6cb255
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "44042603"
---
# <a name="how-to-sort-elements-c"></a><span data-ttu-id="b5d74-102">如何：对元素进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="b5d74-102">How to: Sort Elements (C#)</span></span>
<span data-ttu-id="b5d74-103">本示例演示如何编写对查询结果进行排序的查询。</span><span class="sxs-lookup"><span data-stu-id="b5d74-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b5d74-104">示例</span><span class="sxs-lookup"><span data-stu-id="b5d74-104">Example</span></span>  
 <span data-ttu-id="b5d74-105">本示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d74-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
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
  
 <span data-ttu-id="b5d74-106">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="b5d74-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="b5d74-107">示例</span><span class="sxs-lookup"><span data-stu-id="b5d74-107">Example</span></span>  
 <span data-ttu-id="b5d74-108">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="b5d74-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="b5d74-109">有关详细信息，请参阅[使用 XML 命名空间 (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d74-109">For more information, see [Working with XML Namespaces (C#)](../../../../csharp/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="b5d74-110">本示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的数值数据](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="b5d74-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
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
  
 <span data-ttu-id="b5d74-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="b5d74-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="b5d74-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="b5d74-112">See Also</span></span>

- [<span data-ttu-id="b5d74-113">对数据进行排序 (C#)</span><span class="sxs-lookup"><span data-stu-id="b5d74-113">Sorting Data (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/sorting-data.md)  
- [<span data-ttu-id="b5d74-114">基本查询 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="b5d74-114">Basic Queries (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
