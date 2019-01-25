---
title: 序列化 XML 树 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 2c340695-a726-4030-85be-6975d8a149cf
ms.openlocfilehash: 54591438b49005f9016560fcc2f314d6a947d485
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54616753"
---
# <a name="serializing-xml-trees-visual-basic"></a><span data-ttu-id="2da7c-102">序列化 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da7c-102">Serializing XML Trees (Visual Basic)</span></span>
<span data-ttu-id="2da7c-103">序列化 XML 树意味着从 XML 树生成 XML。</span><span class="sxs-lookup"><span data-stu-id="2da7c-103">Serializing an XML tree means generating XML from the XML tree.</span></span> <span data-ttu-id="2da7c-104">可以将 XML 树序列化到文件、<xref:System.IO.TextWriter> 类的具体实现或 <xref:System.Xml.XmlWriter> 的具体实现。</span><span class="sxs-lookup"><span data-stu-id="2da7c-104">You can serialize to a file, to a concrete implementation of the <xref:System.IO.TextWriter> class, or to a concrete implementation of an <xref:System.Xml.XmlWriter>.</span></span>  
  
 <span data-ttu-id="2da7c-105">可以控制序列化的各个方面。</span><span class="sxs-lookup"><span data-stu-id="2da7c-105">You can control various aspects of serialization.</span></span> <span data-ttu-id="2da7c-106">例如，可以控制是否缩进序列化的 XML，以及是否写入 XML 声明。</span><span class="sxs-lookup"><span data-stu-id="2da7c-106">For example, you can control whether to indent the serialized XML, and whether to write an XML declaration.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2da7c-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="2da7c-107">In This Section</span></span>  
  
|<span data-ttu-id="2da7c-108">主题</span><span class="sxs-lookup"><span data-stu-id="2da7c-108">Topic</span></span>|<span data-ttu-id="2da7c-109">描述</span><span class="sxs-lookup"><span data-stu-id="2da7c-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2da7c-110">在序列化时保留空白</span><span class="sxs-lookup"><span data-stu-id="2da7c-110">Preserving White Space While Serializing</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)|<span data-ttu-id="2da7c-111">介绍如何在序列化 XML 树时控制空白行为。</span><span class="sxs-lookup"><span data-stu-id="2da7c-111">Describes how to control white space behavior when you serialize XML trees.</span></span>|  
|[<span data-ttu-id="2da7c-112">带 XML 声明 (Visual Basic 中) 的序列化</span><span class="sxs-lookup"><span data-stu-id="2da7c-112">Serializing with an XML Declaration (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-with-an-xml-declaration.md)|<span data-ttu-id="2da7c-113">介绍如何序列化包含 XML 声明的 XML 树。</span><span class="sxs-lookup"><span data-stu-id="2da7c-113">Describes how to serialize an XML tree that includes an XML declaration.</span></span>|  
|[<span data-ttu-id="2da7c-114">序列化为文件、TextWriter 和 XmlWriter</span><span class="sxs-lookup"><span data-stu-id="2da7c-114">Serializing to Files, TextWriters, and XmlWriters</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-files-textwriters-and-xmlwriters.md)|<span data-ttu-id="2da7c-115">描述如何将文档序列化到 <xref:System.IO.File>、<xref:System.IO.TextWriter> 或 <xref:System.Xml.XmlWriter>。</span><span class="sxs-lookup"><span data-stu-id="2da7c-115">Describes how to serialize a document to a <xref:System.IO.File>, a <xref:System.IO.TextWriter>, or an <xref:System.Xml.XmlWriter>.</span></span>|  
|[<span data-ttu-id="2da7c-116">序列化为 XmlReader (调用 XSLT) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da7c-116">Serializing to an XmlReader (Invoking XSLT) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/serializing-to-an-xmlreader-invoking-xslt.md)|<span data-ttu-id="2da7c-117">描述如何创建一个 <xref:System.Xml.XmlReader>，使另一个模块能够通过它读取 XML 树的内容。</span><span class="sxs-lookup"><span data-stu-id="2da7c-117">Describes how to create a <xref:System.Xml.XmlReader> that enables another module to read the contents of an XML tree.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2da7c-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="2da7c-118">See also</span></span>
- [<span data-ttu-id="2da7c-119">编程指南 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2da7c-119">Programming Guide (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/programming-guide-linq-to-xml.md)
