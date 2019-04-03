---
title: 如何：命名空间 (Visual Basic) 中的 XML 编写查询
ms.date: 07/20/2015
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
ms.openlocfilehash: 4efa1de254a0264752514c5ae6e601a66fa56f95
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2019
ms.locfileid: "58833433"
---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="be527-102">如何：命名空间 (Visual Basic) 中的 XML 编写查询</span><span class="sxs-lookup"><span data-stu-id="be527-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="be527-103">若要针对命名空间中的 XML 编写查询，必须使用具有正确命名空间的 <xref:System.Xml.Linq.XName> 对象。</span><span class="sxs-lookup"><span data-stu-id="be527-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="be527-104">在 Visual Basic 中，最常用的方法是定义一个全局命名空间，然后使用那些使用该全局命名空间的 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="be527-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="be527-105">您可以定义一个全局默认命名空间，在这种情况中，XML 文本中的元素将默认位于该命名空间中。</span><span class="sxs-lookup"><span data-stu-id="be527-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="be527-106">或者，您可以定义一个具有前缀的全局命名空间，然后根据需要在 XML 文本和 XML 属性中使用该前缀。</span><span class="sxs-lookup"><span data-stu-id="be527-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="be527-107">与其他形式的 XML 一样，默认情况下，属性始终不在任何命名空间中。</span><span class="sxs-lookup"><span data-stu-id="be527-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="be527-108">本主题的第一个示例集演示如何在默认命名空间中创建一个 XML 树。</span><span class="sxs-lookup"><span data-stu-id="be527-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="be527-109">第二个示例集演示如何在带有前缀的命名空间中创建一个 XML 树。</span><span class="sxs-lookup"><span data-stu-id="be527-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="be527-110">示例</span><span class="sxs-lookup"><span data-stu-id="be527-110">Example</span></span>  
 <span data-ttu-id="be527-111">下面的示例创建一个位于默认命名空间中的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="be527-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="be527-112">然后检索元素的集合。</span><span class="sxs-lookup"><span data-stu-id="be527-112">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <Root>  
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
        For Each el As XElement In c1  
            Console.WriteLine(el.Value)  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="be527-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="be527-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="be527-114">示例</span><span class="sxs-lookup"><span data-stu-id="be527-114">Example</span></span>  
 <span data-ttu-id="be527-115">但是，在 Visual Basic 中，在使用带前缀的命名空间的 XML 树上编写查询与在默认命名空间中查询 XML 树却大不相同。</span><span class="sxs-lookup"><span data-stu-id="be527-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="be527-116">您通常使用 `Imports` 语句导入带前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="be527-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="be527-117">然后在构造 XML 树时，在元素和属性名称中使用该前缀。</span><span class="sxs-lookup"><span data-stu-id="be527-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="be527-118">使用 XML 属性查询 XML 树时，还要使用前缀。</span><span class="sxs-lookup"><span data-stu-id="be527-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="be527-119">下面的示例创建一个位于具有前缀的默认命名空间中的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="be527-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="be527-120">然后检索元素的集合。</span><span class="sxs-lookup"><span data-stu-id="be527-120">It then retrieves a collection of elements.</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
  
Module Module1  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <aw:Child>1</aw:Child>  
                <aw:Child>2</aw:Child>  
                <aw:Child>3</aw:Child>  
                <aw:AnotherChild>4</aw:AnotherChild>  
                <aw:AnotherChild>5</aw:AnotherChild>  
                <aw:AnotherChild>6</aw:AnotherChild>  
            </aw:Root>  
        Dim c1 As IEnumerable(Of XElement) = _  
            From el In root.<aw:Child> _  
            Select el  
        For Each el As XElement In c1  
            Console.WriteLine(CInt(el))  
        Next  
    End Sub  
End Module  
```  
  
 <span data-ttu-id="be527-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="be527-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="be527-122">请参阅</span><span class="sxs-lookup"><span data-stu-id="be527-122">See also</span></span>

- [<span data-ttu-id="be527-123">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="be527-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
