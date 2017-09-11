---
title: "LINQ to XML 编程概述 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: a7c07d0a-1fae-4610-ae51-56dd7075cc14
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
ms.openlocfilehash: 57d52b1bc46263e4e8e662be6a83bf4718813b43
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="linq-to-xml-programming-overview-visual-basic"></a><span data-ttu-id="4afd2-102">LINQ to XML 编程概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-102">LINQ to XML Programming Overview (Visual Basic)</span></span>
<span data-ttu-id="4afd2-103">这些主题提供有关 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 类的高级概述信息，以及有关三个最重要类的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4afd2-103">These topics provide high-level overview information about the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes, as well as detailed information about three of the most important classes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="4afd2-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="4afd2-104">In This Section</span></span>  
  
|<span data-ttu-id="4afd2-105">主题</span><span class="sxs-lookup"><span data-stu-id="4afd2-105">Topic</span></span>|<span data-ttu-id="4afd2-106">说明</span><span class="sxs-lookup"><span data-stu-id="4afd2-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="4afd2-107">函数编程与过程性编程 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-107">Functional vs. Procedural Programming (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/functional-vs-procedural-programming-linq-to-xml.md)|<span data-ttu-id="4afd2-108">总览介绍编写 LINQ to XML 应用程序的两种主要方法。</span><span class="sxs-lookup"><span data-stu-id="4afd2-108">Provides a high level view of the two principle approaches to writing LINQ to XML applications.</span></span>|  
|[<span data-ttu-id="4afd2-109">LINQ to XML 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-109">LINQ to XML Classes Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-classes-overview.md)|<span data-ttu-id="4afd2-110">提供 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 类的概述。</span><span class="sxs-lookup"><span data-stu-id="4afd2-110">Provides an overview of the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] classes.</span></span>|  
|[<span data-ttu-id="4afd2-111">XElement 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-111">XElement Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xelement-class-overview.md)|<span data-ttu-id="4afd2-112">引入了<xref:System.Xml.Linq.XElement>类，该类表示 XML 元素。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4afd2-112">Introduces the <xref:System.Xml.Linq.XElement> class, which represents XML elements.</span></span> <span data-ttu-id="4afd2-113"><xref:System.Xml.Linq.XElement>是中的基础类之一[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]类层次结构。</xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="4afd2-113"><xref:System.Xml.Linq.XElement> is one of the fundamental classes in the [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] class hierarchy.</span></span>|  
|[<span data-ttu-id="4afd2-114">XAttribute 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-114">XAttribute Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xattribute-class-overview.md)|<span data-ttu-id="4afd2-115">引入了<xref:System.Xml.Linq.XAttribute>类，该类表示 XML 属性。</xref:System.Xml.Linq.XAttribute></span><span class="sxs-lookup"><span data-stu-id="4afd2-115">Introduces the <xref:System.Xml.Linq.XAttribute> class, which represents XML attributes.</span></span>|  
|[<span data-ttu-id="4afd2-116">XDocument 类概述 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-116">XDocument Class Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/xdocument-class-overview.md)|<span data-ttu-id="4afd2-117">引入了<xref:System.Xml.Linq.XDocument>类，该类表示 XML 文档。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="4afd2-117">Introduces the <xref:System.Xml.Linq.XDocument> class, which represents XML documents.</span></span>|  
|[<span data-ttu-id="4afd2-118">如何︰ 生成 LINQ to XML 示例 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-118">How to: Build LINQ to XML Examples (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-build-linq-to-xml-examples.md)|<span data-ttu-id="4afd2-119">包含`Imports`生成 LINQ to XML 示例所需的语句。</span><span class="sxs-lookup"><span data-stu-id="4afd2-119">Contains the `Imports` statements that are required to build the LINQ to XML examples.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4afd2-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4afd2-120">See Also</span></span>  
 [<span data-ttu-id="4afd2-121">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="4afd2-121">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
