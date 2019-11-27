---
title: 操作 XML
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ to XML [Visual Basic], manipulating XML
- Visual Basic code, XML
- XML [Visual Basic], manipulating
ms.assetid: da32cffb-198d-41b1-9af3-260fe32e3b7d
ms.openlocfilehash: 2565f43c1014bf0fa9fab1618fedfd1bd6bdb7ca
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74330441"
---
# <a name="manipulating-xml-in-visual-basic"></a><span data-ttu-id="9e5c4-102">在 Visual Basic 中操作 XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-102">Manipulating XML in Visual Basic</span></span>
<span data-ttu-id="9e5c4-103">您可以使用*xml 文本*从外部源（如字符串、文件或流）加载 XML。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-103">You can use *XML literals* to load XML from an external source such as a string, file, or stream.</span></span> <span data-ttu-id="9e5c4-104">然后，可以使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 来操作 XML，并使用 [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] 查询 XML。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-104">You can then use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] to manipulate the XML and use [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] to query the XML.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9e5c4-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="9e5c4-105">In This Section</span></span>  
 [<span data-ttu-id="9e5c4-106">如何：从文件、字符串或流加载 XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-106">How to: Load XML from a File, String, or Stream</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-load-xml-from-a-file-string-or-stream.md)  
 <span data-ttu-id="9e5c4-107">演示如何将 XML 加载到 <xref:System.Xml.Linq.XDocument> 或从文本文件、string 或 stream <xref:System.Xml.Linq.XElement> 对象。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-107">Demonstrates how to load XML into an <xref:System.Xml.Linq.XDocument> or <xref:System.Xml.Linq.XElement> object from a text file, string, or stream.</span></span>  
  
 [<span data-ttu-id="9e5c4-108">如何：使用 LINQ 转换 XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-108">How to: Transform XML by Using LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-transform-xml-by-using-linq.md)  
 <span data-ttu-id="9e5c4-109">演示如何将 <xref:System.Xml.Linq.XDocument> 对象的内容转换为新的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-109">Demonstrates how to transform the contents of an <xref:System.Xml.Linq.XDocument> object into a new XML document.</span></span>  
  
 [<span data-ttu-id="9e5c4-110">如何：修改 XML 文本</span><span class="sxs-lookup"><span data-stu-id="9e5c4-110">How to: Modify XML Literals</span></span>](../../../../visual-basic/programming-guide/language-features/xml/how-to-modify-xml-literals.md)  
 <span data-ttu-id="9e5c4-111">演示如何修改 XML 文本中的元素、特性和值。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-111">Demonstrates how to modify the elements, attributes, and values in an XML literal.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="9e5c4-112">相关章节</span><span class="sxs-lookup"><span data-stu-id="9e5c4-112">Related Sections</span></span>  
 [<span data-ttu-id="9e5c4-113">XML 轴属性</span><span class="sxs-lookup"><span data-stu-id="9e5c4-113">XML Axis Properties</span></span>](../../../../visual-basic/language-reference/xml-axis/index.md)  
 <span data-ttu-id="9e5c4-114">提供一些链接，这些链接指向描述各种 XML 访问属性的部分。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-114">Provides links to sections that describe the various XML access properties.</span></span>  
  
 [<span data-ttu-id="9e5c4-115">Visual Basic 中的 LINQ to XML 概述</span><span class="sxs-lookup"><span data-stu-id="9e5c4-115">Overview of LINQ to XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 <span data-ttu-id="9e5c4-116">介绍如何在 Visual Basic 中使用 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-116">Provides an introduction to using [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
 [<span data-ttu-id="9e5c4-117">在 Visual Basic 中创建 XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-117">Creating XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/creating-xml.md)  
 <span data-ttu-id="9e5c4-118">介绍如何使用 Visual Basic 中的 XML 文本。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-118">Provides an introduction to using XML literals in Visual Basic.</span></span>  
  
 [<span data-ttu-id="9e5c4-119">在 Visual Basic 中访问 XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-119">Accessing XML in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/xml/accessing-xml.md)  
 <span data-ttu-id="9e5c4-120">演示如何在 Visual Basic 中访问 XML 元素或文档的各个部分。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-120">Demonstrates how to access parts of an XML element or document in Visual Basic.</span></span>  
  
 [<span data-ttu-id="9e5c4-121">XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-121">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)  
 <span data-ttu-id="9e5c4-122">提供一些链接，这些链接指向介绍如何使用 Visual Basic 中 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的部分。</span><span class="sxs-lookup"><span data-stu-id="9e5c4-122">Provides links to sections that describe how to use [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] in Visual Basic.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e5c4-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9e5c4-123">See also</span></span>

- [<span data-ttu-id="9e5c4-124">XML</span><span class="sxs-lookup"><span data-stu-id="9e5c4-124">XML</span></span>](../../../../visual-basic/programming-guide/language-features/xml/index.md)
- [<span data-ttu-id="9e5c4-125">LINQ</span><span class="sxs-lookup"><span data-stu-id="9e5c4-125">LINQ</span></span>](../../../../visual-basic/programming-guide/language-features/linq/index.md)
- [<span data-ttu-id="9e5c4-126">Visual Basic 中的 LINQ 简介</span><span class="sxs-lookup"><span data-stu-id="9e5c4-126">Introduction to LINQ in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
