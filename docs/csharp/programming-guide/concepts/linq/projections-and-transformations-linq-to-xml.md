---
title: "投影和转换 (LINQ to XML) (C#)"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-csharp
ms.topic: article
ms.assetid: bb0457ab-1823-47e6-9d2d-c93c958cc913
caps.latest.revision: "3"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 81172ebb440bc2737bbe3f1de0f1dd3cf6e086c4
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="projections-and-transformations-linq-to-xml-c"></a><span data-ttu-id="5ee3e-102">投影和转换 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-102">Projections and Transformations (LINQ to XML) (C#)</span></span>
<span data-ttu-id="5ee3e-103">本节提供 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 投影和转换的示例。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-103">This section provides examples of [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] projections and transformations.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5ee3e-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="5ee3e-104">In This Section</span></span>  
  
|<span data-ttu-id="5ee3e-105">主题</span><span class="sxs-lookup"><span data-stu-id="5ee3e-105">Topic</span></span>|<span data-ttu-id="5ee3e-106">描述</span><span class="sxs-lookup"><span data-stu-id="5ee3e-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="5ee3e-107">如何：通过 LINQ to XML 使用字典 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-107">How to: Work with Dictionaries Using LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-work-with-dictionaries-using-linq-to-xml.md)|<span data-ttu-id="5ee3e-108">演示如何将字典转换为 XML，以及如何将 XML 转换为字典。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-108">Shows how to transform dictionaries to XML, and how to transform XML into dictionaries.</span></span>|  
|[<span data-ttu-id="5ee3e-109">如何：转换 XML 树的形状 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-109">How to: Transform the Shape of an XML Tree (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-transform-the-shape-of-an-xml-tree.md)|<span data-ttu-id="5ee3e-110">演示如何转换 XML 文档的形状。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-110">Shows how to transform the shape of an XML document.</span></span>|  
|[<span data-ttu-id="5ee3e-111">如何：控制投影的类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-111">How to: Control the Type of a Projection (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-control-the-type-of-a-projection.md)|<span data-ttu-id="5ee3e-112">演示如何控制 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询的类型。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-112">Shows how to control the type of a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="5ee3e-113">如何：投影新类型 (LINQ to XML) (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-113">How to: Project a New Type (LINQ to XML) (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-a-new-type-linq-to-xml.md)|<span data-ttu-id="5ee3e-114">演示如何从 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询投影用户定义类型的集合。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-114">Shows how to project a collection of a user-defined type from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="5ee3e-115">如何：投影对象图 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-115">How to: Project an Object Graph (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-object-graph.md)|<span data-ttu-id="5ee3e-116">演示如何从 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询投影更复杂的对象图。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-116">Shows how to project a more complex object graph from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="5ee3e-117">如何：投影匿名类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-117">How to: Project an Anonymous Type (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-project-an-anonymous-type.md)|<span data-ttu-id="5ee3e-118">演示如何从 [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] 查询投影匿名对象的集合。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-118">Shows how to project a collection of anonymous objects from a [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)] query.</span></span>|  
|[<span data-ttu-id="5ee3e-119">如何：从 XML 生成文本文件 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-119">How to: Generate Text Files from XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-text-files-from-xml.md)|<span data-ttu-id="5ee3e-120">演示如何将 XML 文件转换为非 XML 文本文件。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-120">Shows how to transform an XML file to a non-XML text file.</span></span>|  
|[<span data-ttu-id="5ee3e-121">如何：从 CSV 文件生成 XML (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-121">How to: Generate XML from CSV Files (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/how-to-generate-xml-from-csv-files.md)|<span data-ttu-id="5ee3e-122">演示如何使用 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 分析 CSV 文件并从它生成 XML。</span><span class="sxs-lookup"><span data-stu-id="5ee3e-122">Shows how to use [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] to parse a CSV file and generate XML from it.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5ee3e-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="5ee3e-123">See Also</span></span>  
 [<span data-ttu-id="5ee3e-124">查询 XML 树 (C#)</span><span class="sxs-lookup"><span data-stu-id="5ee3e-124">Querying XML Trees (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/querying-xml-trees.md)
