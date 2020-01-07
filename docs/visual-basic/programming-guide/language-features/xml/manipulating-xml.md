---
title: 操作 XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: bb5aed5099d81f8c8898cd61523b90a43f27db78
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/03/2020
ms.locfileid: "75636154"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="e5855-102">在 Visual Basic 中操作 XML</span><span class="sxs-lookup"><span data-stu-id="e5855-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="e5855-103">您可以使用*xml 文本*从外部源（如字符串、文件或流）加载 XML。</span><span class="sxs-lookup"><span data-stu-id="e5855-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="e5855-104">然后，可以使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 来操作 XML，并使用语言集成查询（LINQ）来查询 XML。</span><span class="sxs-lookup"><span data-stu-id="e5855-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use Language-Integrated Query (LINQ) to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e5855-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="e5855-105">In This Section</span></span>  
 [<span data-ttu-id="e5855-106">如何：从文件、字符串或流加载 XML</span><span class="sxs-lookup"><span data-stu-id="e5855-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="e5855-107">演示如何将 XML 加载到 <xref:System.Xml.Linq.XDocument> 或从文本文件、string 或 stream <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="e5855-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="e5855-108">如何：使用 LINQ 转换 XML</span><span class="sxs-lookup"><span data-stu-id="e5855-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="e5855-109">演示如何将 <xref:System.Xml.Linq.XDocument> 对象的内容转换为新的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="e5855-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="e5855-110">如何：修改 XML 文本</span><span class="sxs-lookup"><span data-stu-id="e5855-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="e5855-111">演示如何修改 XML 文本中的元素、特性和值。</span><span class="sxs-lookup"><span data-stu-id="e5855-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e5855-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="e5855-112">Related Sections</span></span>  
 [<span data-ttu-id="e5855-113">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="e5855-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="e5855-114">提供一些链接，这些链接指向描述各种 XML 访问属性的部分。</span><span class="sxs-lookup"><span data-stu-id="e5855-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="e5855-115">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="e5855-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="e5855-116">介绍如何在 Visual Basic 中使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e5855-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="e5855-117">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="e5855-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="e5855-118">介绍如何使用 Visual Basic 中的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="e5855-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="e5855-119">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="e5855-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="e5855-120">演示如何在 Visual Basic 中访问 XML 元素或文档的各个部分。</span><span class="sxs-lookup"><span data-stu-id="e5855-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="e5855-121">XML</span><span class="sxs-lookup"><span data-stu-id="e5855-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="e5855-122">提供一些链接，这些链接指向介绍如何使用 Visual Basic 中 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的部分。</span><span class="sxs-lookup"><span data-stu-id="e5855-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5855-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5855-123">See also</span></span>

- [<span data-ttu-id="e5855-124">XML</span><span class="sxs-lookup"><span data-stu-id="e5855-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="e5855-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="e5855-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="e5855-126">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="e5855-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
