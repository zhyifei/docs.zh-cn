---
title: "有效内容的 XElement 和 XDocument Objects2 |Microsoft 文档"
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
ms.assetid: 400bb692-478a-40b6-ac1b-4ccbb4cbbd02
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: ecdcd4c2c0ec61cf248c9e210d42abb750e0546b
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="valid-content-of-xelement-and-xdocument-objects"></a><span data-ttu-id="d0ac7-102">XElement 和 XDocument 对象的有效内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-102">Valid Content of XElement and XDocument Objects</span></span>
<span data-ttu-id="d0ac7-103">本主题描述可以传递给构造函数以及用于向元素和文档添加内容的方法的有效参数。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-103">This topic describes the valid arguments that can be passed to constructors and methods that you use to add content to elements and documents.</span></span>  
  
## <a name="valid-content"></a><span data-ttu-id="d0ac7-104">有效内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-104">Valid Content</span></span>  
 <span data-ttu-id="d0ac7-105">查询计算的结果通常<xref:System.Collections.Generic.IEnumerable%601>或<xref:System.Xml.Linq.XElement><xref:System.Collections.Generic.IEnumerable%601><xref:System.Xml.Linq.XAttribute>。</xref:System.Xml.Linq.XAttribute>的</xref:System.Collections.Generic.IEnumerable%601></xref:System.Xml.Linq.XElement></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d0ac7-105">Queries often evaluate to <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XElement> or <xref:System.Collections.Generic.IEnumerable%601> of <xref:System.Xml.Linq.XAttribute>.</span></span> <span data-ttu-id="d0ac7-106">可以传递的集合<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XAttribute>对象添加到<xref:System.Xml.Linq.XElement>构造函数。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d0ac7-106">You can pass collections of <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XAttribute> objects to the <xref:System.Xml.Linq.XElement> constructor.</span></span> <span data-ttu-id="d0ac7-107">所以，可以很方便地将查询的结果作为内容，传递给用于填充 XML 树的方法和构造函数。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-107">Therefore, it is convenient to pass the results of a query as content into methods and constructors that you use to populate XML trees.</span></span>  
  
 <span data-ttu-id="d0ac7-108">添加简单内容时，可以将多种类型传递给此方法。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-108">When adding simple content, various types can be passed to this method.</span></span> <span data-ttu-id="d0ac7-109">有效类型包括：</span><span class="sxs-lookup"><span data-stu-id="d0ac7-109">Valid types include the following:</span></span>  
  
-   <span data-ttu-id="d0ac7-110"><xref:System.String></xref:System.String></span><span class="sxs-lookup"><span data-stu-id="d0ac7-110"><xref:System.String></span></span>  
  
-   <span data-ttu-id="d0ac7-111"><xref:System.Double></xref:System.Double></span><span class="sxs-lookup"><span data-stu-id="d0ac7-111"><xref:System.Double></span></span>  
  
-   <span data-ttu-id="d0ac7-112"><xref:System.Single></xref:System.Single></span><span class="sxs-lookup"><span data-stu-id="d0ac7-112"><xref:System.Single></span></span>  
  
-   <span data-ttu-id="d0ac7-113"><xref:System.Decimal></xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="d0ac7-113"><xref:System.Decimal></span></span>  
  
-   <span data-ttu-id="d0ac7-114"><xref:System.Boolean></xref:System.Boolean></span><span class="sxs-lookup"><span data-stu-id="d0ac7-114"><xref:System.Boolean></span></span>  
  
-   <span data-ttu-id="d0ac7-115"><xref:System.DateTime></xref:System.DateTime></span><span class="sxs-lookup"><span data-stu-id="d0ac7-115"><xref:System.DateTime></span></span>  
  
-   <span data-ttu-id="d0ac7-116"><xref:System.TimeSpan></xref:System.TimeSpan></span><span class="sxs-lookup"><span data-stu-id="d0ac7-116"><xref:System.TimeSpan></span></span>  
  
-   <span data-ttu-id="d0ac7-117"><xref:System.DateTimeOffset></xref:System.DateTimeOffset></span><span class="sxs-lookup"><span data-stu-id="d0ac7-117"><xref:System.DateTimeOffset></span></span>  
  
-   <span data-ttu-id="d0ac7-118">实现 `Object.ToString` 的任何类型。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-118">Any type that implements `Object.ToString`.</span></span>  
  
-   <span data-ttu-id="d0ac7-119">实现<xref:System.Collections.Generic.IEnumerable%601>。</xref:System.Collections.Generic.IEnumerable%601>的任何类型</span><span class="sxs-lookup"><span data-stu-id="d0ac7-119">Any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>  
  
 <span data-ttu-id="d0ac7-120">添加复杂内容时，可以将多种类型传递给此方法：</span><span class="sxs-lookup"><span data-stu-id="d0ac7-120">When adding complex content, various types can be passed to this method:</span></span>  
  
-   <span data-ttu-id="d0ac7-121"><xref:System.Xml.Linq.XObject></xref:System.Xml.Linq.XObject></span><span class="sxs-lookup"><span data-stu-id="d0ac7-121"><xref:System.Xml.Linq.XObject></span></span>  
  
-   <span data-ttu-id="d0ac7-122"><xref:System.Xml.Linq.XNode></xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="d0ac7-122"><xref:System.Xml.Linq.XNode></span></span>  
  
-   <span data-ttu-id="d0ac7-123"><xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="d0ac7-123"><xref:System.Xml.Linq.XAttribute></span></span>  
  
-   <span data-ttu-id="d0ac7-124">实现的任何类型<xref:System.Collections.Generic.IEnumerable%601></xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d0ac7-124">Any type that implements <xref:System.Collections.Generic.IEnumerable%601></span></span>  
  
 <span data-ttu-id="d0ac7-125">如果对象实现<xref:System.Collections.Generic.IEnumerable%601>，枚举中对象的集合，并添加集合中的所有项。</xref:System.Collections.Generic.IEnumerable%601></span><span class="sxs-lookup"><span data-stu-id="d0ac7-125">If an object implements <xref:System.Collections.Generic.IEnumerable%601>, the collection in the object is enumerated, and all items in the collection are added.</span></span> <span data-ttu-id="d0ac7-126">如果集合包含<xref:System.Xml.Linq.XNode>或<xref:System.Xml.Linq.XAttribute>对象，则单独添加集合中的每个项。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="d0ac7-126">If the collection contains <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, each item in the collection is added separately.</span></span> <span data-ttu-id="d0ac7-127">如果集合包含文本（或转换成文本的对象），则集合中的文本是串联在一起的，并作为单个文本节点添加。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-127">If the collection contains text (or objects that are converted to text), the text in the collection is concatenated and added as a single text node.</span></span>  
  
 <span data-ttu-id="d0ac7-128">如果内容为 `null`，则不添加任何内容。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-128">If content is `null`, nothing is added.</span></span> <span data-ttu-id="d0ac7-129">传递集合时，集合中的项可以为 `null`。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-129">When passing a collection items in the collection can be `null`.</span></span> <span data-ttu-id="d0ac7-130">集合中的 `null` 项对树没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-130">A `null` item in the collection has no effect on the tree.</span></span>  
  
 <span data-ttu-id="d0ac7-131">添加的属性必须在其包含元素内具有唯一名称。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-131">An added attribute must have a unique name within its containing element.</span></span>  
  
 <span data-ttu-id="d0ac7-132">添加时<xref:System.Xml.Linq.XNode>或<xref:System.Xml.Linq.XAttribute>对象时，如果新内容没有父级，则对象简单地附加到 XML 树。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="d0ac7-132">When adding <xref:System.Xml.Linq.XNode> or <xref:System.Xml.Linq.XAttribute> objects, if the new content has no parent, then the objects are simply attached to the XML tree.</span></span> <span data-ttu-id="d0ac7-133">如果新内容已经有父级，并且是另一 XML 树的一部分，则克隆新内容，并将新克隆的内容附加到 XML 树。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-133">If the new content already is parented and is part of another XML tree, then the new content is cloned, and the newly cloned content is attached to the XML tree.</span></span>  
  
## <a name="valid-content-for-documents"></a><span data-ttu-id="d0ac7-134">文档的有效内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-134">Valid Content for Documents</span></span>  
 <span data-ttu-id="d0ac7-135">属性和简单内容无法添加到文档。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-135">Attributes and simple content cannot be added to a document.</span></span>  
  
 <span data-ttu-id="d0ac7-136">不需要您创建<xref:System.Xml.Linq.XDocument>。</xref:System.Xml.Linq.XDocument>的许多方案</span><span class="sxs-lookup"><span data-stu-id="d0ac7-136">There are not many scenarios that require you to create an <xref:System.Xml.Linq.XDocument>.</span></span> <span data-ttu-id="d0ac7-137">相反，您通常可以创建 XML 树与<xref:System.Xml.Linq.XElement>根节点。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d0ac7-137">Instead, you can usually create your XML trees with an <xref:System.Xml.Linq.XElement> root node.</span></span> <span data-ttu-id="d0ac7-138">除非有特定要求创建文档 （例如，因为您必须在顶级创建处理指令和注释，或者必须支持文档类型），通常会更方便地使用<xref:System.Xml.Linq.XElement>作为根节点。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d0ac7-138">Unless you have a specific requirement to create a document (for example, because you have to create processing instructions and comments at the top level, or you have to support document types), it is often more convenient to use <xref:System.Xml.Linq.XElement> as your root node.</span></span>  
  
 <span data-ttu-id="d0ac7-139">文档的有效内容包括：</span><span class="sxs-lookup"><span data-stu-id="d0ac7-139">Valid content for a document includes the following:</span></span>  
  
-   <span data-ttu-id="d0ac7-140">零个或一个<xref:System.Xml.Linq.XDocumentType>对象。</xref:System.Xml.Linq.XDocumentType></span><span class="sxs-lookup"><span data-stu-id="d0ac7-140">Zero or one <xref:System.Xml.Linq.XDocumentType> objects.</span></span> <span data-ttu-id="d0ac7-141">文档类型必须在元素之前。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-141">The document types must come before the element.</span></span>  
  
-   <span data-ttu-id="d0ac7-142">零个或一个元素。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-142">Zero or one element.</span></span>  
  
-   <span data-ttu-id="d0ac7-143">零个或多个注释。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-143">Zero or more comments.</span></span>  
  
-   <span data-ttu-id="d0ac7-144">零个或多个处理指令。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-144">Zero or more processing instructions.</span></span>  
  
-   <span data-ttu-id="d0ac7-145">零个或多个仅包含空白的文本节点。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-145">Zero or more text nodes that contain only white space.</span></span>  
  
## <a name="constructors-and-functions-that-allow-adding-content"></a><span data-ttu-id="d0ac7-146">允许添加内容的构造函数和函数</span><span class="sxs-lookup"><span data-stu-id="d0ac7-146">Constructors and Functions that Allow Adding Content</span></span>  
 <span data-ttu-id="d0ac7-147">下面的方法允许您将子内容添加到<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>::</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d0ac7-147">The following methods allow you to add child content to an <xref:System.Xml.Linq.XElement> or an <xref:System.Xml.Linq.XDocument>:</span></span>  
  
|<span data-ttu-id="d0ac7-148">方法</span><span class="sxs-lookup"><span data-stu-id="d0ac7-148">Method</span></span>|<span data-ttu-id="d0ac7-149">说明</span><span class="sxs-lookup"><span data-stu-id="d0ac7-149">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="d0ac7-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></xref:System.Xml.Linq.XElement.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-150"><xref:System.Xml.Linq.XElement.%23ctor%2A></span></span>|<span data-ttu-id="d0ac7-151">构造<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="d0ac7-151">Constructs an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="d0ac7-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></xref:System.Xml.Linq.XDocument.%23ctor%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-152"><xref:System.Xml.Linq.XDocument.%23ctor%2A></span></span>|<span data-ttu-id="d0ac7-153">构造<xref:System.Xml.Linq.XDocument>。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="d0ac7-153">Constructs a <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="d0ac7-154"><xref:System.Xml.Linq.XContainer.Add%2A></xref:System.Xml.Linq.XContainer.Add%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-154"><xref:System.Xml.Linq.XContainer.Add%2A></span></span>|<span data-ttu-id="d0ac7-155"><xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>.</xref:System.Xml.Linq.XDocument></xref:System.Xml.Linq.XElement>的子内容的末尾添加</span><span class="sxs-lookup"><span data-stu-id="d0ac7-155">Adds to the end of the child content of the <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>.</span></span>|  
|<span data-ttu-id="d0ac7-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-156"><xref:System.Xml.Linq.XNode.AddAfterSelf%2A></span></span>|<span data-ttu-id="d0ac7-157">在<xref:System.Xml.Linq.XNode>。</xref:System.Xml.Linq.XNode>之后添加内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-157">Adds content after the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="d0ac7-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-158"><xref:System.Xml.Linq.XNode.AddBeforeSelf%2A></span></span>|<span data-ttu-id="d0ac7-159"><xref:System.Xml.Linq.XNode>。</xref:System.Xml.Linq.XNode>之前添加的内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-159">Adds content before the <xref:System.Xml.Linq.XNode>.</span></span>|  
|<span data-ttu-id="d0ac7-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></xref:System.Xml.Linq.XContainer.AddFirst%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-160"><xref:System.Xml.Linq.XContainer.AddFirst%2A></span></span>|<span data-ttu-id="d0ac7-161"><xref:System.Xml.Linq.XContainer>。</xref:System.Xml.Linq.XContainer>的子内容的开头添加内容</span><span class="sxs-lookup"><span data-stu-id="d0ac7-161">Adds content at the beginning of the child content of the <xref:System.Xml.Linq.XContainer>.</span></span>|  
|<span data-ttu-id="d0ac7-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></xref:System.Xml.Linq.XElement.ReplaceAll%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-162"><xref:System.Xml.Linq.XElement.ReplaceAll%2A></span></span>|<span data-ttu-id="d0ac7-163">替换<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement>的所有内容 （子节点和属性）</span><span class="sxs-lookup"><span data-stu-id="d0ac7-163">Replaces all content (child nodes and attributes) of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="d0ac7-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-164"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A></span></span>|<span data-ttu-id="d0ac7-165">替换<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement>的属性</span><span class="sxs-lookup"><span data-stu-id="d0ac7-165">Replaces the attributes of an <xref:System.Xml.Linq.XElement>.</span></span>|  
|<span data-ttu-id="d0ac7-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-166"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A></span></span>|<span data-ttu-id="d0ac7-167">用新内容替换子节点。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-167">Replaces the children nodes with new content.</span></span>|  
|<span data-ttu-id="d0ac7-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></xref:System.Xml.Linq.XNode.ReplaceWith%2A></span><span class="sxs-lookup"><span data-stu-id="d0ac7-168"><xref:System.Xml.Linq.XNode.ReplaceWith%2A></span></span>|<span data-ttu-id="d0ac7-169">用新内容替换节点。</span><span class="sxs-lookup"><span data-stu-id="d0ac7-169">Replaces a node with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d0ac7-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d0ac7-170">See Also</span></span>  
 [<span data-ttu-id="d0ac7-171">创建 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d0ac7-171">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
