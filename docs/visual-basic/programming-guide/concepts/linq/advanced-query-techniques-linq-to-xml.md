---
title: "高级查询技术 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 79be877c-fadc-4dfb-9f03-426082b13656
caps.latest.revision: 4
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 6983fa5b9637210bb3c56e8f693eb4f956dab0a8
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="advanced-query-techniques-linq-to-xml-visual-basic"></a><span data-ttu-id="2695c-102">高级查询技术 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-102">Advanced Query Techniques (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="2695c-103">本节提供更多高级 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询技术的示例。</span><span class="sxs-lookup"><span data-stu-id="2695c-103">This section provides examples of more advanced [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query techniques.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="2695c-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="2695c-104">In This Section</span></span>  
  
|<span data-ttu-id="2695c-105">主题</span><span class="sxs-lookup"><span data-stu-id="2695c-105">Topic</span></span>|<span data-ttu-id="2695c-106">说明</span><span class="sxs-lookup"><span data-stu-id="2695c-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="2695c-107">如何︰ 联接两个集合 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-107">How to: Join Two Collections (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-two-collections-linq-to-xml.md)|<span data-ttu-id="2695c-108">演示如何使用 `Join` 子句来利用 XML 数据中的关系。</span><span class="sxs-lookup"><span data-stu-id="2695c-108">Shows how to use the `Join` clause to take advantage of relationships in XML data.</span></span>|  
|[<span data-ttu-id="2695c-109">如何︰ 使用分组 (Visual Basic 中) 创建层次结构</span><span class="sxs-lookup"><span data-stu-id="2695c-109">How to: Create Hierarchy Using Grouping (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-hierarchy-using-grouping.md)|<span data-ttu-id="2695c-110">演示如何将数据分组，再基于分组生成 XML。</span><span class="sxs-lookup"><span data-stu-id="2695c-110">Shows how to group data, and then generate XML based on the grouping.</span></span>|  
|[<span data-ttu-id="2695c-111">如何︰ 查询 LINQ to XML 使用 XPath (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-111">How to: Query LINQ to XML Using XPath (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-linq-to-xml-using-xpath.md)|<span data-ttu-id="2695c-112">演示如何基于 XPath 查询来检索集合。</span><span class="sxs-lookup"><span data-stu-id="2695c-112">Shows how to retrieve collections based on XPath queries.</span></span>|  
|[<span data-ttu-id="2695c-113">如何︰ 编写 LINQ to XML 轴方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-113">How to: Write a LINQ to XML Axis Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-linq-to-xml-axis-method.md)|<span data-ttu-id="2695c-114">演示如何编写 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 轴方法。</span><span class="sxs-lookup"><span data-stu-id="2695c-114">Shows how to write a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] axis method.</span></span>|  
|[<span data-ttu-id="2695c-115">如何︰ 列出树 (Visual Basic 中) 中的所有节点</span><span class="sxs-lookup"><span data-stu-id="2695c-115">How to: List All Nodes in a Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-list-all-nodes-in-a-tree.md)|<span data-ttu-id="2695c-116">演示一种用于列出 XML 树中所有节点的实用工具方法。</span><span class="sxs-lookup"><span data-stu-id="2695c-116">Presents a utility method that lists all nodes in an XML tree.</span></span> <span data-ttu-id="2695c-117">此方法可用于调试修改 XML 树的代码。</span><span class="sxs-lookup"><span data-stu-id="2695c-117">This is useful for debugging code that modifies an XML tree.</span></span>|  
|[<span data-ttu-id="2695c-118">如何︰ 从 Office Open XML 文档 (Visual Basic 中) 中检索段落</span><span class="sxs-lookup"><span data-stu-id="2695c-118">How to: Retrieve Paragraphs from an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-retrieve-paragraphs-from-an-office-open-xml-document.md)|<span data-ttu-id="2695c-119">演示打开 Office Open XML 文档；检索 XElement 对象集合中的段落、段落文本和段落样式的代码。</span><span class="sxs-lookup"><span data-stu-id="2695c-119">Presents code that opens an Office Open XML Document, retrieves the paragraphs in a collection of XElement objects, the text of the paragraphs, and the style of the paragraphs.</span></span>|  
|[<span data-ttu-id="2695c-120">如何︰ 修改 Office Open XML 文档 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-120">How to: Modify an Office Open XML Document (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-modify-an-office-open-xml-document.md)|<span data-ttu-id="2695c-121">演示打开、修改和保存 Office Open XML 文档的代码。</span><span class="sxs-lookup"><span data-stu-id="2695c-121">Presents code that opens, modifies, and saves an Office Open XML Document.</span></span>|  
|[<span data-ttu-id="2695c-122">如何︰ 填充 XML 树从文件系统 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-122">How to: Populate an XML Tree from the File System (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-populate-an-xml-tree-from-the-file-system.md)|<span data-ttu-id="2695c-123">演示从文件系统创建 XML 树的代码。</span><span class="sxs-lookup"><span data-stu-id="2695c-123">Presents code that creates an XML tree from the file system.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2695c-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2695c-124">See Also</span></span>  
 [<span data-ttu-id="2695c-125">查询 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2695c-125">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
