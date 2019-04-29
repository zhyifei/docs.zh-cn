---
title: 如何：查找具有特定子元素的元素 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: b0d0a463-6a85-46c3-8453-ad25b0ecf93c
ms.openlocfilehash: 1b226f009776f397f73ab9ee7826484eb8869f28
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61780596"
---
# <a name="how-to-find-an-element-with-a-specific-child-element-visual-basic"></a><span data-ttu-id="36367-102">如何：查找具有特定子元素的元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36367-102">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>
<span data-ttu-id="36367-103">本主题演示如何查找特定元素，该特定元素包含具有特定值的子元素。</span><span class="sxs-lookup"><span data-stu-id="36367-103">This topic shows how to find a particular element that has a child element with a specific value.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36367-104">示例</span><span class="sxs-lookup"><span data-stu-id="36367-104">Example</span></span>  
 <span data-ttu-id="36367-105">示例查找 `Test` 元素，该元素包含具有值为“Examp2.EXE”的 `CommandLine` 子元素。</span><span class="sxs-lookup"><span data-stu-id="36367-105">The example finds the `Test` element that has a `CommandLine` child element with the value of "Examp2.EXE".</span></span>  
  
 <span data-ttu-id="36367-106">此示例使用下面的 XML 文档：[示例 XML 文件：测试配置 (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="36367-106">This example uses the following XML document: [Sample XML File: Test Configuration (LINQ to XML)](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-linq-to-xml.md).</span></span>  
  
```vb  
Dim root As XElement = XElement.Load("TestConfig.xml")  
Dim tests As IEnumerable(Of XElement) = _  
    From el In root.<Test> _  
    Where el.<CommandLine>.Value = "Examp2.EXE" _  
    Select el  
For Each el as XElement In tests  
    Console.WriteLine(el.@TestId)  
Next  
```  
  
 <span data-ttu-id="36367-107">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="36367-107">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
 <span data-ttu-id="36367-108">请注意，此示例中使用[XML 子轴属性](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)，则[XML 特性轴属性](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)，并[XML 值属性](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)。</span><span class="sxs-lookup"><span data-stu-id="36367-108">Note that this example uses the [XML Child axis property](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md), the [XML Attribute axis property](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md), and the [XML Value property](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="36367-109">示例</span><span class="sxs-lookup"><span data-stu-id="36367-109">Example</span></span>  
 <span data-ttu-id="36367-110">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="36367-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="36367-111">有关详细信息，请参阅[使用 XML 命名空间 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="36367-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
 <span data-ttu-id="36367-112">此示例使用下面的 XML 文档：[示例 XML 文件：命名空间中的测试配置](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md)。</span><span class="sxs-lookup"><span data-stu-id="36367-112">This example uses the following XML document: [Sample XML File: Test Configuration in a Namespace](../../../../visual-basic/programming-guide/concepts/linq/sample-xml-file-test-configuration-in-a-namespace.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = XElement.Load("TestConfigInNamespace.xml")  
        Dim tests As IEnumerable(Of XElement) = _  
            From el In root.<Test> _  
            Where el.<CommandLine>.Value = "Examp2.EXE" _  
            Select el  
        For Each el As XElement In tests  
            Console.WriteLine(el.@TestId)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="36367-113">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="36367-113">This code produces the following output:</span></span>  
  
```  
0002  
0006  
```  
  
## <a name="see-also"></a><span data-ttu-id="36367-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="36367-114">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A>
- <xref:System.Xml.Linq.XContainer.Elements%2A>
- [<span data-ttu-id="36367-115">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36367-115">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="36367-116">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36367-116">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="36367-117">投影运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="36367-117">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
