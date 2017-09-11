---
title: "修改 XML 树3 中的元素、特性和节点"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 0ed22e4e-4c6b-4eb1-b0eb-06685efd8c33
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 432587324fbd3560da924c7516a743e623a38b1e
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="modifying-elements-attributes-and-nodes-in-an-xml-tree"></a><span data-ttu-id="6f302-102">修改 XML 树中的元素、特性和节点</span><span class="sxs-lookup"><span data-stu-id="6f302-102">Modifying Elements, Attributes, and Nodes in an XML Tree</span></span>
<span data-ttu-id="6f302-103">下表汇总了修改元素、元素的子元素或元素属性 (Attribute) 时可以使用的方法和属性 (Property)。</span><span class="sxs-lookup"><span data-stu-id="6f302-103">The following table summarizes the methods and properties that you can use to modify an element, its child elements, or its attributes.</span></span>  
  
 <span data-ttu-id="6f302-104">下面的方法修改 <xref:System.Xml.Linq.XElement>。</span><span class="sxs-lookup"><span data-stu-id="6f302-104">The following methods modify an <xref:System.Xml.Linq.XElement>.</span></span>  
  
|<span data-ttu-id="6f302-105">方法</span><span class="sxs-lookup"><span data-stu-id="6f302-105">Method</span></span>|<span data-ttu-id="6f302-106">说明</span><span class="sxs-lookup"><span data-stu-id="6f302-106">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName>|<span data-ttu-id="6f302-107">用已分析的 XML 替换元素。</span><span class="sxs-lookup"><span data-stu-id="6f302-107">Replaces an element with parsed XML.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAll%2A?displayProperty=fullName>|<span data-ttu-id="6f302-108">移除元素的所有内容（子节点和属性）。</span><span class="sxs-lookup"><span data-stu-id="6f302-108">Removes all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.RemoveAttributes%2A?displayProperty=fullName>|<span data-ttu-id="6f302-109">移除元素的属性。</span><span class="sxs-lookup"><span data-stu-id="6f302-109">Removes the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAll%2A?displayProperty=fullName>|<span data-ttu-id="6f302-110">替换元素的所有内容（子节点和属性）。</span><span class="sxs-lookup"><span data-stu-id="6f302-110">Replaces all content (child nodes and attributes) of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.ReplaceAttributes%2A?displayProperty=fullName>|<span data-ttu-id="6f302-111">替换元素的属性。</span><span class="sxs-lookup"><span data-stu-id="6f302-111">Replaces the attributes of an element.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetAttributeValue%2A?displayProperty=fullName>|<span data-ttu-id="6f302-112">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="6f302-112">Sets the value of an attribute.</span></span> <span data-ttu-id="6f302-113">如果该属性不存在，则创建该属性。</span><span class="sxs-lookup"><span data-stu-id="6f302-113">Creates the attribute if it doesn't exist.</span></span> <span data-ttu-id="6f302-114">如果值设置为 `null`，则移除该属性。</span><span class="sxs-lookup"><span data-stu-id="6f302-114">If the value is set to `null`, removes the attribute.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetElementValue%2A?displayProperty=fullName>|<span data-ttu-id="6f302-115">设置子元素的值。</span><span class="sxs-lookup"><span data-stu-id="6f302-115">Sets the value of a child element.</span></span> <span data-ttu-id="6f302-116">如果该元素不存在，则创建该元素。</span><span class="sxs-lookup"><span data-stu-id="6f302-116">Creates the element if it doesn't exist.</span></span> <span data-ttu-id="6f302-117">如果值设置为 `null`，则移除该元素。</span><span class="sxs-lookup"><span data-stu-id="6f302-117">If the value is set to `null`, removes the element.</span></span>|  
|<xref:System.Xml.Linq.XElement.Value%2A?displayProperty=fullName>|<span data-ttu-id="6f302-118">用指定的文本替换元素的内容（子节点）。</span><span class="sxs-lookup"><span data-stu-id="6f302-118">Replaces the content (child nodes) of an element with the specified text.</span></span>|  
|<xref:System.Xml.Linq.XElement.SetValue%2A?displayProperty=fullName>|<span data-ttu-id="6f302-119">设置元素的值。</span><span class="sxs-lookup"><span data-stu-id="6f302-119">Sets the value of an element.</span></span>|  
  
 <span data-ttu-id="6f302-120">下面的方法修改 <xref:System.Xml.Linq.XAttribute>。</span><span class="sxs-lookup"><span data-stu-id="6f302-120">The following methods modify an <xref:System.Xml.Linq.XAttribute>.</span></span>  
  
|<span data-ttu-id="6f302-121">方法</span><span class="sxs-lookup"><span data-stu-id="6f302-121">Method</span></span>|<span data-ttu-id="6f302-122">描述</span><span class="sxs-lookup"><span data-stu-id="6f302-122">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XAttribute.Value%2A?displayProperty=fullName>|<span data-ttu-id="6f302-123">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="6f302-123">Sets the value of an attribute.</span></span>|  
|<xref:System.Xml.Linq.XAttribute.SetValue%2A?displayProperty=fullName>|<span data-ttu-id="6f302-124">设置属性的值。</span><span class="sxs-lookup"><span data-stu-id="6f302-124">Sets the value of an attribute.</span></span>|  
  
 <span data-ttu-id="6f302-125">下面的方法修改 <xref:System.Xml.Linq.XNode>（包括 <xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument>）。</span><span class="sxs-lookup"><span data-stu-id="6f302-125">The following methods modify an <xref:System.Xml.Linq.XNode> (including an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="6f302-126">方法</span><span class="sxs-lookup"><span data-stu-id="6f302-126">Method</span></span>|<span data-ttu-id="6f302-127">说明</span><span class="sxs-lookup"><span data-stu-id="6f302-127">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XNode.ReplaceWith%2A?displayProperty=fullName>|<span data-ttu-id="6f302-128">用新内容替换节点。</span><span class="sxs-lookup"><span data-stu-id="6f302-128">Replaces a node with new content.</span></span>|  
  
 <span data-ttu-id="6f302-129">下面的方法修改 <xref:System.Xml.Linq.XContainer>（<xref:System.Xml.Linq.XElement> 或 <xref:System.Xml.Linq.XDocument>）。</span><span class="sxs-lookup"><span data-stu-id="6f302-129">The following methods modify an <xref:System.Xml.Linq.XContainer> (an <xref:System.Xml.Linq.XElement> or <xref:System.Xml.Linq.XDocument>).</span></span>  
  
|<span data-ttu-id="6f302-130">方法</span><span class="sxs-lookup"><span data-stu-id="6f302-130">Method</span></span>|<span data-ttu-id="6f302-131">描述</span><span class="sxs-lookup"><span data-stu-id="6f302-131">Description</span></span>|  
|------------|-----------------|  
|<xref:System.Xml.Linq.XContainer.ReplaceNodes%2A?displayProperty=fullName>|<span data-ttu-id="6f302-132">用新内容替换子节点。</span><span class="sxs-lookup"><span data-stu-id="6f302-132">Replaces the children nodes with new content.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6f302-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f302-133">See Also</span></span>  
 [<span data-ttu-id="6f302-134">修改 XML 树 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="6f302-134">Modifying XML Trees (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/modifying-xml-trees-linq-to-xml.md)

