---
title: "分析 XML (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 3d262fd2177ac77ab5109362f94cc51d03c9563c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="parsing-xml-c"></a><span data-ttu-id="1b189-102">分析 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-102">Parsing XML (C#)</span></span>
<span data-ttu-id="1b189-103">本节中的主题介绍如何分析 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="1b189-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1b189-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="1b189-104">In This Section</span></span>  
  
|<span data-ttu-id="1b189-105">主题</span><span class="sxs-lookup"><span data-stu-id="1b189-105">Topic</span></span>|<span data-ttu-id="1b189-106">描述</span><span class="sxs-lookup"><span data-stu-id="1b189-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="1b189-107">如何：分析字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="1b189-108">演示如何分析字符串从而创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="1b189-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="1b189-109">如何：从文件加载 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="1b189-110">演示如何使用 <xref:System.Xml.Linq.XElement.Load%2A> 方法从 URI 加载 XML。</span><span class="sxs-lookup"><span data-stu-id="1b189-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="1b189-111">在加载或分析 XML 时保留空白</span><span class="sxs-lookup"><span data-stu-id="1b189-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="1b189-112">介绍如何在加载 XML 树时控制 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的空白行为。</span><span class="sxs-lookup"><span data-stu-id="1b189-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="1b189-113">如何：捕捉分析错误 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="1b189-114">演示如何检测格式不正确或无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="1b189-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="1b189-115">如何：从 XmlReader 创建树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="1b189-116">演示如何从 <xref:System.Xml.XmlReader> 直接创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="1b189-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="1b189-117">如何：从 XmlReader 流式处理 XML 片段 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="1b189-118">演示如何使用 <xref:System.Xml.XmlReader> 对 XML 片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="1b189-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="1b189-119">如果必须处理很大的 XML 文件，将整个 XML 树加载到内存可能不可行。</span><span class="sxs-lookup"><span data-stu-id="1b189-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="1b189-120">这时，可以对 XML 片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="1b189-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b189-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="1b189-121">See Also</span></span>  
 [<span data-ttu-id="1b189-122">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="1b189-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)
