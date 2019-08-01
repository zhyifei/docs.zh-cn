---
title: 如何：排序元素 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: c2c09279-6c8a-482e-8e71-b1453a815052
ms.openlocfilehash: f92d8ca36d1b322bb8d1538fd199e7256c982b85
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/01/2019
ms.locfileid: "68710489"
---
# <a name="how-to-sort-elements-visual-basic"></a><span data-ttu-id="1caa6-102">如何：排序元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1caa6-102">How to: Sort Elements (Visual Basic)</span></span>
<span data-ttu-id="1caa6-103">本示例演示如何编写对查询结果进行排序的查询。</span><span class="sxs-lookup"><span data-stu-id="1caa6-103">This example shows how to write a query that sorts its results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1caa6-104">示例</span><span class="sxs-lookup"><span data-stu-id="1caa6-104">Example</span></span>  
 <span data-ttu-id="1caa6-105">此示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="1caa6-105">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim prices As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let price = Convert.ToDecimal(el.<Price>.Value) _  
    Order By (price) _  
    Select price  
For Each el As Decimal In prices  
    Console.WriteLine(el)  
Next  
```  
  
 <span data-ttu-id="1caa6-106">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="1caa6-106">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="example"></a><span data-ttu-id="1caa6-107">示例</span><span class="sxs-lookup"><span data-stu-id="1caa6-107">Example</span></span>  
 <span data-ttu-id="1caa6-108">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="1caa6-108">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="1caa6-109">有关详细信息, 请参阅[命名空间概述 (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="1caa6-109">For more information, see [Namespaces Overview (LINQ to XML) (Visual Basic)](namespaces-overview-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="1caa6-110">此示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的数值数据](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="1caa6-110">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim prices As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let price = Convert.ToDecimal(el.<Price>.Value) _  
            Order By (price) _  
            Select price  
        For Each el As Decimal In prices  
            Console.WriteLine(el)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="1caa6-111">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="1caa6-111">This code produces the following output:</span></span>  
  
```  
0.99  
4.95  
6.99  
24.50  
29.00  
66.00  
89.99  
```  
  
## <a name="see-also"></a><span data-ttu-id="1caa6-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="1caa6-112">See also</span></span>

- [<span data-ttu-id="1caa6-113">对数据进行排序</span><span class="sxs-lookup"><span data-stu-id="1caa6-113">Sorting Data</span></span>](../../../../visual-basic/programming-guide/concepts/linq/sorting-data.md)
- [<span data-ttu-id="1caa6-114">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1caa6-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
