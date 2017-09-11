---
title: "分析 XML (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 5bcbd7e2-d9f1-4c8f-80d6-39915fe17bd1
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
ms.openlocfilehash: af4ecce89f2f45069a48ce62826509f795dcf211
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="parsing-xml-visual-basic"></a><span data-ttu-id="d45b2-102">分析 XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45b2-102">Parsing XML (Visual Basic)</span></span>
<span data-ttu-id="d45b2-103">本节中的主题介绍如何分析 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="d45b2-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d45b2-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="d45b2-104">In This Section</span></span>  
  
|<span data-ttu-id="d45b2-105">主题</span><span class="sxs-lookup"><span data-stu-id="d45b2-105">Topic</span></span>|<span data-ttu-id="d45b2-106">说明</span><span class="sxs-lookup"><span data-stu-id="d45b2-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="d45b2-107">如何︰ 分析字符串 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45b2-107">How to: Parse a String (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="d45b2-108">演示如何分析字符串从而创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="d45b2-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="d45b2-109">如何︰ 从文件 (Visual Basic 中) 加载 XML</span><span class="sxs-lookup"><span data-stu-id="d45b2-109">How to: Load XML from a File (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="d45b2-110">演示如何从 URI 使用加载 XML<xref:System.Xml.Linq.XElement.Load%2A>方法。</xref:System.Xml.Linq.XElement.Load%2A></span><span class="sxs-lookup"><span data-stu-id="d45b2-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="d45b2-111">在加载或分析 XML 时保留空白</span><span class="sxs-lookup"><span data-stu-id="d45b2-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../visual-basic/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml.md)|<span data-ttu-id="d45b2-112">介绍如何在加载 XML 树时控制 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 的空白行为。</span><span class="sxs-lookup"><span data-stu-id="d45b2-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="d45b2-113">如何︰ 捕捉分析错误 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45b2-113">How to: Catch Parsing Errors (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="d45b2-114">演示如何检测格式不正确或无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="d45b2-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="d45b2-115">如何︰ 从 XmlReader (Visual Basic 中) 创建树</span><span class="sxs-lookup"><span data-stu-id="d45b2-115">How to: Create a Tree from an XmlReader (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="d45b2-116">演示如何直接从<xref:System.Xml.XmlReader>。</xref:System.Xml.XmlReader>创建 XML 树</span><span class="sxs-lookup"><span data-stu-id="d45b2-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="d45b2-117">如何︰ 从 XmlReader (Visual Basic 中) 的 XML 片段进行流式处理</span><span class="sxs-lookup"><span data-stu-id="d45b2-117">How to: Stream XML Fragments from an XmlReader (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="d45b2-118">演示如何通过使用<xref:System.Xml.XmlReader>。</xref:System.Xml.XmlReader>流式处理 XML 片段</span><span class="sxs-lookup"><span data-stu-id="d45b2-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="d45b2-119">如果必须处理很大的 XML 文件，将整个 XML 树加载到内存可能不可行。</span><span class="sxs-lookup"><span data-stu-id="d45b2-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="d45b2-120">这时，可以对 XML 片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="d45b2-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d45b2-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d45b2-121">See Also</span></span>  
 [<span data-ttu-id="d45b2-122">创建 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d45b2-122">Creating XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/creating-xml-trees.md)
