---
title: 内存中 XML 数据处理
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f1a4587838180896b52bb79d447ed7ede3e22d1a
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836482"
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="e571a-102">内存中 XML 数据处理</span><span class="sxs-lookup"><span data-stu-id="e571a-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="e571a-103">Microsoft .NET Framework 包括三种用于处理 XML 数据的模型：<xref:System.Xml.XmlDocument> 类、<xref:System.Xml.XPath.XPathDocument> 类，以及 [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) 和 [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)。</span><span class="sxs-lookup"><span data-stu-id="e571a-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML (C#)](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) and [LINQ to XML (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md).</span></span>  
  
 <span data-ttu-id="e571a-104"><xref:System.Xml.XmlDocument> 类实现 W3C 文档对象模型 (DOM) 级别 1 核心和 DOM 级别 2 核心建议。</span><span class="sxs-lookup"><span data-stu-id="e571a-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="e571a-105">DOM 是 XML 文档的内存中（缓存）树表示形式。</span><span class="sxs-lookup"><span data-stu-id="e571a-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="e571a-106">使用 <xref:System.Xml.XmlDocument> 及其相关的类，可以构造 XML 文档、加载和访问数据、修改数据以及保存更改。</span><span class="sxs-lookup"><span data-stu-id="e571a-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="e571a-107"><xref:System.Xml.XPath.XPathDocument> 类是基于 XPath 数据模型的只读的、内存中的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="e571a-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="e571a-108"><xref:System.Xml.XPath.XPathNavigator> 类使用 XML 文档的游标模型提供多种编辑选项和浏览功能，该模型包含在只读的 <xref:System.Xml.XPath.XPathDocument> 类以及 <xref:System.Xml.XmlDocument> 类中。</span><span class="sxs-lookup"><span data-stu-id="e571a-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="e571a-109">[LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) 是.NET Framework 3.5 版中引入的用于处理 XML 数据的模型。</span><span class="sxs-lookup"><span data-stu-id="e571a-109">[LINQ to XML](../../../csharp/programming-guide/concepts/linq/linq-to-xml.md) is a model introduced in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="e571a-110">这是利用[语言集成查询 (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md) 的内存中模型。</span><span class="sxs-lookup"><span data-stu-id="e571a-110">It's an in-memory model that leverages [Language-Integrated Query (LINQ)](../../../csharp/programming-guide/concepts/linq/index.md).</span></span> <span data-ttu-id="e571a-111">LINQ 扩展 C# 和 Visual Basic 的语言语法以提供新的查询功能。</span><span class="sxs-lookup"><span data-stu-id="e571a-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e571a-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="e571a-112">In This Section</span></span>  
 [<span data-ttu-id="e571a-113">使用 DOM 模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="e571a-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="e571a-114">讨论如何使用 <xref:System.Xml.XmlDocument> 及其相关的类来处理 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="e571a-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="e571a-115">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="e571a-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="e571a-116">讨论如何使用 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDocument> 和 <xref:System.Xml.XPath.XPathNavigator> 类来处理 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="e571a-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="e571a-117">使用 LINQ to XML 处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="e571a-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="e571a-118">简要概述 LINQ to XML 并提供到 LINQ to XML 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="e571a-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="e571a-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="e571a-119">Related Sections</span></span>  
 [<span data-ttu-id="e571a-120">XML 文档和数据</span><span class="sxs-lookup"><span data-stu-id="e571a-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
