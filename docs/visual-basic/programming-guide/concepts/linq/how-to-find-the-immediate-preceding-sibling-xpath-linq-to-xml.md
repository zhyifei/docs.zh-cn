---
title: 如何：查找前面紧邻的同级 (XPATH-LINQ to XML) (Visual Basic)
ms.date: 07/20/2015
ms.assetid: ec046283-9fe2-4440-b295-860bf700099d
ms.openlocfilehash: ca3602a24b80d9002a639d9a319a731541aeb2df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61854992"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-visual-basic"></a><span data-ttu-id="86589-102">如何：查找前面紧邻的同级 (XPATH-LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86589-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="86589-103">有时，您需要查找某一节点的前面紧邻同级。</span><span class="sxs-lookup"><span data-stu-id="86589-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="86589-104">由于与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 相比，XPath 中前面紧邻轴的位置谓词的语义同，因此这是一个更值得关注的比较。</span><span class="sxs-lookup"><span data-stu-id="86589-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86589-105">示例</span><span class="sxs-lookup"><span data-stu-id="86589-105">Example</span></span>  
 <span data-ttu-id="86589-106">在本示例中，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询使用 <xref:System.Linq.Enumerable.Last%2A> 运算符查找由 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> 返回的集合中的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="86589-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="86589-107">相比之下，XPath 表达式使用值为 1 的谓词来查找前面紧邻的元素。</span><span class="sxs-lookup"><span data-stu-id="86589-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```vb  
Dim root As XElement = _   
    <Root>  
        <Child1/>  
        <Child2/>  
        <Child3/>  
        <Child4/>  
    </Root>  
Dim child4 As XElement = root.Element("Child4")  
  
' LINQ to XML query  
Dim el1 As XElement = child4.ElementsBeforeSelf().Last()  
  
' XPath expression  
Dim el2 As XElement = _  
    DirectCast(child4.XPathEvaluate("preceding-sibling::*[1]"),  _  
    IEnumerable).Cast(Of XElement)().First()  
  
If el1 Is el2 Then  
    Console.WriteLine("Results are identical")  
Else  
    Console.WriteLine("Results differ")  
End If  
Console.WriteLine(el1)  
```  
  
 <span data-ttu-id="86589-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="86589-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
  
## <a name="see-also"></a><span data-ttu-id="86589-109">请参阅</span><span class="sxs-lookup"><span data-stu-id="86589-109">See also</span></span>

- [<span data-ttu-id="86589-110">LINQ to XML 针对 XPath 用户 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86589-110">LINQ to XML for XPath Users (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-for-xpath-users.md)
