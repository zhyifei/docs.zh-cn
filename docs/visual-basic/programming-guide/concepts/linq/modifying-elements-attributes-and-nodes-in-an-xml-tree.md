---
title: "修改元素、 特性和节点在 XML Tree1 |Microsoft 文档"
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
ms.assetid: 865cf54e-f8ac-4871-863b-a3e6fc61a4b9
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 88531f2af88074f4406c4859354860829efda69f
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="4e2a3-102">修改 XML 树中的元素、特性和节点</span><span class="sxs-lookup"><span data-stu-id="4e2a3-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="4e2a3-103">下表汇总了修改元素、元素的子元素或元素属性 (Attribute) 时可以使用的方法和属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="4e2a3-104">下面的方法修改<xref:System.Xml.Linq.XElement>。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4e2a3-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="4e2a3-105">方法</span><span class="sxs-lookup"><span data-stu-id="4e2a3-105">Method</span></span>|<span data-ttu-id="4e2a3-106">说明</span><span class="sxs-lookup"><span data-stu-id="4e2a3-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e2a3-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-107"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-108">用已分析的 XML 替换元素。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-108">Replaces an element with parsed XML.</span></span>|  
|<span data-ttu-id="4e2a3-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-109"><xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-110">移除元素的所有内容（子节点和属性）。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-110">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="4e2a3-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-111"><xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-112">移除元素的属性。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-112">Removes the attributes of an element.</span></span>|  
|<span data-ttu-id="4e2a3-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-113"><xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-114">替换元素的所有内容（子节点和属性）。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-114">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<span data-ttu-id="4e2a3-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-115"><xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-116">替换元素的属性。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-116">Replaces the attributes of an element.</span></span>|  
|<span data-ttu-id="4e2a3-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-117"><xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-118">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-118">Sets the value of an attribute.</span></span> <span data-ttu-id="4e2a3-119">如果该属性不存在，则创建该属性。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-119">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="4e2a3-120">如果值设置为 `null`，则移除该属性。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-120">If the value is set to `null`, removes the attribute.</span></span>|  
|<span data-ttu-id="4e2a3-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-121"><xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-122">设置子元素的值。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-122">Sets the value of a child element.</span></span> <span data-ttu-id="4e2a3-123">如果该元素不存在，则创建该元素。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-123">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="4e2a3-124">如果值设置为 `null`，则移除该元素。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-124">If the value is set to `null`, removes the element.</span></span>|  
|<span data-ttu-id="4e2a3-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-125"><xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-126">用指定的文本替换元素的内容（子节点）。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-126">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<span data-ttu-id="4e2a3-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-127"><xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-128">设置元素的值。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-128">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="4e2a3-129">下面的方法修改<xref:System.Xml.Linq.XAttribute>。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="4e2a3-129">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="4e2a3-130">方法</span><span class="sxs-lookup"><span data-stu-id="4e2a3-130">Method</span></span>|<span data-ttu-id="4e2a3-131">描述</span><span class="sxs-lookup"><span data-stu-id="4e2a3-131">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e2a3-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-132"><xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-133">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-133">Sets the value of an attribute.</span></span>|  
|<span data-ttu-id="4e2a3-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-134"><xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-135">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-135">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="4e2a3-136">下面的方法修改<xref:System.Xml.Linq.XNode>(包括<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>)。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XNode></span><span class="sxs-lookup"><span data-stu-id="4e2a3-136">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="4e2a3-137">方法</span><span class="sxs-lookup"><span data-stu-id="4e2a3-137">Method</span></span>|<span data-ttu-id="4e2a3-138">描述</span><span class="sxs-lookup"><span data-stu-id="4e2a3-138">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e2a3-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-139"><xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-140">用新内容替换节点。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-140">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="4e2a3-141">下面的方法修改<xref:System.Xml.Linq.XContainer>(<xref:System.Xml.Linq.XElement>或<xref:System.Xml.Linq.XDocument>)。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XContainer></span><span class="sxs-lookup"><span data-stu-id="4e2a3-141">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="4e2a3-142">方法</span><span class="sxs-lookup"><span data-stu-id="4e2a3-142">Method</span></span>|<span data-ttu-id="4e2a3-143">说明</span><span class="sxs-lookup"><span data-stu-id="4e2a3-143">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="4e2a3-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="4e2a3-144"><xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName></span></span>|<span data-ttu-id="4e2a3-145">用新内容替换子节点。</span><span class="sxs-lookup"><span data-stu-id="4e2a3-145">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4e2a3-146">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4e2a3-146">See Also</span></span>  
 [<span data-ttu-id="4e2a3-147">修改 XML 树 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4e2a3-147">Modifying XML Trees (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)
