---
title: "序列化 XML 树 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: b3937e54-4ce9-4236-ac96-14e7972aa594
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: f3b8ee68065a056cccbf02d96bf5f21e7ccea16b
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="serializing-xml-trees-c"></a><span data-ttu-id="5e4c0-102">序列化 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="5e4c0-102">Serializing XML Trees (C#)</span></span>
<span data-ttu-id="5e4c0-103">序列化 XML 树意味着从 XML 树生成 XML。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="5e4c0-104">可以将 XML 树序列化到文件、<xref:System.IO.TextWriter> 类的具体实现或 <xref:System.Xml.XmlWriter> 的具体实现。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="5e4c0-105">可以控制序列化的各个方面。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="5e4c0-106">例如，可以控制是否缩进序列化的 XML，以及是否写入 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5e4c0-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="5e4c0-107">In This Section</span></span>  
  
|<span data-ttu-id="5e4c0-108">主题</span><span class="sxs-lookup"><span data-stu-id="5e4c0-108">Topic</span></span>|<span data-ttu-id="5e4c0-109">描述</span><span class="sxs-lookup"><span data-stu-id="5e4c0-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5e4c0-110">在序列化时保留空白</span><span class="sxs-lookup"><span data-stu-id="5e4c0-110">Preserving White Space While Serializing</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="5e4c0-111">介绍如何在序列化 XML 树时控制空白行为。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="5e4c0-112">带 XML 声明的序列化 (C#)</span><span class="sxs-lookup"><span data-stu-id="5e4c0-112">Serializing with an XML Declaration (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="5e4c0-113">介绍如何序列化包含 XML 声明的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="5e4c0-114">序列化为文件、TextWriter 和 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="5e4c0-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="5e4c0-115">描述如何将文档序列化到 <xref:System.IO.File>、<xref:System.IO.TextWriter> 或 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="5e4c0-116">序列化为 XmlReader（调用 XSLT）(C#)</span><span class="sxs-lookup"><span data-stu-id="5e4c0-116">Serializing to an XmlReader (Invoking XSLT) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="5e4c0-117">描述如何创建一个 <xref:System.Xml.XmlReader>，使另一个模块能够通过它读取 XML 树的内容。</span><span class="sxs-lookup"><span data-stu-id="5e4c0-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5e4c0-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5e4c0-118">See Also</span></span>  
 [<span data-ttu-id="5e4c0-119">编程指南 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5e4c0-119">Programming Guide (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)

