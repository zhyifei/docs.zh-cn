---
title: 在 Visual Basic 中的默认命名空间的范围
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: e33505dd8e8ad94e3c758f15f245d0cbaf6987bc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58836709"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="20821-102">在 Visual Basic 中的默认命名空间的范围</span><span class="sxs-lookup"><span data-stu-id="20821-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="20821-103">XML 树中表示的默认命名空间不在查询范围内。</span><span class="sxs-lookup"><span data-stu-id="20821-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="20821-104">如果您的 XML 在默认命名空间内，仍须声明一个 <xref:System.Xml.Linq.XNamespace> 变量，并将该变量与本地名称组合在一起，生成一个限定名，在查询中使用。</span><span class="sxs-lookup"><span data-stu-id="20821-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="20821-105">查询 XML 树时遇到的一个最常见问题是，如果 XML 树具有默认命名空间，开发人员在编写查询时，有时会将 XML 视为不在命名空间内。</span><span class="sxs-lookup"><span data-stu-id="20821-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="20821-106">本主题的第一个示例集演示一种加载但是按不正确方式查询默认命名空间中的 XML 的典型方式。</span><span class="sxs-lookup"><span data-stu-id="20821-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="20821-107">第二个示例集演示必需的更正，以便可以查询命名空间中的 XML。</span><span class="sxs-lookup"><span data-stu-id="20821-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="20821-108">示例</span><span class="sxs-lookup"><span data-stu-id="20821-108">Example</span></span>  
 <span data-ttu-id="20821-109">此示例演示如何在命名空间中创建 XML 和一个返回空结果集的查询。</span><span class="sxs-lookup"><span data-stu-id="20821-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="20821-110">代码</span><span class="sxs-lookup"><span data-stu-id="20821-110">Code</span></span>  
  
```vb  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="20821-111">注释</span><span class="sxs-lookup"><span data-stu-id="20821-111">Comments</span></span>  
 <span data-ttu-id="20821-112">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="20821-112">This example produces the following result:</span></span>  
  
```  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="20821-113">示例</span><span class="sxs-lookup"><span data-stu-id="20821-113">Example</span></span>  
 <span data-ttu-id="20821-114">本示例演示如何在命名空间中创建 XML 和一个正确编码的查询。</span><span class="sxs-lookup"><span data-stu-id="20821-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="20821-115">与上述不正确编码示例，相比使用 Visual Basic 时的正确方法是声明和初始化一个全局默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="20821-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="20821-116">这样会将所有 XML 属性放入该默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="20821-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="20821-117">无需对该示例做任何其他修改，即可使它正常运行。</span><span class="sxs-lookup"><span data-stu-id="20821-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="20821-118">代码</span><span class="sxs-lookup"><span data-stu-id="20821-118">Code</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root xmlns='http://www.adventure-works.com'>  
                <Child>1</Child>  
                <Child>2</Child>  
                <Child>3</Child>  
                <AnotherChild>4</AnotherChild>  
                <AnotherChild>5</AnotherChild>  
                <AnotherChild>6</AnotherChild>  
            </Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
                From el In root.<Child> _  
                Select el  
        Console.WriteLine("Result set follows:")  
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
        Console.WriteLine("End of result set")  
    End Sub  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="20821-119">注释</span><span class="sxs-lookup"><span data-stu-id="20821-119">Comments</span></span>  
 <span data-ttu-id="20821-120">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="20821-120">This example produces the following result:</span></span>  
  
```  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="20821-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="20821-121">See also</span></span>

- [<span data-ttu-id="20821-122">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="20821-122">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
