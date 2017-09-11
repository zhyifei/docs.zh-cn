---
title: "在 Visual Basic 中操作 XML |Microsoft 文档"
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
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
caps.latest.revision: 5
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 62b955d78eb507aab4c786e84f3044ba54a38ebc
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="83eb0-102">在 Visual Basic 中操作 XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="83eb0-103">您可以使用*XML 文本*从外部源如字符串、 文件或流加载 XML。</span><span class="sxs-lookup"><span data-stu-id="83eb0-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="83eb0-104">然后，可以使用[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]操作 XML，并使用[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)]来查询 XML。</span><span class="sxs-lookup"><span data-stu-id="83eb0-104">You can then use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext_md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83eb0-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="83eb0-105">In This Section</span></span>  
 [<span data-ttu-id="83eb0-106">如何：从文件、字符串或流加载 XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="83eb0-107">演示如何以 XML 加载到<xref:System.Xml.Linq.XDocument>或<xref:System.Xml.Linq.XElement>文本文件、 字符串或流中的对象。</xref:System.Xml.Linq.XElement> </xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83eb0-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="83eb0-108">如何：使用 LINQ 转换 XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="83eb0-109">演示如何将转换的内容<xref:System.Xml.Linq.XDocument>对象插入新的 XML 文档。</xref:System.Xml.Linq.XDocument></span><span class="sxs-lookup"><span data-stu-id="83eb0-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="83eb0-110">如何：修改 XML 文本</span><span class="sxs-lookup"><span data-stu-id="83eb0-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="83eb0-111">演示如何修改元素、 属性和 XML 文本中的值。</span><span class="sxs-lookup"><span data-stu-id="83eb0-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="83eb0-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="83eb0-112">Related Sections</span></span>  
 [<span data-ttu-id="83eb0-113">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="83eb0-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/xml-axis-properties.md)  
 <span data-ttu-id="83eb0-114">提供指向介绍了各种 XML 访问属性的章节。</span><span class="sxs-lookup"><span data-stu-id="83eb0-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="83eb0-115">LINQ to XML 在 Visual Basic 中的概述</span><span class="sxs-lookup"><span data-stu-id="83eb0-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="83eb0-116">提供介绍如何使用[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="83eb0-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="83eb0-117">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="83eb0-118">提供介绍如何在 Visual Basic 中使用 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="83eb0-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="83eb0-119">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="83eb0-120">演示如何访问的 XML 元素或在 Visual Basic 中的文档部分。</span><span class="sxs-lookup"><span data-stu-id="83eb0-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="83eb0-121">XML</span><span class="sxs-lookup"><span data-stu-id="83eb0-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="83eb0-122">提供指向描述如何使用部分的[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]在 Visual Basic 中。</span><span class="sxs-lookup"><span data-stu-id="83eb0-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83eb0-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="83eb0-123">See Also</span></span>  
 <span data-ttu-id="83eb0-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span><span class="sxs-lookup"><span data-stu-id="83eb0-124">[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md) </span></span>  
<span data-ttu-id="83eb0-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span><span class="sxs-lookup"><span data-stu-id="83eb0-125"> [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md) </span></span>  
<span data-ttu-id="83eb0-126"> [在 Visual Basic 中的 LINQ 简介](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span><span class="sxs-lookup"><span data-stu-id="83eb0-126"> [Introduction to LINQ in Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)</span></span>
