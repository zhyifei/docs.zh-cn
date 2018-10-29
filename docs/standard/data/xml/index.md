---
title: XML 文档和数据
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: e695047f-3c0f-4045-8708-5baea91cc380
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3b5c774d566766936ebe043f264040ce26b8e9e3
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/29/2018
ms.locfileid: "50202954"
---
# <a name="xml-documents-and-data"></a><span data-ttu-id="738eb-102">XML 文档和数据</span><span class="sxs-lookup"><span data-stu-id="738eb-102">XML Documents and Data</span></span>
<span data-ttu-id="738eb-103">.NET Framework 提供了一组全面而集成的类，可用来方便地生成可以识别 XML 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="738eb-103">The .NET Framework provides a comprehensive and integrated set of classes that enable you to build XML-aware apps easily.</span></span> <span data-ttu-id="738eb-104">通过以下命名空间中的类，可以分析和编写 XML，编辑内存中的 XML 数据，进行数据验证以及 XSLT 转换。</span><span class="sxs-lookup"><span data-stu-id="738eb-104">The classes in the following namespaces support parsing and writing XML, editing XML data in memory, data validation, and XSLT transformation.</span></span>  
  
-   <xref:System.Xml>  
  
-   <xref:System.Xml.XPath>  
  
-   <xref:System.Xml.Xsl>  
  
-   <xref:System.Xml.Schema>  
  
-   <xref:System.Xml.Linq>  
  
 <span data-ttu-id="738eb-105">有关完整列表，请参阅 [System.Xml 命名空间](https://msdn.microsoft.com/library/gg145036.aspx)网页。</span><span class="sxs-lookup"><span data-stu-id="738eb-105">For a full list, see the [System.Xml Namespaces](https://msdn.microsoft.com/library/gg145036.aspx) webpage.</span></span>  
  
 <span data-ttu-id="738eb-106">这些命名空间中的类支持万维网联合会 (W3C) 建议。</span><span class="sxs-lookup"><span data-stu-id="738eb-106">The classes in these namespaces support World Wide Web Consortium (W3C) recommendations.</span></span> <span data-ttu-id="738eb-107">例如:</span><span class="sxs-lookup"><span data-stu-id="738eb-107">For example:</span></span>  
  
-   <span data-ttu-id="738eb-108"><xref:System.Xml.XmlDocument?displayProperty=nameWithType> 类可实现 [W3C 文档对象模型 (DOM) 级别 1 核心](https://www.w3.org/TR/REC-DOM-Level-1/)和 [DOM 级别 2 核心](https://www.w3.org/TR/DOM-Level-2-Core/)建议。</span><span class="sxs-lookup"><span data-stu-id="738eb-108">The <xref:System.Xml.XmlDocument?displayProperty=nameWithType> class implements the [W3C Document Object Model (DOM) Level 1 Core](https://www.w3.org/TR/REC-DOM-Level-1/) and [DOM Level 2 Core](https://www.w3.org/TR/DOM-Level-2-Core/) recommendations.</span></span>  
  
-   <span data-ttu-id="738eb-109"><xref:System.Xml.XmlReader?displayProperty=nameWithType> 和 <xref:System.Xml.XmlWriter?displayProperty=nameWithType> 类支持 [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) 和 [XML 中的命名空间](https://www.w3.org/TR/REC-xml-names/)建议。</span><span class="sxs-lookup"><span data-stu-id="738eb-109">The <xref:System.Xml.XmlReader?displayProperty=nameWithType> and <xref:System.Xml.XmlWriter?displayProperty=nameWithType> classes support the [W3C XML 1.0](https://www.w3.org/TR/2006/REC-xml-20060816/) and the [Namespaces in XML](https://www.w3.org/TR/REC-xml-names/) recommendations.</span></span>  
  
-   <span data-ttu-id="738eb-110"><xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> 类中的架构支持 [W3C XML 架构第 1 部分：结构](https://www.w3.org/TR/xmlschema-1/)和 [XML 架构第 2 部分：数据类型](https://www.w3.org/TR/xmlschema-2/)建议。</span><span class="sxs-lookup"><span data-stu-id="738eb-110">Schemas in the <xref:System.Xml.Schema.XmlSchemaSet?displayProperty=nameWithType> class support the [W3C XML Schema Part 1: Structures](https://www.w3.org/TR/xmlschema-1/) and [XML Schema Part 2: Datatypes](https://www.w3.org/TR/xmlschema-2/) recommendations.</span></span>  
  
-   <span data-ttu-id="738eb-111"><xref:System.Xml.Xsl?displayProperty=nameWithType> 命名空间中的类支持符合 [W3C XSLT 1.0](https://www.w3.org/TR/xslt) 建议的 XSLT 转换。</span><span class="sxs-lookup"><span data-stu-id="738eb-111">Classes in the <xref:System.Xml.Xsl?displayProperty=nameWithType> namespace support XSLT transformations that conform to the [W3C XSLT 1.0](https://www.w3.org/TR/xslt) recommendation.</span></span>  
  
 <span data-ttu-id="738eb-112">.NET Framework 中的 XML 类具有以下优点：</span><span class="sxs-lookup"><span data-stu-id="738eb-112">The XML classes in the .NET Framework provide these benefits:</span></span>  
  
-   <span data-ttu-id="738eb-113">**高效率。**</span><span class="sxs-lookup"><span data-stu-id="738eb-113">**Productivity.**</span></span> <span data-ttu-id="738eb-114">通过 [LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)，可更方便地用 XML 编程，并可得到与 SQL 类似的查询体验。</span><span class="sxs-lookup"><span data-stu-id="738eb-114">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13) makes it easier to program with XML and provides a query experience that is similar to SQL.</span></span>  
  
-   <span data-ttu-id="738eb-115">**扩展性。**</span><span class="sxs-lookup"><span data-stu-id="738eb-115">**Extensibility.**</span></span> <span data-ttu-id="738eb-116">.NET Framework 中的 XML 类可使用抽象基类和虚拟方法进行扩展。</span><span class="sxs-lookup"><span data-stu-id="738eb-116">The XML classes in the .NET Framework are extensible through the use of abstract base classes and virtual methods.</span></span> <span data-ttu-id="738eb-117">例如，您可以创建 <xref:System.Xml.XmlUrlResolver> 类的一个派生类，用以将缓存流存储到本地磁盘。</span><span class="sxs-lookup"><span data-stu-id="738eb-117">For example, you can create a derived class of the <xref:System.Xml.XmlUrlResolver> class that stores the cache stream to the local disk.</span></span>  
  
-   <span data-ttu-id="738eb-118">**可插入的体系结构。**</span><span class="sxs-lookup"><span data-stu-id="738eb-118">**Pluggable architecture.**</span></span> <span data-ttu-id="738eb-119">.NET Framework 提供了一种体系结构，其中的组件可以相互利用，数据可以在各组件之间传送。</span><span class="sxs-lookup"><span data-stu-id="738eb-119">The .NET Framework provides an architecture in which components can utilize one another, and data can be streamed between components.</span></span> <span data-ttu-id="738eb-120">例如，可以使用 <xref:System.Xml.XPath.XPathDocument> 类来转换数据存储（例如，<xref:System.Xml.XmlDocument> 或 <xref:System.Xml.Xsl.XslCompiledTransform> 对象），然后可将输出传送到另一个存储或作为 Web 服务的流返回。</span><span class="sxs-lookup"><span data-stu-id="738eb-120">For example, a data store, such as an <xref:System.Xml.XPath.XPathDocument> or <xref:System.Xml.XmlDocument> object, can be transformed with the <xref:System.Xml.Xsl.XslCompiledTransform> class, and the output can then be streamed either into another store or returned as a stream from a web service.</span></span>  
  
-   <span data-ttu-id="738eb-121">**性能。**</span><span class="sxs-lookup"><span data-stu-id="738eb-121">**Performance.**</span></span> <span data-ttu-id="738eb-122">为获得更佳应用程序性能，.NET Framework 中设计的某些 XML 类支持基于流的模型并具有以下特性：</span><span class="sxs-lookup"><span data-stu-id="738eb-122">For better app performance, some of the XML classes in the .NET Framework support a streaming-based model with the following characteristics:</span></span>  
  
    -   <span data-ttu-id="738eb-123">只进、拉出模型分析使用最小缓存 (<xref:System.Xml.XmlReader>)。</span><span class="sxs-lookup"><span data-stu-id="738eb-123">Minimal caching for forward-only, pull-model parsing (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="738eb-124">只进验证 (<xref:System.Xml.XmlReader>)。</span><span class="sxs-lookup"><span data-stu-id="738eb-124">Forward-only validation (<xref:System.Xml.XmlReader>).</span></span>  
  
    -   <span data-ttu-id="738eb-125">游标式导航，可使创建的节点减少到单个虚拟节点，同时提供对文档的随机访问 (<xref:System.Xml.XPath.XPathNavigator>)。</span><span class="sxs-lookup"><span data-stu-id="738eb-125">Cursor style navigation that minimizes node creation to a single virtual node while providing random access to the document (<xref:System.Xml.XPath.XPathNavigator>).</span></span>  
  
     <span data-ttu-id="738eb-126">为了在需要进行 XSLT 处理时都获得更佳性能，您可以使用 <xref:System.Xml.XPath.XPathDocument> 类，这是一个用于 XPath 查询的经过优化的只读存储，旨在高效地与 <xref:System.Xml.Xsl.XslCompiledTransform> 类结合使用。</span><span class="sxs-lookup"><span data-stu-id="738eb-126">For better performance whenever XSLT processing is required, you can use the <xref:System.Xml.XPath.XPathDocument> class, which is an optimized, read-only store for XPath queries designed to work efficiently with the <xref:System.Xml.Xsl.XslCompiledTransform> class.</span></span>  
  
-   <span data-ttu-id="738eb-127">**与 ADO.NET 集成。**</span><span class="sxs-lookup"><span data-stu-id="738eb-127">**Integration with ADO.NET.**</span></span> <span data-ttu-id="738eb-128">XML 类和 [ADO.NET](../../../../docs/framework/data/adonet/index.md) 紧密集成，将关系数据和 XML 组合在一起。</span><span class="sxs-lookup"><span data-stu-id="738eb-128">The XML classes and [ADO.NET](../../../../docs/framework/data/adonet/index.md) are tightly integrated to bring together relational data and XML.</span></span> <span data-ttu-id="738eb-129"><xref:System.Data.DataSet> 类是从数据库中检索到的数据在内存中的缓存。</span><span class="sxs-lookup"><span data-stu-id="738eb-129">The <xref:System.Data.DataSet> class is an in-memory cache of data retrieved from a database.</span></span> <span data-ttu-id="738eb-130"><xref:System.Data.DataSet> 类能够使用 <xref:System.Xml.XmlReader> 和 <xref:System.Xml.XmlWriter> 类读取和写入 XML，以 XML 架构 (XSD) 形式保持其内部关系架构结构，并可以推断 XML 文档的架构结构。</span><span class="sxs-lookup"><span data-stu-id="738eb-130">The <xref:System.Data.DataSet> class has the ability to read and write XML by using the <xref:System.Xml.XmlReader> and <xref:System.Xml.XmlWriter> classes, to persist its internal relational schema structure as XML schemas (XSD), and to infer the schema structure of an XML document.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="738eb-131">本节内容</span><span class="sxs-lookup"><span data-stu-id="738eb-131">In This Section</span></span>  
 [<span data-ttu-id="738eb-132">XML 处理选项</span><span class="sxs-lookup"><span data-stu-id="738eb-132">XML Processing Options</span></span>](../../../../docs/standard/data/xml/xml-processing-options.md)  
 <span data-ttu-id="738eb-133">讨论用于处理 XML 数据的选项。</span><span class="sxs-lookup"><span data-stu-id="738eb-133">Discusses options for processing XML data.</span></span>  
  
 [<span data-ttu-id="738eb-134">内存中 XML 数据处理</span><span class="sxs-lookup"><span data-stu-id="738eb-134">Processing XML Data In-Memory</span></span>](../../../../docs/standard/data/xml/processing-xml-data-in-memory.md)  
 <span data-ttu-id="738eb-135">讨论用于处理内存中 XML 数据的三种模型。</span><span class="sxs-lookup"><span data-stu-id="738eb-135">Discusses the three models for processing XML data in-memory.</span></span> <span data-ttu-id="738eb-136">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)、<xref:System.Xml.XmlDocument> 类（基于 W3C 文档对象模型）和 <xref:System.Xml.XPath.XPathDocument> 类（基于 XPath 数据模型）。</span><span class="sxs-lookup"><span data-stu-id="738eb-136">[LINQ to XML](https://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13), the <xref:System.Xml.XmlDocument> class (based on the W3C Document Object Model), and the <xref:System.Xml.XPath.XPathDocument> class (based on the XPath data model).</span></span>  
  
 [<span data-ttu-id="738eb-137">XSLT 转换</span><span class="sxs-lookup"><span data-stu-id="738eb-137">XSLT Transformations</span></span>](../../../../docs/standard/data/xml/xslt-transformations.md)  
 <span data-ttu-id="738eb-138">描述如何使用 XSLT 处理器。</span><span class="sxs-lookup"><span data-stu-id="738eb-138">Describes how to use the XSLT processor.</span></span>  
  
 [<span data-ttu-id="738eb-139">XML 架构对象模型 (SOM)</span><span class="sxs-lookup"><span data-stu-id="738eb-139">XML Schema Object Model (SOM)</span></span>](../../../../docs/standard/data/xml/xml-schema-object-model-som.md)  
 <span data-ttu-id="738eb-140">描述用于通过提供 <xref:System.Xml.Schema.XmlSchema> 类加载和编辑架构来生成和处理 XML 架构 (XSD) 的类。</span><span class="sxs-lookup"><span data-stu-id="738eb-140">Describes the classes used for building and manipulating XML Schemas (XSD) by providing an <xref:System.Xml.Schema.XmlSchema> class to load and edit a schema.</span></span>  
  
 [<span data-ttu-id="738eb-141">关系数据和 ADO.NET 的 XML 集成</span><span class="sxs-lookup"><span data-stu-id="738eb-141">XML Integration with Relational Data and ADO.NET</span></span>](../../../../docs/standard/data/xml/xml-integration-with-relational-data-and-adonet.md)  
 <span data-ttu-id="738eb-142">描述 .NET Framework 如何通过 <xref:System.Data.DataSet> 对象和 <xref:System.Xml.XmlDataDocument> 对象启用对数据的关系和分层表示形式的实时同步访问。</span><span class="sxs-lookup"><span data-stu-id="738eb-142">Describes how the .NET Framework enables real-time, synchronous access to both the relational and hierarchical representations of data through the <xref:System.Data.DataSet> object and the <xref:System.Xml.XmlDataDocument> object.</span></span>  
  
 [<span data-ttu-id="738eb-143">管理 XML 文档中的命名空间</span><span class="sxs-lookup"><span data-stu-id="738eb-143">Managing Namespaces in an XML Document</span></span>](../../../../docs/standard/data/xml/managing-namespaces-in-an-xml-document.md)  
 <span data-ttu-id="738eb-144">描述 <xref:System.Xml.XmlNamespaceManager> 类如何用于存储和维护命名空间信息。</span><span class="sxs-lookup"><span data-stu-id="738eb-144">Describes how the <xref:System.Xml.XmlNamespaceManager> class is used to store and maintain namespace information.</span></span>  
  
 [<span data-ttu-id="738eb-145">System.Xml 类中的类型支持</span><span class="sxs-lookup"><span data-stu-id="738eb-145">Type Support in the System.Xml Classes</span></span>](../../../../docs/standard/data/xml/type-support-in-the-system-xml-classes.md)  
 <span data-ttu-id="738eb-146">描述如何将 XML 数据类型映射到 CLR 类型，如何转换 XML 类型，并描述 <xref:System.Xml> 类中的其它类型支持功能。</span><span class="sxs-lookup"><span data-stu-id="738eb-146">Describes how XML data types map to CLR types, how to convert XML data types, and other type support features in the <xref:System.Xml> classes.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="738eb-147">相关章节</span><span class="sxs-lookup"><span data-stu-id="738eb-147">Related Sections</span></span>  
 [<span data-ttu-id="738eb-148">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="738eb-148">ADO.NET</span></span>](../../../../docs/framework/data/adonet/index.md)  
 <span data-ttu-id="738eb-149">提供如何使用 ADO.NET 访问数据的信息。</span><span class="sxs-lookup"><span data-stu-id="738eb-149">Provides information on how to access data using ADO.NET.</span></span>  
  
 [<span data-ttu-id="738eb-150">安全性</span><span class="sxs-lookup"><span data-stu-id="738eb-150">Security</span></span>](../../../../docs/standard/security/index.md)  
 <span data-ttu-id="738eb-151">提供对 .NET Framework 安全系统的概述。</span><span class="sxs-lookup"><span data-stu-id="738eb-151">Provides an overview of the .NET Framework security system.</span></span>  
  