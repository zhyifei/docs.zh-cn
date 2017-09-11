---
title: "加载或分析 XML2 时保留空白 |Microsoft 文档"
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
ms.assetid: ef6518e0-2c8d-462c-8b92-a16e9dc737ad
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: a2872c1e2354c0a0bd106f7fb945542ce37e7774
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="preserving-white-space-while-loading-or-parsing-xml"></a><span data-ttu-id="db277-102">在加载或分析 XML 时保留空白</span><span class="sxs-lookup"><span data-stu-id="db277-102">Preserving White Space while Loading or Parsing XML</span></span>
<span data-ttu-id="db277-103">本主题说明如何控制 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 的空白行为。</span><span class="sxs-lookup"><span data-stu-id="db277-103">This topic describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="db277-104">一种常用情况是读取缩进的 XML，在内存中创建一个没有任何空白文本节点（即不保留空白）的 XML 树，对该 XML 执行某些操作，然后保存带缩进的 XML。</span><span class="sxs-lookup"><span data-stu-id="db277-104">A common scenario is to read indented XML, create an in-memory XML tree without any white space text nodes (that is, not preserving white space), perform some operations on the XML, and then save the XML with indentation.</span></span> <span data-ttu-id="db277-105">在序列化带格式的 XML 时，只保留 XML 树中有意义的空白。</span><span class="sxs-lookup"><span data-stu-id="db277-105">When you serialize the XML with formatting, only significant white space in the XML tree is preserved.</span></span> <span data-ttu-id="db277-106">这是 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 的默认行为。</span><span class="sxs-lookup"><span data-stu-id="db277-106">This is the default behavior for [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)].</span></span>  
  
 <span data-ttu-id="db277-107">另一个常见的情况是读取和修改已经有意缩进的 XML。</span><span class="sxs-lookup"><span data-stu-id="db277-107">Another common scenario is to read and modify XML that has already been intentionally indented.</span></span> <span data-ttu-id="db277-108">您可能不想以任何方式更改这种缩进。</span><span class="sxs-lookup"><span data-stu-id="db277-108">You might not want to change this indentation in any way.</span></span> <span data-ttu-id="db277-109">若要在 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 中执行此操作，您要在加载或解析 XML 时保留空白，并在序列化 XML 时禁用格式设置。</span><span class="sxs-lookup"><span data-stu-id="db277-109">To do this in [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)], you preserve white space when you load or parse the XML and disable formatting when you serialize the XML.</span></span>  
  
 <span data-ttu-id="db277-110">本主题说明用于填充 XML 树的方法的空白行为。</span><span class="sxs-lookup"><span data-stu-id="db277-110">This topic describes the white space behavior of methods that populate XML trees.</span></span> <span data-ttu-id="db277-111">有关序列化 XML 树时控制空白区域的信息，请参阅[保留空白时序列化](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md)。</span><span class="sxs-lookup"><span data-stu-id="db277-111">For information about controlling white space when you serialize XML trees, see [Preserving White Space While Serializing](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-serializing.md).</span></span>  
  
## <a name="behavior-of-methods-that-populate-xml-trees"></a><span data-ttu-id="db277-112">用于填充 XML 树的方法的行为</span><span class="sxs-lookup"><span data-stu-id="db277-112">Behavior of Methods that Populate XML Trees</span></span>  
 <span data-ttu-id="db277-113">中的以下方法<xref:System.Xml.Linq.XElement>和<xref:System.Xml.Linq.XDocument>类填充 XML 树。</xref:System.Xml.Linq.XDocument> </xref:System.Xml.Linq.XElement></span><span class="sxs-lookup"><span data-stu-id="db277-113">The following methods in the <xref:System.Xml.Linq.XElement> and <xref:System.Xml.Linq.XDocument> classes populate an XML tree.</span></span> <span data-ttu-id="db277-114">您可以填充 XML 树从一个文件， <xref:System.IO.TextReader>、 <xref:System.Xml.XmlReader>，或一个字符串︰</xref:System.Xml.XmlReader> </xref:System.IO.TextReader></span><span class="sxs-lookup"><span data-stu-id="db277-114">You can populate an XML tree from a file, a <xref:System.IO.TextReader>, an <xref:System.Xml.XmlReader>, or a string:</span></span>  
  
-   <span data-ttu-id="db277-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="db277-115"><xref:System.Xml.Linq.XElement.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="db277-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="db277-116"><xref:System.Xml.Linq.XElement.Parse%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="db277-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="db277-117"><xref:System.Xml.Linq.XDocument.Load%2A?displayProperty=fullName></span></span>  
  
-   <span data-ttu-id="db277-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="db277-118"><xref:System.Xml.Linq.XDocument.Parse%2A?displayProperty=fullName></span></span>  
  
 <span data-ttu-id="db277-119">如果该方法不采用<xref:System.Xml.Linq.LoadOptions>作为参数，该方法将不保留无关紧要的空白区域。</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="db277-119">If the method does not take <xref:System.Xml.Linq.LoadOptions> as an argument, the method will not preserve insignificant white space.</span></span>  
  
 <span data-ttu-id="db277-120">在大多数情况下，如果该方法采用<xref:System.Xml.Linq.LoadOptions>作为参数，您可以选择保留无意义的空白作为 XML 树中的文本节点。</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="db277-120">In most cases, if the method takes <xref:System.Xml.Linq.LoadOptions> as an argument, you can optionally preserve insignificant white space as text nodes in the XML tree.</span></span> <span data-ttu-id="db277-121">但是，如果该方法从 XML 加载<xref:System.Xml.XmlReader>，则<xref:System.Xml.XmlReader>确定是否保留空白区域。</xref:System.Xml.XmlReader> </xref:System.Xml.XmlReader></span><span class="sxs-lookup"><span data-stu-id="db277-121">However, if the method is loading the XML from an <xref:System.Xml.XmlReader>, then the <xref:System.Xml.XmlReader> determines whether white space will be preserved or not.</span></span> <span data-ttu-id="db277-122">设置<xref:System.Xml.Linq.LoadOptions>不起作用。</xref:System.Xml.Linq.LoadOptions></span><span class="sxs-lookup"><span data-stu-id="db277-122">Setting <xref:System.Xml.Linq.LoadOptions> will have no effect.</span></span>  
  
 <span data-ttu-id="db277-123">使用这些方法，如果保留空白，无关紧要的空白区域插入到 XML 树中作为<xref:System.Xml.Linq.XText>节点。</xref:System.Xml.Linq.XText></span><span class="sxs-lookup"><span data-stu-id="db277-123">With these methods, if white space is preserved, insignificant white space is inserted into the XML tree as <xref:System.Xml.Linq.XText> nodes.</span></span> <span data-ttu-id="db277-124">如果不保留空白，则不会插入文本节点。</span><span class="sxs-lookup"><span data-stu-id="db277-124">If white space is not preserved, text nodes are not inserted.</span></span>  
  
 <span data-ttu-id="db277-125">可以通过使用<xref:System.Xml.XmlWriter>。</xref:System.Xml.XmlWriter>创建 XML 树</span><span class="sxs-lookup"><span data-stu-id="db277-125">You can create an XML tree by using an <xref:System.Xml.XmlWriter>.</span></span> <span data-ttu-id="db277-126">写入到的节点<xref:System.Xml.XmlWriter>在树中填充。</xref:System.Xml.XmlWriter></span><span class="sxs-lookup"><span data-stu-id="db277-126">Nodes that are written to the <xref:System.Xml.XmlWriter> are populated in the tree.</span></span> <span data-ttu-id="db277-127">但在使用此方法生成 XML 树时，不管节点是否为空白或是否为无意义的空白，都将保留所有节点。</span><span class="sxs-lookup"><span data-stu-id="db277-127">However, when you build an XML tree using this method, all nodes are preserved, regardless of whether the node is white space or not, or whether the white space is significant or not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db277-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db277-128">See Also</span></span>  
 [<span data-ttu-id="db277-129">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="db277-129">Parsing XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/parsing-xml.md)
