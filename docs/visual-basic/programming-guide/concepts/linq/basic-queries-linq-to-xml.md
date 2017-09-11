---
title: "基本查询 (LINQ to XML) (Visual Basic 中) |Microsoft 文档"
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
ms.assetid: aec6ef60-f6f4-4548-b3db-cf6c94bb0008
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 5c558201ad4fdd5412930651fa926f4441b78346
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017


---
# <a name="basic-queries-linq-to-xml-visual-basic"></a><span data-ttu-id="0d1f5-102">基本查询 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-102">Basic Queries (LINQ to XML) (Visual Basic)</span></span>
<span data-ttu-id="0d1f5-103">本节提供基本 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询的示例。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-103">This section provides examples of basic [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] queries.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0d1f5-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="0d1f5-104">In This Section</span></span>  
  
|<span data-ttu-id="0d1f5-105">主题</span><span class="sxs-lookup"><span data-stu-id="0d1f5-105">Topic</span></span>|<span data-ttu-id="0d1f5-106">说明</span><span class="sxs-lookup"><span data-stu-id="0d1f5-106">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="0d1f5-107">如何︰ 查找具有特定属性 (Visual Basic 中) 的元素</span><span class="sxs-lookup"><span data-stu-id="0d1f5-107">How to: Find an Element with a Specific Attribute (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-element-with-a-specific-attribute.md)|<span data-ttu-id="0d1f5-108">演示如何查找特定的元素，该元素包含具有特定值的属性。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-108">Shows how to find a particular element that has an attribute that has a specific value.</span></span>|  
|[<span data-ttu-id="0d1f5-109">如何︰ 查找具有特定子元素 (Visual Basic 中) 的元素</span><span class="sxs-lookup"><span data-stu-id="0d1f5-109">How to: Find an Element with a Specific Child Element (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-an-element-with-a-specific-child-element.md)|<span data-ttu-id="0d1f5-110">演示如何查找特定的元素，该元素包含具有特定值的子元素。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-110">Shows how to find a particular element that has a child element that has a specific value.</span></span>|  
|[<span data-ttu-id="0d1f5-111">查询 XDocument 与查询 XElement (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-111">Querying an XDocument vs. Querying an XElement (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-an-xdocument-vs-querying-an-xelement.md)|<span data-ttu-id="0d1f5-112">说明和<xref:System.Xml.Linq.XElement>编写查询 XML 树的根部位于<xref:System.Xml.Linq.XDocument>。</xref:System.Xml.Linq.XDocument>上</xref:System.Xml.Linq.XElement>取得 root 权限的 XML 树上编写查询之间的差异</span><span class="sxs-lookup"><span data-stu-id="0d1f5-112">Explains the differences between writing queries on an XML tree that is rooted in <xref:System.Xml.Linq.XElement> and writing queries on an XML tree that is rooted in <xref:System.Xml.Linq.XDocument>.</span></span>|  
|[<span data-ttu-id="0d1f5-113">如何︰ 查找具有特定元素名称 (Visual Basic 中) 的子代</span><span class="sxs-lookup"><span data-stu-id="0d1f5-113">How to: Find Descendants with a Specific Element Name (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-descendants-with-a-specific-element-name.md)|<span data-ttu-id="0d1f5-114">演示如何查找元素的具有特定名称的所有子代。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-114">Shows how to find all the descendants of an element that have a specific name.</span></span> <span data-ttu-id="0d1f5-115">此示例使用<xref:System.Xml.Linq.XContainer.Descendants%2A>轴。</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="0d1f5-115">This example uses the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis.</span></span>|  
|[<span data-ttu-id="0d1f5-116">如何︰ 查找单个子代使用 Descendants 方法 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-116">How to: Find a Single Descendant Using the Descendants Method (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-a-single-descendant-using-the-descendants-method.md)|<span data-ttu-id="0d1f5-117">演示如何使用<xref:System.Xml.Linq.XContainer.Descendants%2A>轴方法来查找单个具有唯一名称的元素。</xref:System.Xml.Linq.XContainer.Descendants%2A></span><span class="sxs-lookup"><span data-stu-id="0d1f5-117">Shows how to use the <xref:System.Xml.Linq.XContainer.Descendants%2A> axis method to find a single uniquely named element.</span></span>|  
|[<span data-ttu-id="0d1f5-118">如何︰ 使用复杂筛选 (Visual Basic) 编写查询</span><span class="sxs-lookup"><span data-stu-id="0d1f5-118">How to: Write Queries with Complex Filtering (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-queries-with-complex-filtering.md)|<span data-ttu-id="0d1f5-119">演示如何编写具有更复杂的筛选器的查询。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-119">Shows how to write a query with a more complex filter.</span></span>|  
|[<span data-ttu-id="0d1f5-120">如何︰ 筛选可选元素 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-120">How to: Filter on an Optional Element (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-filter-on-an-optional-element.md)|<span data-ttu-id="0d1f5-121">演示如何在形状不规则的树中查找节点。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-121">Shows how to find nodes in an irregularly shaped tree.</span></span>|  
|[<span data-ttu-id="0d1f5-122">如何︰ 查找 Namespace (Visual Basic 中) 中的所有节点</span><span class="sxs-lookup"><span data-stu-id="0d1f5-122">How to: Find All Nodes in a Namespace (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-find-all-nodes-in-a-namespace.md)|<span data-ttu-id="0d1f5-123">演示如何查找特定命名空间中的所有节点。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-123">Shows how to find all nodes that are in a specific namespace.</span></span>|  
|[<span data-ttu-id="0d1f5-124">如何︰ 对元素 (Visual Basic 中) 进行排序</span><span class="sxs-lookup"><span data-stu-id="0d1f5-124">How to: Sort Elements (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-elements.md)|<span data-ttu-id="0d1f5-125">演示如何编写对查询结果进行排序的查询。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-125">Shows how to write a query that sorts its results.</span></span>|  
|[<span data-ttu-id="0d1f5-126">如何︰ 对多个键 (Visual Basic 中) 上的元素进行排序</span><span class="sxs-lookup"><span data-stu-id="0d1f5-126">How to: Sort Elements on Multiple Keys (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-sort-elements-on-multiple-keys.md)|<span data-ttu-id="0d1f5-127">演示如何对多个键进行排序。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-127">Shows how to sort on multiple keys.</span></span>|  
|[<span data-ttu-id="0d1f5-128">如何︰ 计算中间值 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-128">How to: Calculate Intermediate Values (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-calculate-intermediate-values.md)|<span data-ttu-id="0d1f5-129">演示如何使用 `Let` 子句在 [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] 查询中计算中间值。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-129">Shows how to use the `Let` clause to calculate intermediate values in a [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq_md.md)] query.</span></span>|  
|[<span data-ttu-id="0d1f5-130">如何︰ 编写基于上下文 (Visual Basic 中) 查找元素的查询</span><span class="sxs-lookup"><span data-stu-id="0d1f5-130">How to: Write a Query that Finds Elements Based on Context (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-write-a-query-that-finds-elements-based-on-context.md)|<span data-ttu-id="0d1f5-131">演示如何根据树中的其他元素来选择元素。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-131">Shows how to select elements based on other elements in the tree.</span></span>|  
|[<span data-ttu-id="0d1f5-132">如何︰ 调试空查询结果集 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-132">How to: Debug Empty Query Results Sets (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-debug-empty-query-results-sets.md)|<span data-ttu-id="0d1f5-133">显示在对针对默认命名空间中 XML 的查询进行调试时相应的修补程序。</span><span class="sxs-lookup"><span data-stu-id="0d1f5-133">Shows the appropriate fix when debugging queries on XML that is in a default namespace.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0d1f5-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0d1f5-134">See Also</span></span>  
 [<span data-ttu-id="0d1f5-135">查询 XML 树 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0d1f5-135">Querying XML Trees (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/querying-xml-trees.md)
