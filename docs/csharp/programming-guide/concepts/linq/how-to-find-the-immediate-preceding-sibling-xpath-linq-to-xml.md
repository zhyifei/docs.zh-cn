---
title: 如何：查找前面紧邻的同级 (XPath-LINQ to XML) (C#)
ms.date: 07/20/2015
ms.assetid: 74c06201-0b1b-4b5e-b3ac-0092980614e6
ms.openlocfilehash: 7d1d49f262b13f769ab1d28de8b75d214d8abe64
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486711"
---
# <a name="how-to-find-the-immediate-preceding-sibling-xpath-linq-to-xml-c"></a><span data-ttu-id="86304-102">如何：查找前面紧邻的同级 (XPath-LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="86304-102">How to: Find the Immediate Preceding Sibling (XPath-LINQ to XML) (C#)</span></span>
<span data-ttu-id="86304-103">有时，您需要查找某一节点的前面紧邻同级。</span><span class="sxs-lookup"><span data-stu-id="86304-103">Sometimes you want to find the immediate preceding sibling to a node.</span></span> <span data-ttu-id="86304-104">由于与 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 相比，XPath 中前面紧邻轴的位置谓词的语义同，因此这是一个更值得关注的比较。</span><span class="sxs-lookup"><span data-stu-id="86304-104">Due to the difference in the semantics of positional predicates for the preceding sibling axes in XPath as opposed to [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)], this is one of the more interesting comparisons.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86304-105">示例</span><span class="sxs-lookup"><span data-stu-id="86304-105">Example</span></span>  
 <span data-ttu-id="86304-106">在本示例中，[!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询使用 <xref:System.Linq.Enumerable.Last%2A> 运算符查找由 <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A> 返回的集合中的最后一个节点。</span><span class="sxs-lookup"><span data-stu-id="86304-106">In this example, the [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query uses the <xref:System.Linq.Enumerable.Last%2A> operator to find the last node in the collection returned by <xref:System.Xml.Linq.XNode.ElementsBeforeSelf%2A>.</span></span> <span data-ttu-id="86304-107">相比之下，XPath 表达式使用值为 1 的谓词来查找前面紧邻的元素。</span><span class="sxs-lookup"><span data-stu-id="86304-107">By contrast, the XPath expression uses a predicate with a value of 1 to find the immediately preceding element.</span></span>  
  
```csharp  
XElement root = XElement.Parse(  
    @"<Root>  
    <Child1/>  
    <Child2/>  
    <Child3/>  
    <Child4/>  
</Root>");  
XElement child4 = root.Element("Child4");  
  
// LINQ to XML query  
XElement el1 =  
    child4  
    .ElementsBeforeSelf()  
    .Last();  
  
// XPath expression  
XElement el2 =  
    ((IEnumerable)child4  
                 .XPathEvaluate("preceding-sibling::*[1]"))  
                 .Cast<XElement>()  
                 .First();  
  
if (el1 == el2)  
    Console.WriteLine("Results are identical");  
else  
    Console.WriteLine("Results differ");  
Console.WriteLine(el1);  
```  
  
 <span data-ttu-id="86304-108">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="86304-108">This example produces the following output:</span></span>  
  
```  
Results are identical  
<Child3 />  
```  
