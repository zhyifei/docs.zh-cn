---
title: "创建 XML 树 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: e86ba12b-17de-4579-81bb-66322b84cfbe
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
ms.openlocfilehash: c60746a3da6255e4c245febf55151b41186a75b7
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="creating-xml-trees-visual-basic"></a><span data-ttu-id="566d5-102">创建 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-102">Creating XML Trees (Visual Basic)</span></span>
<span data-ttu-id="566d5-103">最常见的 XML 任务之一是构造 XML 树。</span><span class="sxs-lookup"><span data-stu-id="566d5-103">One of the most common XML tasks is constructing an XML tree.</span></span> <span data-ttu-id="566d5-104">本节介绍多种创建 XML 树的方法。</span><span class="sxs-lookup"><span data-stu-id="566d5-104">This section describes several ways to create them.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="566d5-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="566d5-105">In This Section</span></span>  
  
|<span data-ttu-id="566d5-106">主题</span><span class="sxs-lookup"><span data-stu-id="566d5-106">Topic</span></span>|<span data-ttu-id="566d5-107">说明</span><span class="sxs-lookup"><span data-stu-id="566d5-107">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="566d5-108">功能构造 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-108">Functional Construction (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-construction-linq-to-xml.md)|<span data-ttu-id="566d5-109">提供对 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 中的功能构造的概述。</span><span class="sxs-lookup"><span data-stu-id="566d5-109">Provides an overview of functional construction in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span> <span data-ttu-id="566d5-110">功能构造使您能在单条语句中创建全部或部分 XML 树。</span><span class="sxs-lookup"><span data-stu-id="566d5-110">Functional construction enables you to create all or part of your XML tree in a single statement.</span></span> <span data-ttu-id="566d5-111">本主题演示如何在构造 XML 树时嵌入查询。</span><span class="sxs-lookup"><span data-stu-id="566d5-111">This topic also shows how to embed queries when constructing an XML tree.</span></span>|  
|[<span data-ttu-id="566d5-112">在 Visual Basic 中的 XML 文本简介</span><span class="sxs-lookup"><span data-stu-id="566d5-112">Introduction to XML Literals in Visual Basic</span></span>](../../../../visual-basic/programming-guide/concepts/linq/introduction-to-xml-literals.md)|<span data-ttu-id="566d5-113">快速介绍如何使用 XML 文本在 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 中创建树。</span><span class="sxs-lookup"><span data-stu-id="566d5-113">Provides a quick introduction to creating trees in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] by using XML literals.</span></span> <span data-ttu-id="566d5-114">本主题包括到 XML 文本的 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="566d5-114">This topic includes links to the [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] documentation of XML literals.</span></span>|  
|[<span data-ttu-id="566d5-115">克隆与附加 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-115">Cloning vs. Attaching (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/cloning-vs-attaching.md)|<span data-ttu-id="566d5-116">演示从现有 XML 树（先克隆节点然后添加）添加节点与添加没有父节点的节点（只是简单地附加）之间的差别。</span><span class="sxs-lookup"><span data-stu-id="566d5-116">Demonstrates the difference between adding nodes from an existing XML tree (nodes are cloned and then added) and adding nodes with no parent (they are simply attached).</span></span>|  
|[<span data-ttu-id="566d5-117">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-117">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)|<span data-ttu-id="566d5-118">演示如何从不同的源分析 XML。</span><span class="sxs-lookup"><span data-stu-id="566d5-118">Shows how to parse XML from a variety of sources.</span></span> [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]<span data-ttu-id="566d5-119">上层<xref:System.Xml.XmlReader>，它用于分析 XML。</xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="566d5-119"> is layered on top of <xref:System.Xml.XmlReader>, which is used to parse the XML.</span></span>|  
|[<span data-ttu-id="566d5-120">如何︰ 填充 XML 树使用 XmlWriter (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-120">How to: Populate an XML Tree with an XmlWriter (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-with-an-xmlwriter-linq-to-xml.md)|<span data-ttu-id="566d5-121">演示如何通过使用<xref:System.Xml.XmlWriter>。</xref:System.Xml.XmlWriter>填充 XML 树</span><span class="sxs-lookup"><span data-stu-id="566d5-121">Shows how to populate an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="566d5-122">如何︰ 使用 XSD (LINQ to XML) 进行验证 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-122">How to: Validate Using XSD (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-validate-using-xsd-linq-to-xml.md)|<span data-ttu-id="566d5-123">演示如何使用 XSD 验证 XML 树。</span><span class="sxs-lookup"><span data-stu-id="566d5-123">Shows how to validate an XML tree using XSD.</span></span>|  
|[<span data-ttu-id="566d5-124">XElement 和 XDocument 对象的有效内容</span><span class="sxs-lookup"><span data-stu-id="566d5-124">Valid Content of XElement and XDocument Objects</span></span>](../../../../visual-basic/programming-guide/concepts/linq/valid-content-of-xelement-and-xdocument-objects.md)|<span data-ttu-id="566d5-125">描述可以传递给构造函数的有效自变量，以及用于向元素和文档添加内容的方法。</span><span class="sxs-lookup"><span data-stu-id="566d5-125">Describes the valid arguments that can be passed to the constructors and methods that are used to add content to elements and documents.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="566d5-126">另请参阅</span><span class="sxs-lookup"><span data-stu-id="566d5-126">See Also</span></span>  
 [<span data-ttu-id="566d5-127">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="566d5-127">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
