---
title: 使用 DOM 模型处理 XML 数据
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 56b6e9c7-ed82-4a65-a647-7be32c83bcc8
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c59d84148aae35794410f5f7237cef96ab5b7560
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33570340"
---
# <a name="process-xml-data-using-the-dom-model"></a><span data-ttu-id="1c544-102">使用 DOM 模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="1c544-102">Process XML Data Using the DOM Model</span></span>
<span data-ttu-id="1c544-103">XML 文档对象模型 (DOM) 将 XML 数据作为一组标准的对象对待，用于处理内存中的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="1c544-103">The XML Document Object Model (DOM) treats XML data as a standard set of objects and is used to process XML data in memory.</span></span> <span data-ttu-id="1c544-104">`System.Xml` 命名空间提供 XML 文档、片断、节点或节点集的编程表示形式。</span><span class="sxs-lookup"><span data-stu-id="1c544-104">The `System.Xml` namespace provides a programmatic representation of XML documents, fragments, nodes, or node-sets.</span></span> <span data-ttu-id="1c544-105">基于万维网联合会 (W3C) DOM 级别 1 核心和 DOM 级别 2 核心建议。</span><span class="sxs-lookup"><span data-stu-id="1c544-105">It is based on the World Wide Web Consortium (W3C) DOM Level 1 Core and the DOM Level 2 Core recommendations.</span></span>  
  
 <span data-ttu-id="1c544-106"><xref:System.Xml.XmlDocument> 类表示 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="1c544-106">The <xref:System.Xml.XmlDocument> class represents an XML document.</span></span> <span data-ttu-id="1c544-107">包括用于检索和创建所有其他 XML 对象的成员。</span><span class="sxs-lookup"><span data-stu-id="1c544-107">It includes members for retrieving and creating all other XML objects.</span></span> <span data-ttu-id="1c544-108">使用 <xref:System.Xml.XmlDocument> 及其相关的类，可以构造 XML 文档、加载和访问数据、修改数据以及保存更改。</span><span class="sxs-lookup"><span data-stu-id="1c544-108">Using the <xref:System.Xml.XmlDocument>, and its related classes, you can construct XML documents, load and access data, modify data, and save changes.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1c544-109">本节内容</span><span class="sxs-lookup"><span data-stu-id="1c544-109">In This Section</span></span>  
  
-   [<span data-ttu-id="1c544-110">XML 文档对象模型 (DOM)</span><span class="sxs-lookup"><span data-stu-id="1c544-110">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)  
  
-   [<span data-ttu-id="1c544-111">XML 节点类型</span><span class="sxs-lookup"><span data-stu-id="1c544-111">Types of XML Nodes</span></span>](../../../../docs/standard/data/xml/types-of-xml-nodes.md)  
  
-   [<span data-ttu-id="1c544-112">XML 文档对象模型 (DOM) 层次结构</span><span class="sxs-lookup"><span data-stu-id="1c544-112">XML Document Object Model (DOM) Hierarchy</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom-hierarchy.md)  
  
-   [<span data-ttu-id="1c544-113">将对象层次结构映射到 XML 数据</span><span class="sxs-lookup"><span data-stu-id="1c544-113">Mapping the Object Hierarchy to XML Data</span></span>](../../../../docs/standard/data/xml/mapping-the-object-hierarchy-to-xml-data.md)  
  
-   [<span data-ttu-id="1c544-114">创建 XML 文档</span><span class="sxs-lookup"><span data-stu-id="1c544-114">XML Document Creation</span></span>](../../../../docs/standard/data/xml/xml-document-creation.md)  
  
-   [<span data-ttu-id="1c544-115">将 XML 文档读入 DOM</span><span class="sxs-lookup"><span data-stu-id="1c544-115">Reading an XML Document into the DOM</span></span>](../../../../docs/standard/data/xml/reading-an-xml-document-into-the-dom.md)  
  
-   [<span data-ttu-id="1c544-116">将节点插入 XML 文档中</span><span class="sxs-lookup"><span data-stu-id="1c544-116">Inserting Nodes into an XML Document</span></span>](../../../../docs/standard/data/xml/inserting-nodes-into-an-xml-document.md)  
  
-   [<span data-ttu-id="1c544-117">从 XML 删除文档中的节点、内容和值</span><span class="sxs-lookup"><span data-stu-id="1c544-117">Removing Nodes, Content, and Values from an XML Document</span></span>](../../../../docs/standard/data/xml/removing-nodes-content-and-values-from-an-xml-document.md)  
  
-   [<span data-ttu-id="1c544-118">修改 XML 文档中的节点、内容和值</span><span class="sxs-lookup"><span data-stu-id="1c544-118">Modifying Nodes, Content, and Values in an XML Document</span></span>](../../../../docs/standard/data/xml/modifying-nodes-content-and-values-in-an-xml-document.md)  
  
-   [<span data-ttu-id="1c544-119">在 DOM 中验证 XML 文档</span><span class="sxs-lookup"><span data-stu-id="1c544-119">Validating an XML Document in the DOM</span></span>](../../../../docs/standard/data/xml/validating-an-xml-document-in-the-dom.md)  
  
-   [<span data-ttu-id="1c544-120">保存和编写文档</span><span class="sxs-lookup"><span data-stu-id="1c544-120">Saving and Writing a Document</span></span>](../../../../docs/standard/data/xml/saving-and-writing-a-document.md)  
  
-   [<span data-ttu-id="1c544-121">使用 XPath 导航选择节点</span><span class="sxs-lookup"><span data-stu-id="1c544-121">Select Nodes Using XPath Navigation</span></span>](../../../../docs/standard/data/xml/select-nodes-using-xpath-navigation.md)  
  
-   [<span data-ttu-id="1c544-122">解析外部资源</span><span class="sxs-lookup"><span data-stu-id="1c544-122">Resolving External Resources</span></span>](../../../../docs/standard/data/xml/resolving-external-resources.md)  
  
-   [<span data-ttu-id="1c544-123">使用 XmlNameTable 的对象比较</span><span class="sxs-lookup"><span data-stu-id="1c544-123">Object Comparison Using XmlNameTable</span></span>](../../../../docs/standard/data/xml/object-comparison-using-xmlnametable.md)  
  
-   [<span data-ttu-id="1c544-124">NamedNodeMap 和 NodeList 中的节点集合</span><span class="sxs-lookup"><span data-stu-id="1c544-124">Node Collections in NamedNodeMaps and NodeLists</span></span>](../../../../docs/standard/data/xml/node-collections-in-namednodemaps-and-nodelists.md)  
  
-   [<span data-ttu-id="1c544-125">NodeList 和 NamedNodeMap 的动态更新</span><span class="sxs-lookup"><span data-stu-id="1c544-125">Dynamic Updates to NodeLists and NamedNodeMaps</span></span>](../../../../docs/standard/data/xml/dynamic-updates-to-nodelists-and-namednodemaps.md)  
  
-   [<span data-ttu-id="1c544-126">DOM 中的命名空间支持</span><span class="sxs-lookup"><span data-stu-id="1c544-126">Namespace Support in the DOM</span></span>](../../../../docs/standard/data/xml/namespace-support-in-the-dom.md)  
  
-   [<span data-ttu-id="1c544-127">使用 XmlNodeChangedEventArgs 的 XML 文档中的事件处理</span><span class="sxs-lookup"><span data-stu-id="1c544-127">Event Handling in an XML Document Using the XmlNodeChangedEventArgs</span></span>](../../../../docs/standard/data/xml/event-handling-in-an-xml-document-using-the-xmlnodechangedeventargs.md)  
  
-   [<span data-ttu-id="1c544-128">扩展 DOM</span><span class="sxs-lookup"><span data-stu-id="1c544-128">Extending the DOM</span></span>](../../../../docs/standard/data/xml/extending-the-dom.md)  
  
## <a name="related-sections"></a><span data-ttu-id="1c544-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="1c544-129">Related Sections</span></span>  
 [<span data-ttu-id="1c544-130">使用 XPath 数据模型处理 XML 数据</span><span class="sxs-lookup"><span data-stu-id="1c544-130">Process XML Data Using the XPath Data Model</span></span>](../../../../docs/standard/data/xml/process-xml-data-using-the-xpath-data-model.md)  
 <span data-ttu-id="1c544-131">讨论如何使用 <xref:System.Xml.XPath.XPathNavigator> 类进行 XML 处理。</span><span class="sxs-lookup"><span data-stu-id="1c544-131">Discusses XML processing using the <xref:System.Xml.XPath.XPathNavigator> class.</span></span>
