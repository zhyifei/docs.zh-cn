---
title: 如何：筛选可选元素 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: a74b76ad-6889-4185-a189-d6ef2c63841e
ms.openlocfilehash: f2a1c7d4091af80e79a6758bcede8f4ccc753f03
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61855382"
---
# <a name="how-to-filter-on-an-optional-element-visual-basic"></a><span data-ttu-id="d9fe4-102">如何：筛选可选元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9fe4-102">How to: Filter on an Optional Element (Visual Basic)</span></span>
<span data-ttu-id="d9fe4-103">有时，尽管不能确定某个元素是否存在于 XML 文档中，您还是会尝试筛选该元素。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-103">Sometimes you want to filter for an element even though you are not sure it exists in your XML document.</span></span> <span data-ttu-id="d9fe4-104">应当执行搜索，这样如果特定元素没有子元素，就不会因为筛选它而触发空引用异常。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-104">The search should be executed so that if the particular element does not have the child element, you do not trigger a null reference exception by filtering for it.</span></span> <span data-ttu-id="d9fe4-105">在下面的示例中，`Child5` 元素没有 `Type` 子元素，但是查询仍可以正确执行。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-105">In the following example, the `Child5` element does not have a `Type` child element, but the query still executes correctly.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9fe4-106">示例</span><span class="sxs-lookup"><span data-stu-id="d9fe4-106">Example</span></span>  
 <span data-ttu-id="d9fe4-107">本示例使用 <xref:System.Xml.Linq.Extensions.Elements%2A> 扩展方法。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-107">This example uses the <xref:System.Xml.Linq.Extensions.Elements%2A> extension method.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1>  
            <Text>Child One Text</Text>  
            <Type Value="Yes"/>  
        </Child1>  
        <Child2>  
            <Text>Child Two Text</Text>  
            <Type Value="Yes"/>  
        </Child2>  
        <Child3>  
            <Text>Child Three Text</Text>  
            <Type Value="No"/>  
        </Child3>  
        <Child4>  
            <Text>Child Four Text</Text>  
            <Type Value="Yes"/>  
        </Child4>  
        <Child5>  
            <Text>Child Five Text</Text>  
        </Child5>  
    </Root>  
Dim cList As IEnumerable(Of String) = _  
    From typeElement In root.Elements().<Type> _  
    Where typeElement.@Value = "Yes" _  
    Select typeElement.Parent.<Text>.Value  
Dim str As String  
For Each str In cList  
    Console.WriteLine(str)  
Next  
```  
  
 <span data-ttu-id="d9fe4-108">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d9fe4-108">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="example"></a><span data-ttu-id="d9fe4-109">示例</span><span class="sxs-lookup"><span data-stu-id="d9fe4-109">Example</span></span>  
 <span data-ttu-id="d9fe4-110">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-110">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="d9fe4-111">有关详细信息，请参阅[使用 XML 命名空间 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="d9fe4-111">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
                <Child1>  
                    <Text>Child One Text</Text>  
                    <Type Value="Yes"/>  
                </Child1>  
                <Child2>  
                    <Text>Child Two Text</Text>  
                    <Type Value="Yes"/>  
                </Child2>  
                <Child3>  
                    <Text>Child Three Text</Text>  
                    <Type Value="No"/>  
                </Child3>  
                <Child4>  
                    <Text>Child Four Text</Text>  
                    <Type Value="Yes"/>  
                </Child4>  
                <Child5>  
                    <Text>Child Five Text</Text>  
                </Child5>  
            </Root>  
        Dim cList As IEnumerable(Of String) = _  
            From typeElement In root.Elements().<Type> _  
            Where typeElement.@Value = "Yes" _  
            Select typeElement.Parent.<Text>.Value  
        Dim str As String  
        For Each str In cList  
            Console.WriteLine(str)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="d9fe4-112">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="d9fe4-112">This code produces the following output:</span></span>  
  
```  
Child One Text  
Child Two Text  
Child Four Text  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9fe4-113">请参阅</span><span class="sxs-lookup"><span data-stu-id="d9fe4-113">See also</span></span>

- <xref:System.Xml.Linq.XElement.Attribute%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.XContainer.Elements%2A?displayProperty=nameWithType>
- <xref:System.Xml.Linq.Extensions.Elements%2A?displayProperty=nameWithType>
- [<span data-ttu-id="d9fe4-114">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9fe4-114">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
- [<span data-ttu-id="d9fe4-115">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="d9fe4-115">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)
- [<span data-ttu-id="d9fe4-116">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="d9fe4-116">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)
- [<span data-ttu-id="d9fe4-117">XML 值属性</span><span class="sxs-lookup"><span data-stu-id="d9fe4-117">XML Value Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="d9fe4-118">标准查询运算符概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9fe4-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="d9fe4-119">投影运算 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9fe4-119">Projection Operations (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/projection-operations.md)
