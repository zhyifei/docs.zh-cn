---
title: Visual Basic 中语言集成的轴 (LINQ to XML)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8360281d1d8de0cad243297cd78e97958530bae4
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2018
---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="16866-102">Visual Basic 中语言集成的轴 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="16866-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="16866-103">本部分介绍直接内置于 Visual Basic 语言，以便可以方便地访问 XML 的功能。</span><span class="sxs-lookup"><span data-stu-id="16866-103">This section describes features built directly into the Visual Basic language to make it easy to access XML.</span></span> <span data-ttu-id="16866-104">许多中 LINQ to XML 文档的示例使用这些集成的 Visual Basic 轴。</span><span class="sxs-lookup"><span data-stu-id="16866-104">Many of the examples in the LINQ to XML documentation use these integrated Visual Basic axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="16866-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="16866-105">In This Section</span></span>  
  
|<span data-ttu-id="16866-106">主题</span><span class="sxs-lookup"><span data-stu-id="16866-106">Topic</span></span>|<span data-ttu-id="16866-107">描述</span><span class="sxs-lookup"><span data-stu-id="16866-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="16866-108">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="16866-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="16866-109">提供对以下一项的子级的访问：<xref:System.Xml.Linq.XElement> 对象、<xref:System.Xml.Linq.XDocument> 对象、<xref:System.Xml.Linq.XElement> 对象的集合或 <xref:System.Xml.Linq.XDocument> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="16866-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="16866-110">此轴等效于 <xref:System.Xml.Linq.XContainer.Elements%2A> 轴。</span><span class="sxs-lookup"><span data-stu-id="16866-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="16866-111">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="16866-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="16866-112">提供对以下各项的后代的访问：<xref:System.Xml.Linq.XElement> 对象、<xref:System.Xml.Linq.XDocument> 对象或 <xref:System.Xml.Linq.XElement> 对象的集合。</span><span class="sxs-lookup"><span data-stu-id="16866-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="16866-113">此轴等效于 <xref:System.Xml.Linq.XContainer.Descendants%2A> 轴。</span><span class="sxs-lookup"><span data-stu-id="16866-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="16866-114">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="16866-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="16866-115">提供对 <xref:System.Xml.Linq.XElement> 对象的属性的访问。</span><span class="sxs-lookup"><span data-stu-id="16866-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="16866-116">此轴大致等效于 <xref:System.Xml.Linq.XElement.Attribute%2A> 轴。</span><span class="sxs-lookup"><span data-stu-id="16866-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="16866-117">此轴与 <xref:System.Xml.Linq.XElement.Attribute%2A> 轴的不同之处在于它返回属性的值而不是一个 <xref:System.Xml.Linq.XAttribute> 对象。</span><span class="sxs-lookup"><span data-stu-id="16866-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="16866-118">扩展索引器属性</span><span class="sxs-lookup"><span data-stu-id="16866-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="16866-119">提供对集合中各个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="16866-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="16866-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="16866-120">See Also</span></span>  
 [<span data-ttu-id="16866-121">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="16866-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
