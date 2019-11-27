---
title: 默认命名空间的范围
ms.date: 07/20/2015
ms.assetid: d4cce80c-342f-4097-be8b-40ab0bfa90ba
ms.openlocfilehash: 8ba4d13b6d40180a88651f0503d1323f2b78f36c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74343649"
---
# <a name="scope-of-default-namespaces-in-visual-basic"></a><span data-ttu-id="0f682-102">Visual Basic 中的默认命名空间的范围</span><span class="sxs-lookup"><span data-stu-id="0f682-102">Scope of Default Namespaces in Visual Basic</span></span>
<span data-ttu-id="0f682-103">XML 树中表示的默认命名空间不在查询范围内。</span><span class="sxs-lookup"><span data-stu-id="0f682-103">Default namespaces as represented in the XML tree are not in scope for queries.</span></span> <span data-ttu-id="0f682-104">如果您的 XML 在默认命名空间内，仍须声明一个 <xref:System.Xml.Linq.XNamespace> 变量，并将该变量与本地名称组合在一起，生成一个限定名，在查询中使用。</span><span class="sxs-lookup"><span data-stu-id="0f682-104">If you have XML that is in a default namespace, you still must declare an <xref:System.Xml.Linq.XNamespace> variable, and combine it with the local name to make a qualified name to be used in the query.</span></span>  
  
 <span data-ttu-id="0f682-105">查询 XML 树时遇到的一个最常见问题是，如果 XML 树具有默认命名空间，开发人员在编写查询时，有时会将 XML 视为不在命名空间内。</span><span class="sxs-lookup"><span data-stu-id="0f682-105">One of the most common problems when querying XML trees is that if the XML tree has a default namespace, the developer sometimes writes the query as though the XML were not in a namespace.</span></span>  
  
 <span data-ttu-id="0f682-106">本主题的第一个示例集演示一种加载但是按不正确方式查询默认命名空间中的 XML 的典型方式。</span><span class="sxs-lookup"><span data-stu-id="0f682-106">The first set of examples in this topic shows a typical way that XML in a default namespace is loaded, but is queried improperly.</span></span>  
  
 <span data-ttu-id="0f682-107">第二个示例集演示必需的更正，以便可以查询命名空间中的 XML。</span><span class="sxs-lookup"><span data-stu-id="0f682-107">The second set of examples show the necessary corrections so that you can query XML in a namespace.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0f682-108">示例</span><span class="sxs-lookup"><span data-stu-id="0f682-108">Example</span></span>  
 <span data-ttu-id="0f682-109">此示例演示如何在命名空间中创建 XML 和一个返回空结果集的查询。</span><span class="sxs-lookup"><span data-stu-id="0f682-109">This example shows the creation of XML in a namespace, and a query that returns an empty result set.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0f682-110">代码</span><span class="sxs-lookup"><span data-stu-id="0f682-110">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="0f682-111">注释</span><span class="sxs-lookup"><span data-stu-id="0f682-111">Comments</span></span>  
 <span data-ttu-id="0f682-112">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="0f682-112">This example produces the following result:</span></span>  
  
```console  
Result set follows:  
End of result set  
```  
  
## <a name="example"></a><span data-ttu-id="0f682-113">示例</span><span class="sxs-lookup"><span data-stu-id="0f682-113">Example</span></span>  
 <span data-ttu-id="0f682-114">本示例演示如何在命名空间中创建 XML 和一个正确编码的查询。</span><span class="sxs-lookup"><span data-stu-id="0f682-114">This example shows the creation of XML in a namespace, and a query that is coded properly.</span></span>  
  
 <span data-ttu-id="0f682-115">与上述错误编码的示例相比，使用 Visual Basic 时的正确方法是声明和初始化一个全局默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="0f682-115">In contrast to the incorrectly coded example above, the correct approach when using Visual Basic is to declare and initialize a global default namespace.</span></span> <span data-ttu-id="0f682-116">这样会将所有 XML 属性放入该默认命名空间。</span><span class="sxs-lookup"><span data-stu-id="0f682-116">This places all XML properties in the default namespace.</span></span> <span data-ttu-id="0f682-117">无需对该示例做任何其他修改，即可使它正常运行。</span><span class="sxs-lookup"><span data-stu-id="0f682-117">No other modifications are required to the example to make it work properly.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0f682-118">代码</span><span class="sxs-lookup"><span data-stu-id="0f682-118">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="0f682-119">注释</span><span class="sxs-lookup"><span data-stu-id="0f682-119">Comments</span></span>  
 <span data-ttu-id="0f682-120">此示例产生下面的结果：</span><span class="sxs-lookup"><span data-stu-id="0f682-120">This example produces the following result:</span></span>  
  
```console  
Result set follows:  
1  
2  
3  
End of result set  
```  
  
## <a name="see-also"></a><span data-ttu-id="0f682-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0f682-121">See also</span></span>

- [<span data-ttu-id="0f682-122">命名空间概述（LINQ to XML）（Visual Basic）</span><span class="sxs-lookup"><span data-stu-id="0f682-122">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
