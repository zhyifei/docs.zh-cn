---
title: 如何：计算中间值 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 933a97b2-dfe7-4f4d-94ad-e6e20df84abd
ms.openlocfilehash: cb619784d487ae12b1fb8bb3adc97acb0f767455
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/18/2019
ms.locfileid: "58827037"
---
# <a name="how-to-calculate-intermediate-values-visual-basic"></a><span data-ttu-id="0f362-102">如何：计算中间值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f362-102">How to: Calculate Intermediate Values (Visual Basic)</span></span>
<span data-ttu-id="0f362-103">本示例演示如何计算可用于进行排序、筛选和选择的中间值。</span><span class="sxs-lookup"><span data-stu-id="0f362-103">This example shows how to calculate intermediate values that can be used in sorting, filtering, and selecting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f362-104">示例</span><span class="sxs-lookup"><span data-stu-id="0f362-104">Example</span></span>  
 <span data-ttu-id="0f362-105">下面的示例使用 `Let` 子句。</span><span class="sxs-lookup"><span data-stu-id="0f362-105">The following example uses the `Let` clause.</span></span>  
  
 <span data-ttu-id="0f362-106">此示例使用下面的 XML 文档：[示例 XML 文件：数值数据 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="0f362-106">This example uses the following XML document: [Sample XML File: Numerical Data (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("Data.xml")  
Dim extensions As IEnumerable(Of Decimal) = _  
    From el In root.<Data> _  
    Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
    Where extension > 25 _  
    Order By extension _  
    Select extension  
For Each ex As Decimal In extensions  
    Console.WriteLine(ex)  
Next  
```  
  
 <span data-ttu-id="0f362-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="0f362-107">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="example"></a><span data-ttu-id="0f362-108">示例</span><span class="sxs-lookup"><span data-stu-id="0f362-108">Example</span></span>  
 <span data-ttu-id="0f362-109">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="0f362-109">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="0f362-110">有关详细信息，请参阅[使用 XML 命名空间 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="0f362-110">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="0f362-111">此示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的数值数据](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="0f362-111">This example uses the following XML document: [Sample XML File: Numerical Data in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-numerical-data-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns="http://www.adatum.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("DataInNamespace.xml")  
        Dim extensions As IEnumerable(Of Decimal) = _  
            From el In root.<Data> _  
            Let extension = CDec(el.<Quantity>.Value) * CDec(el.<Price>.Value) _  
            Where extension > 25 _  
            Order By extension _  
            Select extension  
        For Each ex As Decimal In extensions  
            Console.WriteLine(ex)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="0f362-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="0f362-112">This code produces the following output:</span></span>  
  
```  
55.92  
73.50  
89.99  
198.00  
435.00  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f362-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="0f362-113">See also</span></span>

- [<span data-ttu-id="0f362-114">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0f362-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
