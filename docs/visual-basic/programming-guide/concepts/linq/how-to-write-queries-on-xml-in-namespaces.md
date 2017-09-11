---
title: "如何︰ 编写针对命名空间 (Visual Basic 中) 中的 XML 的查询 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 7d4131b5-3288-414f-b77c-b2edc2a1f465
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d3f16cecf118e88b3309384e880cc895ed7f2674
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-write-queries-on-xml-in-namespaces-visual-basic"></a><span data-ttu-id="43729-102">如何︰ 编写针对命名空间 (Visual Basic 中) 中的 XML 的查询</span><span class="sxs-lookup"><span data-stu-id="43729-102">How to: Write Queries on XML in Namespaces (Visual Basic)</span></span>
<span data-ttu-id="43729-103">若要针对的是命名空间中的 XML 编写查询，必须使用<xref:System.Xml.Linq.XName>具有正确的命名空间的对象。</xref:System.Xml.Linq.XName></span><span class="sxs-lookup"><span data-stu-id="43729-103">To write a query on XML that is in a namespace, you must use <xref:System.Xml.Linq.XName> objects that have the correct namespace.</span></span>  
  
 <span data-ttu-id="43729-104">在 Visual Basic 中，最常用的方法是定义一个全局命名空间，然后使用那些使用该全局命名空间的 XML 文本和 XML 属性。</span><span class="sxs-lookup"><span data-stu-id="43729-104">In Visual Basic, the most common approach is to define a global namespace, and then use XML literals and XML properties that use the global namespace.</span></span> <span data-ttu-id="43729-105">您可以定义一个全局默认命名空间，在这种情况中，XML 文本中的元素将默认位于该命名空间中。</span><span class="sxs-lookup"><span data-stu-id="43729-105">You can define a global default namespace, in which case elements in the XML literals will be in the namespace by default.</span></span> <span data-ttu-id="43729-106">或者，您可以定义一个具有前缀的全局命名空间，然后根据需要在 XML 文本和 XML 属性中使用该前缀。</span><span class="sxs-lookup"><span data-stu-id="43729-106">Alternatively, you can define a global namespace with a prefix, and then use the prefix as required in the XML literals, and in XML properties.</span></span> <span data-ttu-id="43729-107">与其他形式的 XML 一样，默认情况下，属性始终不在任何命名空间中。</span><span class="sxs-lookup"><span data-stu-id="43729-107">As with other forms of XML, attributes are always in no namespace by default.</span></span>  
  
 <span data-ttu-id="43729-108">本主题中示例的第一组演示如何在默认命名空间中创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="43729-108">The first set of examples in this topic shows how to create an XML tree in a default namespace.</span></span> <span data-ttu-id="43729-109">第二个集演示如何在具有前缀的命名空间中创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="43729-109">The second set shows how to create an XML tree in a namespace with a prefix.</span></span>  
  
## <a name="example"></a><span data-ttu-id="43729-110">示例</span><span class="sxs-lookup"><span data-stu-id="43729-110">Example</span></span>  
 <span data-ttu-id="43729-111">下面的示例创建一个位于默认命名空间中的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="43729-111">The following example creates an XML tree that is in a default namespace.</span></span> <span data-ttu-id="43729-112">然后检索元素的集合。</span><span class="sxs-lookup"><span data-stu-id="43729-112">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="43729-113">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="43729-113">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="example"></a><span data-ttu-id="43729-114">示例</span><span class="sxs-lookup"><span data-stu-id="43729-114">Example</span></span>  
 <span data-ttu-id="43729-115">但是，在 Visual Basic 中，在使用带前缀的命名空间的 XML 树上编写查询与在默认命名空间中查询 XML 树却大不相同。</span><span class="sxs-lookup"><span data-stu-id="43729-115">In Visual Basic, however, writing queries on an XML tree that uses a namespace with a prefix is quite different from querying an XML tree in a default namespace.</span></span> <span data-ttu-id="43729-116">您通常使用 `Imports` 语句导入带前缀的命名空间。</span><span class="sxs-lookup"><span data-stu-id="43729-116">Typically you use the `Imports` statement to import the namespace with a prefix.</span></span> <span data-ttu-id="43729-117">然后在构造 XML 树时，在元素和属性名称中使用该前缀。</span><span class="sxs-lookup"><span data-stu-id="43729-117">You then use the prefix in the element and attribute names when you construct the XML tree.</span></span> <span data-ttu-id="43729-118">使用 XML 属性查询 XML 树时，还要使用前缀。</span><span class="sxs-lookup"><span data-stu-id="43729-118">You also use the prefix when querying an XML tree using XML properties.</span></span>  
  
 <span data-ttu-id="43729-119">下面的示例创建一个位于具有前缀的默认命名空间中的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="43729-119">The following example creates an XML tree that is in a namespace with a prefix.</span></span> <span data-ttu-id="43729-120">然后检索元素的集合。</span><span class="sxs-lookup"><span data-stu-id="43729-120">It then retrieves a collection of elements.</span></span>  
  
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
  
 <span data-ttu-id="43729-121">该示例产生下面的输出：</span><span class="sxs-lookup"><span data-stu-id="43729-121">This example produces the following output:</span></span>  
  
```  
1  
2  
3  
```  
  
## <a name="see-also"></a><span data-ttu-id="43729-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="43729-122">See Also</span></span>  
 [<span data-ttu-id="43729-123">使用 XML 命名空间 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="43729-123">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
