---
title: 如何：编写基于上下文 (Visual Basic 中) 查找元素的查询
ms.date: 07/20/2015
ms.assetid: 0b085290-ddc1-4126-aaa0-e4c95a3d9a09
ms.openlocfilehash: 4921652b5b9c59f767e0477e26987edaf4655897
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54708137"
---
# <a name="how-to-write-a-query-that-finds-elements-based-on-context-visual-basic"></a><span data-ttu-id="bc791-102">如何：编写基于上下文 (Visual Basic 中) 查找元素的查询</span><span class="sxs-lookup"><span data-stu-id="bc791-102">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>
<span data-ttu-id="bc791-103">有时，您可能必须编写基于元素上下文选择元素的查询。</span><span class="sxs-lookup"><span data-stu-id="bc791-103">Sometimes you might have to write a query that selects elements based on their context.</span></span> <span data-ttu-id="bc791-104">您可能需要基于前面或后面的同级元素进行筛选。</span><span class="sxs-lookup"><span data-stu-id="bc791-104">You might want to filter based on preceding or following sibling elements.</span></span> <span data-ttu-id="bc791-105">您可能需要基于子元素或上级元素进行筛选。</span><span class="sxs-lookup"><span data-stu-id="bc791-105">You might want to filter based on child or ancestor elements.</span></span>  
  
 <span data-ttu-id="bc791-106">通过编写查询并在 `where` 子句中使用查询的结果可以实现此目的。</span><span class="sxs-lookup"><span data-stu-id="bc791-106">You can do this by writing a query and using the results of the query in the `where` clause.</span></span> <span data-ttu-id="bc791-107">如果在测试值之前必须先测试空值，则更适合在 `let` 子句中执行查询，然后在 `where` 子句中使用查询结果。</span><span class="sxs-lookup"><span data-stu-id="bc791-107">If you have to first test against null, and then test the value, it is more convenient to do the query in a `let` clause, and then use the results in the `where` clause.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc791-108">示例</span><span class="sxs-lookup"><span data-stu-id="bc791-108">Example</span></span>  
 <span data-ttu-id="bc791-109">下面的示例选择后面紧接 `p` 元素的所有 `ul` 元素。</span><span class="sxs-lookup"><span data-stu-id="bc791-109">The following example selects all `p` elements that are immediately followed by a `ul` element.</span></span>  
  
```vb  
Dim doc As XElement = _  
    <Root>  
        <p id='1'/>  
        <ul>abc</ul>  
        <Child>  
            <p id='2'/>  
            <notul/>  
            <p id='3'/>  
            <ul>def</ul>  
            <p id='4'/>  
        </Child>  
        <Child>  
            <p id='5'/>  
            <notul/>  
            <p id='6'/>  
            <ul>abc</ul>  
            <p id='7'/>  
        </Child>  
    </Root>  
  
Dim items As IEnumerable(Of XElement) = _  
    From e In doc...<p> _  
    Let z = e.ElementsAfterSelf().FirstOrDefault() _  
    Where z IsNot Nothing AndAlso z.Name.LocalName = "ul" _  
    Select e  
  
For Each e As XElement In items  
    Console.WriteLine("id = {0}", e.@<id>)  
Next  
```  
  
 <span data-ttu-id="bc791-110">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="bc791-110">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="example"></a><span data-ttu-id="bc791-111">示例</span><span class="sxs-lookup"><span data-stu-id="bc791-111">Example</span></span>  
 <span data-ttu-id="bc791-112">下面的示例演示如何对命名空间中的 XML 进行同样的查询。</span><span class="sxs-lookup"><span data-stu-id="bc791-112">The following example shows the same query for XML that is in a namespace.</span></span> <span data-ttu-id="bc791-113">有关详细信息，请参阅[使用 XML 命名空间 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)。</span><span class="sxs-lookup"><span data-stu-id="bc791-113">For more information, see [Working with XML Namespaces (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md).</span></span>  
  
```vb  
Imports <xmlns='http://www.adatum.com'>  
  
Module Module1  
    Sub Main()  
        Dim doc As XElement = _  
            <Root>  
                <p id='1'/>  
                <ul>abc</ul>  
                <Child>  
                    <p id='2'/>  
                    <notul/>  
                    <p id='3'/>  
                    <ul>def</ul>  
                    <p id='4'/>  
                </Child>  
                <Child>  
                    <p id='5'/>  
                    <notul/>  
                    <p id='6'/>  
                    <ul>abc</ul>  
                    <p id='7'/>  
                </Child>  
            </Root>  
  
        Dim items As IEnumerable(Of XElement) = _  
            From e In doc...<p> _  
            Let z = e.ElementsAfterSelf().FirstOrDefault() _  
            Where z IsNot Nothing AndAlso z.Name = GetXmlNamespace().GetName("ul") _  
            Select e  
  
        For Each e As XElement In items  
            Console.WriteLine("id = {0}", e.@<id>)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="bc791-114">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="bc791-114">This code produces the following output:</span></span>  
  
```  
id = 1  
id = 3  
id = 6  
```  
  
## <a name="see-also"></a><span data-ttu-id="bc791-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="bc791-115">See also</span></span>
- <xref:System.Xml.Linq.XElement.Parse%2A>
- <xref:System.Xml.Linq.XContainer.Descendants%2A>
- <xref:System.Xml.Linq.XNode.ElementsAfterSelf%2A>
- <xref:System.Linq.Enumerable.FirstOrDefault%2A>
- [<span data-ttu-id="bc791-116">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc791-116">Basic Queries (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/basic-queries-linq-to-xml.md)
