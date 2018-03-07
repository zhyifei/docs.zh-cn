---
title: "内存中 XML 数据处理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1bbb4d05-ead7-4bda-8ece-f86d35c57ad4
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 9fc2f9e7a9ba232c062b12e8c1aeb72eece760e2
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/23/2017
---
# <a name="processing-xml-data-in-memory"></a><span data-ttu-id="11fb6-102">内存中 XML 数据处理</span><span class="sxs-lookup"><span data-stu-id="11fb6-102">Processing XML Data In-Memory</span></span>
<span data-ttu-id="11fb6-103">Microsoft .NET Framework 包括三个 XML 数据处理模型：<xref:System.Xml.XmlDocument> 类、<xref:System.Xml.XPath.XPathDocument> 类和 [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)。</span><span class="sxs-lookup"><span data-stu-id="11fb6-103">The Microsoft .NET Framework includes three models for processing XML data: the <xref:System.Xml.XmlDocument> class, the <xref:System.Xml.XPath.XPathDocument> class, and [LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13).</span></span>  
  
 <span data-ttu-id="11fb6-104"><xref:System.Xml.XmlDocument> 类实现 W3C 文档对象模型 (DOM) 级别 1 核心和 DOM 级别 2 核心建议。</span><span class="sxs-lookup"><span data-stu-id="11fb6-104">The <xref:System.Xml.XmlDocument> class implements the W3C document object model (DOM) level 1 core and the core DOM level 2 recommendations.</span></span> <span data-ttu-id="11fb6-105">DOM 是 XML 文档的内存中（缓存）树表示形式。</span><span class="sxs-lookup"><span data-stu-id="11fb6-105">The DOM is an in-memory (cache) tree representation of an XML document.</span></span> <span data-ttu-id="11fb6-106">使用 <xref:System.Xml.XmlDocument> 及其相关的类，可以构造 XML 文档、加载和访问数据、修改数据以及保存更改。</span><span class="sxs-lookup"><span data-stu-id="11fb6-106">With the <xref:System.Xml.XmlDocument> and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
 <span data-ttu-id="11fb6-107"><xref:System.Xml.XPath.XPathDocument> 类是基于 XPath 数据模型的只读的、内存中的数据存储区。</span><span class="sxs-lookup"><span data-stu-id="11fb6-107">The <xref:System.Xml.XPath.XPathDocument> class is a read-only, in-memory data store that is based on the XPath data model.</span></span> <span data-ttu-id="11fb6-108"><xref:System.Xml.XPath.XPathNavigator> 类使用 XML 文档的游标模型提供多种编辑选项和浏览功能，该模型包含在只读的 <xref:System.Xml.XPath.XPathDocument> 类以及 <xref:System.Xml.XmlDocument> 类中。</span><span class="sxs-lookup"><span data-stu-id="11fb6-108">The <xref:System.Xml.XPath.XPathNavigator> class offers several editing options and navigation capabilities using a cursor model over XML documents contained in the read-only <xref:System.Xml.XPath.XPathDocument> class as well as the <xref:System.Xml.XmlDocument> class.</span></span>  
  
 <span data-ttu-id="11fb6-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) 是 .NET Framework 版本 3.5 中用于处理 XML 数据的新模型。</span><span class="sxs-lookup"><span data-stu-id="11fb6-109">[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) is the new model in the .NET Framework version 3.5 for processing XML data.</span></span> <span data-ttu-id="11fb6-110">这是利用 [LINQ （语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)的内存中模型。</span><span class="sxs-lookup"><span data-stu-id="11fb6-110">It is an in-memory model that leverages [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d).</span></span> <span data-ttu-id="11fb6-111">LINQ 扩展 C# 和 Visual Basic 的语言语法以提供新的查询功能。</span><span class="sxs-lookup"><span data-stu-id="11fb6-111">LINQ extends the language syntax of C# and Visual Basic to provide new query capabilities.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="11fb6-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="11fb6-112">In This Section</span></span>  
 [<span data-ttu-id="11fb6-113">使用 DOM 模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="11fb6-113">Process XML Data Using the DOM Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-dom-model.md)  
 <span data-ttu-id="11fb6-114">讨论如何使用 <xref:System.Xml.XmlDocument> 及其相关的类来处理 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="11fb6-114">Discusses using the <xref:System.Xml.XmlDocument>, and its related classes to process XML data.</span></span>  
  
 [<span data-ttu-id="11fb6-115">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="11fb6-115">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="11fb6-116">讨论如何使用 <xref:System.Xml.XPath.XPathDocument>、<xref:System.Xml.XmlDocument> 和 <xref:System.Xml.XPath.XPathNavigator> 类来处理 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="11fb6-116">Discusses using the <xref:System.Xml.XPath.XPathDocument>, <xref:System.Xml.XmlDocument>, and <xref:System.Xml.XPath.XPathNavigator> classes to process XML data.</span></span>  
  
 [<span data-ttu-id="11fb6-117">使用 LINQ to XML 处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="11fb6-117">Process XML Data Using LINQ to XML</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-linq-to-xml.md)  
 <span data-ttu-id="11fb6-118">简要概述 LINQ to XML 并提供到 LINQ to XML 文档的链接。</span><span class="sxs-lookup"><span data-stu-id="11fb6-118">Provides a brief overview of LINQ to XML and provides links to the LINQ to XML documentation.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="11fb6-119">相关章节</span><span class="sxs-lookup"><span data-stu-id="11fb6-119">Related Sections</span></span>  
 [<span data-ttu-id="11fb6-120">XML 文档和数据</span><span class="sxs-lookup"><span data-stu-id="11fb6-120">XML Documents and Data</span></span>](../../../../docs/standard/data/xml/index.md)
