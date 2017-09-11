---
title: "将元素、 特性和节点添加到 XML 树 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: e243e694-c987-43aa-8b22-1e33dace582c
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: f8ee26aef896a2f404e815823ade83e204270613
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="adding-elements-attributes-and-nodes-to-an-xml-tree-visual-basic"></a><span data-ttu-id="2a686-102">将元素、 特性和节点添加到 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a686-102">Adding Elements, Attributes, and Nodes to an XML Tree (Visual Basic)</span></span>
<span data-ttu-id="2a686-103">可以向现有的 XML 树中添加内容（包括元素、属性、注释、处理指令、文本和 CDATA）。</span><span class="sxs-lookup"><span data-stu-id="2a686-103">You can add content (elements, attributes, comments, processing instructions, text, and CDATA) to an existing XML tree.</span></span>  
  
## <a name="methods-for-adding-content"></a><span data-ttu-id="2a686-104">添加内容的方法</span><span class="sxs-lookup"><span data-stu-id="2a686-104">Methods for Adding Content</span></span>  
 <span data-ttu-id="2a686-105">以下方法将子内容添加到<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a686-105">The following methods add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="2a686-106">方法</span><span class="sxs-lookup"><span data-stu-id="2a686-106">Method</span></span>|<span data-ttu-id="2a686-107">说明</span><span class="sxs-lookup"><span data-stu-id="2a686-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2a686-108"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="2a686-108"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="2a686-109"><xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer>的子内容的末尾添加内容</span><span class="sxs-lookup"><span data-stu-id="2a686-109">Adds content at the end of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="2a686-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="2a686-110"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="2a686-111"><xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer>的子内容的开头添加内容</span><span class="sxs-lookup"><span data-stu-id="2a686-111">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
  
 <span data-ttu-id="2a686-112">以下方法将内容添加为<xref:System.Xml.Linq.XNode>。</xref:System.Xml.Linq.XNode>的同级节点</span><span class="sxs-lookup"><span data-stu-id="2a686-112">The following methods add content as sibling nodes of an <xref:System.Xml.Linq.XNode>.</span></span> <span data-ttu-id="2a686-113">向其中添加同级内容的最常见的节点是<xref:System.Xml.Linq.XElement>，尽管您可以添加到其他类型的节点<xref:System.Xml.Linq.XText>或<xref:System.Xml.Linq.XComment>。</xref:System.Xml.Linq.XComment></xref:System.Xml.Linq.XText>等的有效的同级内容</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="2a686-113">The most common node to which you add sibling content is <xref:System.Xml.Linq.XElement>, although you can add valid sibling content to other types of nodes such as <xref:System.Xml.Linq.XText> or <xref:System.Xml.Linq.XComment>.</span></span>  
  
|<span data-ttu-id="2a686-114">方法</span><span class="sxs-lookup"><span data-stu-id="2a686-114">Method</span></span>|<span data-ttu-id="2a686-115">说明</span><span class="sxs-lookup"><span data-stu-id="2a686-115">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="2a686-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="2a686-116"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="2a686-117">在<xref:System.Xml.Linq.XNode>。</xref:System.Xml.Linq.XNode>之后添加内容</span><span class="sxs-lookup"><span data-stu-id="2a686-117">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="2a686-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="2a686-118"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="2a686-119"><xref:System.Xml.Linq.XNode>。</xref:System.Xml.Linq.XNode>之前添加的内容</span><span class="sxs-lookup"><span data-stu-id="2a686-119">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="2a686-120">示例</span><span class="sxs-lookup"><span data-stu-id="2a686-120">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="2a686-121">描述</span><span class="sxs-lookup"><span data-stu-id="2a686-121">Description</span></span>  
 <span data-ttu-id="2a686-122">下面的示例创建两个 XML 树，然后修改其中一个树。</span><span class="sxs-lookup"><span data-stu-id="2a686-122">The following example creates two XML trees, and then modifies one of the trees.</span></span>  
  
### <a name="code"></a><span data-ttu-id="2a686-123">代码</span><span class="sxs-lookup"><span data-stu-id="2a686-123">Code</span></span>  
  
```vb  
Dim srcTree As XElement = _  
    <Root>  
        <Element1>1</Element1>  
        <Element2>2</Element2>  
        <Element3>3</Element3>  
        <Element4>4</Element4>  
        <Element5>5</Element5>  
    </Root>  
Dim xmlTree As XElement = _  
    <Root>  
        <Child1>1</Child1>  
        <Child2>2</Child2>  
        <Child3>3</Child3>  
        <Child4>4</Child4>  
        <Child5>5</Child5>  
    </Root>  
  
xmlTree.Add(<NewChild>new content</NewChild>)  
xmlTree.Add( _  
    From el In srcTree.Elements() _  
    Where CInt(el) > 3 _  
    Select el)  
  
' Even though Child9 does not exist in srcTree, the following statement  
' will not throw an exception, and nothing will be added to xmlTree.  
xmlTree.Add(srcTree.Element("Child9"))  
Console.WriteLine(xmlTree)  
  
```  
  
### <a name="comments"></a><span data-ttu-id="2a686-124">注释</span><span class="sxs-lookup"><span data-stu-id="2a686-124">Comments</span></span>  
 <span data-ttu-id="2a686-125">此代码生成以下输出：</span><span class="sxs-lookup"><span data-stu-id="2a686-125">This code produces the following output:</span></span>  
  
```xml  
<Root>  
  <Child1>1</Child1>  
  <Child2>2</Child2>  
  <Child3>3</Child3>  
  <Child4>4</Child4>  
  <Child5>5</Child5>  
  <NewChild>new content</NewChild>  
  <Element4>4</Element4>  
  <Element5>5</Element5>  
</Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="2a686-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2a686-126">See Also</span></span>  
 [<span data-ttu-id="2a686-127">修改 XML 树 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2a686-127">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
