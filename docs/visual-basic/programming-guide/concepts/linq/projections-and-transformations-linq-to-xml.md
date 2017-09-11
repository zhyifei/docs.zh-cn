---
title: "投影和转换 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: 297de224-b625-44cf-8c00-186b6189aa0e
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 723685400aadbf883d7ad939e6a1dd5bdeb7ba09
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="projections-and-transformations-linq-to-xml-visual-basic"></a><span data-ttu-id="77efb-102">投影和转换 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77efb-102">Projections and Transformations (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="77efb-103">本部分提供的示例[!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)]投影和转换。</span><span class="sxs-lookup"><span data-stu-id="77efb-103">This section provides examples of [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="77efb-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="77efb-104">In This Section</span></span>  
  
|<span data-ttu-id="77efb-105">主题</span><span class="sxs-lookup"><span data-stu-id="77efb-105">Topic</span></span>|<span data-ttu-id="77efb-106">说明</span><span class="sxs-lookup"><span data-stu-id="77efb-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="77efb-107">如何︰ 使用 LINQ to XML (Visual Basic 中) 处理字典</span><span class="sxs-lookup"><span data-stu-id="77efb-107">How to: Work with Dictionaries Using LINQ to XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="77efb-108">演示如何将字典转换为 XML，以及如何将 XML 转换为字典。</span><span class="sxs-lookup"><span data-stu-id="77efb-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="77efb-109">如何︰ 转换 XML 树 (Visual Basic 中) 的形状</span><span class="sxs-lookup"><span data-stu-id="77efb-109">How to: Transform the Shape of an XML Tree (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="77efb-110">演示如何转换 XML 文档的形状。</span><span class="sxs-lookup"><span data-stu-id="77efb-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="77efb-111">如何︰ 控制投影 (Visual Basic 中) 的类型</span><span class="sxs-lookup"><span data-stu-id="77efb-111">How to: Control the Type of a Projection (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="77efb-112">演示如何控制 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询的类型。</span><span class="sxs-lookup"><span data-stu-id="77efb-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="77efb-113">如何︰ 投影新类型 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77efb-113">How to: Project a New Type (LINQ to XML) (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="77efb-114">演示如何从 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询投影用户定义类型的集合。</span><span class="sxs-lookup"><span data-stu-id="77efb-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="77efb-115">如何︰ 投影对象图 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77efb-115">How to: Project an Object Graph (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="77efb-116">演示如何从 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询投影更复杂的对象图。</span><span class="sxs-lookup"><span data-stu-id="77efb-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="77efb-117">如何︰ 投影匿名类型 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77efb-117">How to: Project an Anonymous Type (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="77efb-118">演示如何从 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询投影匿名对象的集合。</span><span class="sxs-lookup"><span data-stu-id="77efb-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="77efb-119">如何︰ 从 XML (Visual Basic 中) 生成文本文件</span><span class="sxs-lookup"><span data-stu-id="77efb-119">How to: Generate Text Files from XML (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="77efb-120">演示如何将 XML 文件转换为非 XML 文本文件。</span><span class="sxs-lookup"><span data-stu-id="77efb-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="77efb-121">如何︰ 从 CSV 文件 (Visual Basic 中) 生成 XML</span><span class="sxs-lookup"><span data-stu-id="77efb-121">How to: Generate XML from CSV Files (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="77efb-122">演示如何使用 [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] 分析 CSV 文件并从它生成 XML。</span><span class="sxs-lookup"><span data-stu-id="77efb-122">Shows how to use [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq_md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="77efb-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77efb-123">See Also</span></span>  
 [<span data-ttu-id="77efb-124">查询 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77efb-124">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
