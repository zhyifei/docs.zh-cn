---
title: "语言集成的轴，在 Visual Basic (LINQ to XML) |Microsoft 文档"
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
ms.assetid: d450a556-a134-4261-b011-44e399660894
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 7ca88aed0772f4fb93ab561af4bd9a1129cbf3c5
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="language-integrated-axes-in-visual-basic-linq-to-xml"></a><span data-ttu-id="04d55-102">Visual Basic 中语言集成的轴 (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="04d55-102">Language-Integrated Axes in Visual Basic (LINQ to XML)</span></span>
<span data-ttu-id="04d55-103">本部分介绍功能直接内置于[!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]以便可以方便地访问 XML 的语言。</span><span class="sxs-lookup"><span data-stu-id="04d55-103">This section describes features built directly into the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] language to make it easy to access XML.</span></span> <span data-ttu-id="04d55-104">LINQ to XML 文档中的很多示例都使用这些集成的 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 轴。</span><span class="sxs-lookup"><span data-stu-id="04d55-104">Many of the examples in the LINQ to XML documentation use these integrated [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] axes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="04d55-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="04d55-105">In This Section</span></span>  
  
|<span data-ttu-id="04d55-106">主题</span><span class="sxs-lookup"><span data-stu-id="04d55-106">Topic</span></span>|<span data-ttu-id="04d55-107">说明</span><span class="sxs-lookup"><span data-stu-id="04d55-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="04d55-108">XML 子轴属性</span><span class="sxs-lookup"><span data-stu-id="04d55-108">XML Child Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-child-axis-property.md)|<span data-ttu-id="04d55-109">提供对以下一项的子级的访问︰<xref:System.Xml.Linq.XElement>对象，<xref:System.Xml.Linq.XDocument>对象、 一套<xref:System.Xml.Linq.XElement>对象或一套<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="04d55-109">Provides access to the children of one of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, a collection of <xref:System.Xml.Linq.XElement> objects, or a collection of <xref:System.Xml.Linq.XDocument> objects.</span></span> <span data-ttu-id="04d55-110">此轴等效于<xref:System.Xml.Linq.XContainer.Elements%2A>轴。</xref:System.Xml.Linq.XContainer.Elements%2A></span><span class="sxs-lookup"><span data-stu-id="04d55-110">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Elements%2A> axis.</span></span>|  
|[<span data-ttu-id="04d55-111">XML 子代轴属性</span><span class="sxs-lookup"><span data-stu-id="04d55-111">XML Descendant Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-descendant-axis-property.md)|<span data-ttu-id="04d55-112">提供对以下的后代的访问︰<xref:System.Xml.Linq.XElement>对象，<xref:System.Xml.Linq.XDocument>对象或集合的<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="04d55-112">Provides access to the descendants of the following: an <xref:System.Xml.Linq.XElement> object, an <xref:System.Xml.Linq.XDocument> object, or a collection of <xref:System.Xml.Linq.XElement> objects.</span></span> <span data-ttu-id="04d55-113">此轴等效于<xref:System.Xml.Linq.XContainer.Descendants%2A>轴。</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="04d55-113">This axis is equivalent to the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="04d55-114">XML 特性轴属性</span><span class="sxs-lookup"><span data-stu-id="04d55-114">XML Attribute Axis Property</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-attribute-axis-property.md)|<span data-ttu-id="04d55-115">提供对属性的访问<xref:System.Xml.Linq.XElement>对象。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="04d55-115">Provides access to an attribute of an <xref:System.Xml.Linq.XElement> object.</span></span> <span data-ttu-id="04d55-116">此轴是大致相当于<xref:System.Xml.Linq.XElement.Attribute%2A>轴。</xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="04d55-116">This axis is roughly equivalent to the <xref:System.Xml.Linq.XElement.Attribute%2A> axis.</span></span> <span data-ttu-id="04d55-117">此轴不同于<xref:System.Xml.Linq.XElement.Attribute%2A>它不返回该属性的值中的轴<xref:System.Xml.Linq.XAttribute>对象。</xref:System.Xml.Linq.XAttribute> </xref:System.Xml.Linq.XElement.Attribute%2A></span><span class="sxs-lookup"><span data-stu-id="04d55-117">This axis differs from the <xref:System.Xml.Linq.XElement.Attribute%2A> axis in that it returns the value of the attribute, not an <xref:System.Xml.Linq.XAttribute> object.</span></span>|  
|[<span data-ttu-id="04d55-118">扩展索引器属性</span><span class="sxs-lookup"><span data-stu-id="04d55-118">Extension Indexer Property</span></span>](../../../../visual-basic/language-reference/xml-axis/extension-indexer-property.md)|<span data-ttu-id="04d55-119">提供对集合中各个元素的访问。</span><span class="sxs-lookup"><span data-stu-id="04d55-119">Provides access to individual elements in a collection.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="04d55-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04d55-120">See Also</span></span>  
 [<span data-ttu-id="04d55-121">LINQ to XML 轴 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04d55-121">LINQ to XML Axes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-axes.md)
