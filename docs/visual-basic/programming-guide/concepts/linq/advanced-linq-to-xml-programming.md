---
title: "高级 LINQ to XML 编程 (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 36018532-a55c-4538-8a27-98f475ea3415
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 9c4add52a2c195593fd44abf3728bde68fe8d4e1
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="advanced-linq-to-xml-programming-visual-basic"></a><span data-ttu-id="8f783-102">高级的 LINQ to XML 编程 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-102">Advanced LINQ to XML Programming (Visual Basic)</span></span>
<span data-ttu-id="8f783-103">本节为高级开发人员提供一些只适用于某些 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 方案的信息。</span><span class="sxs-lookup"><span data-stu-id="8f783-103">This section provides information that will only be applicable to advanced developers in certain [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] scenarios.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="8f783-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="8f783-104">In This Section</span></span>  
  
|<span data-ttu-id="8f783-105">主题</span><span class="sxs-lookup"><span data-stu-id="8f783-105">Topic</span></span>|<span data-ttu-id="8f783-106">描述</span><span class="sxs-lookup"><span data-stu-id="8f783-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="8f783-107">LINQ to XML 批注</span><span class="sxs-lookup"><span data-stu-id="8f783-107">LINQ to XML Annotations</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-annotations.md)|<span data-ttu-id="8f783-108">介绍如何将批注添加到 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 节点和属性。</span><span class="sxs-lookup"><span data-stu-id="8f783-108">Describes how to add annotations to [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] nodes and attributes.</span></span>|  
|[<span data-ttu-id="8f783-109">LINQ to XML 事件 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-109">LINQ to XML Events (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml-events.md)|<span data-ttu-id="8f783-110">介绍如何为更改 XML 树时所发生的事件编写事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="8f783-110">Describes how to write event handlers for events that occur when you alter an XML tree.</span></span>|  
|[<span data-ttu-id="8f783-111">使用节点 (Visual Basic 中) 进行编程</span><span class="sxs-lookup"><span data-stu-id="8f783-111">Programming with Nodes (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-with-nodes.md)|<span data-ttu-id="8f783-112">介绍如何在比元素和属性更精细的粒度级别上查询和操作节点。</span><span class="sxs-lookup"><span data-stu-id="8f783-112">Describes how to query and manipulate nodes at a finer level of granularity than elements and attributes.</span></span>|  
|[<span data-ttu-id="8f783-113">混合声明性代码/强制性代码 Bug (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-113">Mixed Declarative Code/Imperative Code Bugs (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/mixed-declarative-code-imperative-code-bugs-linq-to-xml.md)|<span data-ttu-id="8f783-114">介绍在混合声明性代码（查询）与命令性代码（修改 XML 树的代码）时所出现的问题。</span><span class="sxs-lookup"><span data-stu-id="8f783-114">Describes the problems that appear when you mix declarative code (queries) with imperative code (code that modifies the XML tree).</span></span>|  
|[<span data-ttu-id="8f783-115">如何︰ 访问标头信息 (Visual Basic 中) 的 XML 片段进行流式处理</span><span class="sxs-lookup"><span data-stu-id="8f783-115">How to: Stream XML Fragments with Access to Header Information (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-with-access-to-header-information.md)|<span data-ttu-id="8f783-116">介绍如何从<xref:System.Xml.XmlReader>。</xref:System.Xml.XmlReader> XML 片段进行流式处理</span><span class="sxs-lookup"><span data-stu-id="8f783-116">Describes how to stream XML fragments from an <xref:System.Xml.XmlReader>.</span></span> <span data-ttu-id="8f783-117">使用此技术，可以控制应用程序的内存需求量。</span><span class="sxs-lookup"><span data-stu-id="8f783-117">You can use this technique to control the memory footprint of your application.</span></span>|  
|[<span data-ttu-id="8f783-118">如何︰ 执行大型 XML 文档 (Visual Basic 中) 的流式转换</span><span class="sxs-lookup"><span data-stu-id="8f783-118">How to: Perform Streaming Transform of Large XML Documents (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-perform-streaming-transform-of-large-xml-documents.md)|<span data-ttu-id="8f783-119">描述如何从<xref:System.Xml.XmlReader>、 转换 XML 片段中，和流式处理使用<xref:System.Xml.Linq.XStreamingElement>。</xref:System.Xml.Linq.XStreamingElement>的输出</xref:System.Xml.XmlReader>流 XML</span><span class="sxs-lookup"><span data-stu-id="8f783-119">Describes how to stream XML from an <xref:System.Xml.XmlReader>, transform the XML fragment, and stream the output using <xref:System.Xml.Linq.XStreamingElement>.</span></span>|  
|[<span data-ttu-id="8f783-120">如何︰ 读取和写入编码的文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-120">How to: Read and Write an Encoded Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-read-and-write-an-encoded-document.md)|<span data-ttu-id="8f783-121">介绍如何读取和写入经过编码的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="8f783-121">Describes how to read and write XML documents that are encoded.</span></span>|  
|[<span data-ttu-id="8f783-122">使用 XSLT 转换 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-122">Using XSLT to Transform an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/using-xslt-to-transform-an-xml-tree.md)|<span data-ttu-id="8f783-123">介绍如何使用 XSLT 转换 XML 树。</span><span class="sxs-lookup"><span data-stu-id="8f783-123">Describes how to transform an XML tree using XSLT.</span></span>|  
|[<span data-ttu-id="8f783-124">如何︰ 使用批注来转换 LINQ to XML 树的 XSLT 样式 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-124">How to: Use Annotations to Transform LINQ to XML Trees in an XSLT Style (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-use-annotation-trees-to-transform-linq-to-xml-trees-in-an-xslt-style.md)|<span data-ttu-id="8f783-125">介绍如何使用批注来帮助进行 XML 树的转换。</span><span class="sxs-lookup"><span data-stu-id="8f783-125">Describes how annotations can be used to facilitate transforms of an XML tree.</span></span>|  
|[<span data-ttu-id="8f783-126">序列化包含 XElement 对象 (Visual Basic 中) 的对象图</span><span class="sxs-lookup"><span data-stu-id="8f783-126">Serializing Object Graphs that Contain XElement Objects (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-object-graphs-that-contain-xelement-objects.md)|<span data-ttu-id="8f783-127">介绍如何序列化对象图包含<xref:System.Xml.Linq.XElement>和<xref:System.Xml.Linq.XDocument>对象。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="8f783-127">Describes how to serialize object graphs that contain <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> objects.</span></span>|  
|[<span data-ttu-id="8f783-128">使用 LINQ to XML 进行 WPF 数据绑定</span><span class="sxs-lookup"><span data-stu-id="8f783-128">WPF Data Binding with LINQ to XML</span></span>](https://docs.microsoft.com/visualstudio/designers/wpf-data-binding-with-linq-to-xml)|<span data-ttu-id="8f783-129">介绍如何将 LINQ to XML 用作 Windows Presentation Foundation 应用程序中数据绑定的数据源。</span><span class="sxs-lookup"><span data-stu-id="8f783-129">Describes how to use LINQ to XML as the data source for data binding in Windows Presentation Foundation applications.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="8f783-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8f783-130">See Also</span></span>  
 [<span data-ttu-id="8f783-131">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8f783-131">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
