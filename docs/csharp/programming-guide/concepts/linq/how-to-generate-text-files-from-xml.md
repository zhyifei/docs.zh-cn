---
title: 如何：从 XML 生成文本文件 (C#)
ms.date: 07/20/2015
ms.assetid: 9ad283f7-7cac-42ff-bf32-92aa866e6883
ms.openlocfilehash: 05d1edfc236bf7fa9a6e2fffd270384d3ce1aaec
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33316473"
---
# <a name="how-to-generate-text-files-from-xml-c"></a><span data-ttu-id="2911c-102">如何：从 XML 生成文本文件 (C#)</span><span class="sxs-lookup"><span data-stu-id="2911c-102">How to: Generate Text Files from XML (C#)</span></span>
<span data-ttu-id="2911c-103">本示例演示如何从 XML 文件生成逗号分隔值 (CSV) 文件。</span><span class="sxs-lookup"><span data-stu-id="2911c-103">This example shows how to generate a comma-separated values (CSV) file from an XML file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2911c-104">示例</span><span class="sxs-lookup"><span data-stu-id="2911c-104">Example</span></span>  
 <span data-ttu-id="2911c-105">本示例的 C# 版本使用方法语法和 `Aggregate` 运算符通过一个表达式从 XML 文档生成 CSV 文件。</span><span class="sxs-lookup"><span data-stu-id="2911c-105">The C# version of this example uses method syntax and the `Aggregate` operator to generate a CSV file from an XML document in a single expression.</span></span> <span data-ttu-id="2911c-106">有关详细信息，请参阅 [LINQ 中的查询语法和方法语法](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md)。</span><span class="sxs-lookup"><span data-stu-id="2911c-106">For more information, see [Query Syntax and Method Syntax in LINQ](../../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).</span></span>  
  
 <span data-ttu-id="2911c-107">本示例使用下面的 XML 文档：[示例 XML 文件：客户和订单 (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md)。</span><span class="sxs-lookup"><span data-stu-id="2911c-107">This example uses the following XML document: [Sample XML File: Customers and Orders (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/sample-xml-file-customers-and-orders-linq-to-xml-2.md).</span></span>  
  
```csharp  
XElement custOrd = XElement.Load("CustomersOrders.xml");  
string csv =  
    (from el in custOrd.Element("Customers").Elements("Customer")  
    select  
        String.Format("{0},{1},{2},{3},{4},{5},{6},{7},{8},{9}{10}",  
            (string)el.Attribute("CustomerID"),  
            (string)el.Element("CompanyName"),  
            (string)el.Element("ContactName"),  
            (string)el.Element("ContactTitle"),  
            (string)el.Element("Phone"),  
            (string)el.Element("FullAddress").Element("Address"),  
            (string)el.Element("FullAddress").Element("City"),  
            (string)el.Element("FullAddress").Element("Region"),  
            (string)el.Element("FullAddress").Element("PostalCode"),  
            (string)el.Element("FullAddress").Element("Country"),  
            Environment.NewLine  
        )  
    )  
    .Aggregate(  
        new StringBuilder(),  
        (sb, s) => sb.Append(s),  
        sb => sb.ToString()  
    );  
Console.WriteLine(csv);  
```  
  
 <span data-ttu-id="2911c-108">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="2911c-108">This code produces the following output:</span></span>  
  
```  
GREAL,Great Lakes Food Market,Howard Snyder,Marketing Manager,(503) 555-7555,2732 Baker Blvd.,Eugene,OR,97403,USA  
HUNGC,Hungry Coyote Import Store,Yoshi Latimer,Sales Representative,(503) 555-6874,City Center Plaza 516 Main St.,Elgin,OR,97827,USA  
LAZYK,Lazy K Kountry Store,John Steel,Marketing Manager,(509) 555-7969,12 Orchestra Terrace,Walla Walla,WA,99362,USA  
LETSS,Let's Stop N Shop,Jaime Yorres,Owner,(415) 555-5938,87 Polk St. Suite 5,San Francisco,CA,94117,USA  
```  
  
## <a name="see-also"></a><span data-ttu-id="2911c-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="2911c-109">See Also</span></span>  
 [<span data-ttu-id="2911c-110">投影和转换 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="2911c-110">Projections and Transformations (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/projections-and-transformations-linq-to-xml.md)
