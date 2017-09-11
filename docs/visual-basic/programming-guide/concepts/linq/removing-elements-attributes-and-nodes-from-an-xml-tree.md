---
title: "从 XML 树 (Visual Basic 中) 中移除元素、 特性和节点 |Microsoft 文档"
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
ms.assetid: 5cf21919-4360-4b49-b29d-58ea3164ac72
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8842858080ce1f27d997e6af61a8dd2301cdc2bc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="removing-elements-attributes-and-nodes-from-an-xml-tree-visual-basic"></a><span data-ttu-id="edd4c-102">从 XML 树 (Visual Basic 中) 中移除元素、 特性和节点</span><span class="sxs-lookup"><span data-stu-id="edd4c-102">Removing Elements, Attributes, and Nodes from an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="edd4c-103">可以修改 XML 树，移除元素、属性和其他类型的节点。</span><span class="sxs-lookup"><span data-stu-id="edd4c-103">You can modify an XML tree, removing elements, attributes, and other types of nodes.</span></span>  
  
 <span data-ttu-id="edd4c-104">从 XML 文档中移除单个元素或单个属性的操作非常简单。</span><span class="sxs-lookup"><span data-stu-id="edd4c-104">Removing a single element or a single attribute from an XML document is straightforward.</span></span> <span data-ttu-id="edd4c-105">但是，若要移除多个元素或属性的集合，则应首先将一个集合具体化为一个列表，然后从该列表中删除相应元素或属性。</span><span class="sxs-lookup"><span data-stu-id="edd4c-105">However, when removing collections of elements or attributes, you should first materialize a collection into a list, and then delete the elements or attributes from the list.</span></span> <span data-ttu-id="edd4c-106">最佳方法是使用<xref:System.Xml.Linq.Extensions.Remove%2A>扩展方法，它将为您执行此操作。</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="edd4c-106">The best approach is to use the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method, which will do this for you.</span></span>  
  
 <span data-ttu-id="edd4c-107">这么做的主要原因在于，从 XML 树检索的大多数集合都是用延迟执行生成的。</span><span class="sxs-lookup"><span data-stu-id="edd4c-107">The main reason for doing this is that most of the collections you retrieve from an XML tree are yielded using deferred execution.</span></span> <span data-ttu-id="edd4c-108">如果不首先将集合具体化为列表，或者不使用扩展方法，则可能会遇到某类 Bug。</span><span class="sxs-lookup"><span data-stu-id="edd4c-108">If you do not first materialize them into a list, or if you do not use the extension methods, it is possible to encounter a certain class of bugs.</span></span> <span data-ttu-id="edd4c-109">有关详细信息，请参阅[混合声明性代码/强制性代码 Bug (LINQ to XML) (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="edd4c-109">For more information, see [Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="edd4c-110">下列方法可以从 XML 树中移除节点和属性。</span><span class="sxs-lookup"><span data-stu-id="edd4c-110">The following methods remove nodes and attributes from an XML tree.</span></span>  
  
|<span data-ttu-id="edd4c-111">方法</span><span class="sxs-lookup"><span data-stu-id="edd4c-111">Method</span></span>|<span data-ttu-id="edd4c-112">说明</span><span class="sxs-lookup"><span data-stu-id="edd4c-112">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="edd4c-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="edd4c-113">[XAttribute.Remove](https://msdn.microsoft.com/library/system.xml.linq.xattribute.remove\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="edd4c-114">删除<xref:System.Xml.Linq.XAttribute>从其父代。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="edd4c-114">Removes an <xref:System.Xml.Linq.XAttribute> from its parent.</span></span>|  
|<span data-ttu-id="edd4c-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span><span class="sxs-lookup"><span data-stu-id="edd4c-115">[XContainer.RemoveNodes](https://msdn.microsoft.com/library/system.xml.linq.xcontainer.removenodes\(v=vs.110\).aspx)</span></span>|<span data-ttu-id="edd4c-116">从<xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer>移除子节点</span><span class="sxs-lookup"><span data-stu-id="edd4c-116">Removes the child nodes from an <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="edd4c-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-117"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-118">从<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement>中移除内容和属性</span><span class="sxs-lookup"><span data-stu-id="edd4c-118">Removes content and attributes from an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="edd4c-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-119"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-120">移除<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement>的属性</span><span class="sxs-lookup"><span data-stu-id="edd4c-120">Removes the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="edd4c-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-121"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-122">如果传递 `null` 作为值，则移除该属性。</span><span class="sxs-lookup"><span data-stu-id="edd4c-122">If you pass `null` for value, then removes the attribute.</span></span>|  
|<span data-ttu-id="edd4c-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-123"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-124">如果传递 `null` 作为值，则移除该子元素。</span><span class="sxs-lookup"><span data-stu-id="edd4c-124">If you pass `null` for value, then removes the child element.</span></span>|  
|<span data-ttu-id="edd4c-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-125"><xref:System.Xml.Linq.XNode.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-126">删除<xref:System.Xml.Linq.XNode>从其父代。</xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="edd4c-126">Removes an <xref:System.Xml.Linq.XNode> from its parent.</span></span>|  
|<span data-ttu-id="edd4c-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-127"><xref:System.Xml.Linq.Extensions.Remove%2A?displayProperty=fullName></span></span>|<span data-ttu-id="edd4c-128">从父元素中移除源集合中的每个属性或元素。</span><span class="sxs-lookup"><span data-stu-id="edd4c-128">Removes every attribute or element in the source collection from its parent element.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="edd4c-129">示例</span><span class="sxs-lookup"><span data-stu-id="edd4c-129">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="edd4c-130">描述</span><span class="sxs-lookup"><span data-stu-id="edd4c-130">Description</span></span>  
 <span data-ttu-id="edd4c-131">此示例演示三种移除元素的方法。</span><span class="sxs-lookup"><span data-stu-id="edd4c-131">This example demonstrates three approaches to removing elements.</span></span> <span data-ttu-id="edd4c-132">第一种，移除单个元素。</span><span class="sxs-lookup"><span data-stu-id="edd4c-132">First, it removes a single element.</span></span> <span data-ttu-id="edd4c-133">其次，检索元素集合，将它们具体化使用<xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName>运算符，然后移除集合。</xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="edd4c-133">Second, it retrieves a collection of elements, materializes them using the <xref:System.Linq.Enumerable.ToList%2A?displayProperty=fullName> operator, and removes the collection.</span></span> <span data-ttu-id="edd4c-134">最后，它检索的元素的集合，并将其使用<xref:System.Xml.Linq.Extensions.Remove%2A>扩展方法。</xref:System.Xml.Linq.Extensions.Remove%2A></span><span class="sxs-lookup"><span data-stu-id="edd4c-134">Finally, it retrieves a collection of elements and removes them using the <xref:System.Xml.Linq.Extensions.Remove%2A> extension method.</span></span>  
  
 <span data-ttu-id="edd4c-135">有关详细信息<xref:System.Linq.Enumerable.ToList%2A>运算符，请参阅[转换数据类型 (Visual Basic 中)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md)。</xref:System.Linq.Enumerable.ToList%2A></span><span class="sxs-lookup"><span data-stu-id="edd4c-135">For more information on the <xref:System.Linq.Enumerable.ToList%2A> operator, see [Converting Data Types (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).</span></span>  
  
### <a name="code"></a><span data-ttu-id="edd4c-136">代码</span><span class="sxs-lookup"><span data-stu-id="edd4c-136">Code</span></span>  
  
```vb  
Dim root As XElement = _  
    <Root>  
        <Child1>  
            <GrandChild1/>  
            <GrandChild2/>  
            <GrandChild3/>  
        </Child1>  
        <Child2>  
            <GrandChild4/>  
            <GrandChild5/>  
            <GrandChild6/>  
        </Child2>  
        <Child3>  
            <GrandChild7/>  
            <GrandChild8/>  
            <GrandChild9/>  
        </Child3>  
    </Root>  
root.<Child1>.<GrandChild1>.Remove()  
root.<Child2>.Elements().ToList().Remove()  
root.<Child3>.Elements().Remove()  
Console.WriteLine(root)  
  
```  
  
### <a name="comments"></a><span data-ttu-id="edd4c-137">注释</span><span class="sxs-lookup"><span data-stu-id="edd4c-137">Comments</span></span>  
 <span data-ttu-id="edd4c-138">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="edd4c-138">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>  
    <GrandChild2 />  
    <GrandChild3 />  
  </Child1>  
  <Child2 />  
  <Child3 />  
</Root>  
```  
  
 <span data-ttu-id="edd4c-139">请注意，第一个孙元素已从 `Child1` 中移除。</span><span class="sxs-lookup"><span data-stu-id="edd4c-139">Notice that the first grandchild element has been removed from `Child1`.</span></span> <span data-ttu-id="edd4c-140">所有孙元素都已从 `Child2` 和 `Child3` 中移除。</span><span class="sxs-lookup"><span data-stu-id="edd4c-140">All grandchildren elements have been removed from `Child2` and from `Child3`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="edd4c-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="edd4c-141">See Also</span></span>  
 [<span data-ttu-id="edd4c-142">修改 XML 树 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="edd4c-142">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
