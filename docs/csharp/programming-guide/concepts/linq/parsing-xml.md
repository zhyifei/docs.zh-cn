---
title: "分析 XML (C#)"
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
ms.assetid: 7ea83f83-a779-423a-9875-4ea4e51f97fc
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
ms.openlocfilehash: 13807e57b3616d51bd88b37d0acc703a18445a02
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="parsing-xml-c"></a><span data-ttu-id="208ec-102">分析 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-102">Parsing XML (C#)</span></span>
<span data-ttu-id="208ec-103">本节中的主题介绍如何分析 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="208ec-103">The topics in this section describe how to parse XML documents.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="208ec-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="208ec-104">In This Section</span></span>  
  
|<span data-ttu-id="208ec-105">主题</span><span class="sxs-lookup"><span data-stu-id="208ec-105">Topic</span></span>|<span data-ttu-id="208ec-106">描述</span><span class="sxs-lookup"><span data-stu-id="208ec-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="208ec-107">如何：分析字符串 (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-107">How to: Parse a String (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-parse-a-string.md)|<span data-ttu-id="208ec-108">演示如何分析字符串从而创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="208ec-108">Shows how to parse a string to create an XML tree.</span></span>|  
|[<span data-ttu-id="208ec-109">如何：从文件加载 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-109">How to: Load XML from a File (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-load-xml-from-a-file.md)|<span data-ttu-id="208ec-110">演示如何使用 <xref:System.Xml.Linq.XElement.Load%2A> 方法从 URI 加载 XML。</span><span class="sxs-lookup"><span data-stu-id="208ec-110">Shows how to load XML from a URI using the <xref:System.Xml.Linq.XElement.Load%2A> method.</span></span>|  
|[<span data-ttu-id="208ec-111">在加载或分析 XML 时保留空白</span><span class="sxs-lookup"><span data-stu-id="208ec-111">Preserving White Space while Loading or Parsing XML</span></span>](../../../../csharp/programming-guide/concepts/linq/preserving-white-space-while-loading-or-parsing-xml1.md)|<span data-ttu-id="208ec-112">介绍如何在加载 XML 树时控制 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 的空白行为。</span><span class="sxs-lookup"><span data-stu-id="208ec-112">Describes how to control the white space behavior of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] while loading XML trees.</span></span>|  
|[<span data-ttu-id="208ec-113">如何：捕捉分析错误 (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-113">How to: Catch Parsing Errors (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-catch-parsing-errors.md)|<span data-ttu-id="208ec-114">演示如何检测格式不正确或无效的 XML。</span><span class="sxs-lookup"><span data-stu-id="208ec-114">Shows how to detect badly formed or invalid XML.</span></span>|  
|[<span data-ttu-id="208ec-115">如何：从 XmlReader 创建树 (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-115">How to: Create a Tree from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-create-a-tree-from-an-xmlreader.md)|<span data-ttu-id="208ec-116">演示如何从 <xref:System.Xml.XmlReader> 直接创建 XML 树。</span><span class="sxs-lookup"><span data-stu-id="208ec-116">Shows how to create an XML tree directly from an <xref:System.Xml.XmlReader>.</span></span>|  
|[<span data-ttu-id="208ec-117">如何：从 XmlReader 流式处理 XML 片段 (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-117">How to: Stream XML Fragments from an XmlReader (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-stream-xml-fragments-from-an-xmlreader.md)|<span data-ttu-id="208ec-118">演示如何使用 <xref:System.Xml.XmlReader> 对 XML 片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="208ec-118">Shows how to stream XML fragments by using an <xref:System.Xml.XmlReader>.</span></span><br /><br /> <span data-ttu-id="208ec-119">如果必须处理很大的 XML 文件，将整个 XML 树加载到内存可能不可行。</span><span class="sxs-lookup"><span data-stu-id="208ec-119">When you have to process arbitrarily large XML files, it might not be feasible to load the whole XML tree into memory.</span></span> <span data-ttu-id="208ec-120">这时，可以对 XML 片段进行流式处理。</span><span class="sxs-lookup"><span data-stu-id="208ec-120">Instead, you can stream XML fragments.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="208ec-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="208ec-121">See Also</span></span>  
 [<span data-ttu-id="208ec-122">创建 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="208ec-122">Creating XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees.md)

