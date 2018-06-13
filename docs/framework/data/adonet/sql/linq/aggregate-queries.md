---
title: 聚合查询
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: e4d5e0a9dc1ffb0bf1857fee788d46947f3901d4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33358838"
---
# <a name="aggregate-queries"></a><span data-ttu-id="1cad7-102">聚合查询</span><span class="sxs-lookup"><span data-stu-id="1cad7-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="1cad7-103"> 支持 `Average`、`Count`、`Max`、`Min` 和 `Sum` 聚合运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-103"> supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="1cad7-104">请注意 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中聚合运算符的以下特征：</span><span class="sxs-lookup"><span data-stu-id="1cad7-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
-   <span data-ttu-id="1cad7-105">聚合查询是立即执行的。</span><span class="sxs-lookup"><span data-stu-id="1cad7-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="1cad7-106">有关详细信息，请参阅 [LINQ 查询简介 (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="1cad7-106">For more information, see [Introduction to LINQ Queries (C#)](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
-   <span data-ttu-id="1cad7-107">聚合查询通常返回一个数字，而非一个集合。</span><span class="sxs-lookup"><span data-stu-id="1cad7-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="1cad7-108">有关详细信息，请参阅[聚合操作](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4)。</span><span class="sxs-lookup"><span data-stu-id="1cad7-108">For more information, see [Aggregation Operations](http://msdn.microsoft.com/library/36d97c83-5de5-457d-971d-10a69365e7c4).</span></span>  
  
-   <span data-ttu-id="1cad7-109">不能对匿名类型调用聚合。</span><span class="sxs-lookup"><span data-stu-id="1cad7-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="1cad7-110">以下主题中的示例来自 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="1cad7-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="1cad7-111">有关详细信息，请参阅[下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="1cad7-111">For more information, see [Downloading Sample Databases](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1cad7-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="1cad7-112">In This Section</span></span>  
 [<span data-ttu-id="1cad7-113">从数值序列中返回平均值</span><span class="sxs-lookup"><span data-stu-id="1cad7-113">Return the Average Value From a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="1cad7-114">演示如何使用 <xref:System.Linq.Enumerable.Average%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="1cad7-115">对序列中元素的数目进行计数</span><span class="sxs-lookup"><span data-stu-id="1cad7-115">Count the Number of Elements in a Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="1cad7-116">演示如何使用 <xref:System.Linq.Enumerable.Count%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="1cad7-117">查找数值序列中的最大值</span><span class="sxs-lookup"><span data-stu-id="1cad7-117">Find the Maximum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="1cad7-118">演示如何使用 <xref:System.Linq.Enumerable.Max%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="1cad7-119">查找数值序列中的最小值</span><span class="sxs-lookup"><span data-stu-id="1cad7-119">Find the Minimum Value in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="1cad7-120">演示如何使用 <xref:System.Linq.Enumerable.Min%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="1cad7-121">计算数值序列中值的和</span><span class="sxs-lookup"><span data-stu-id="1cad7-121">Compute the Sum of Values in a Numeric Sequence</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="1cad7-122">演示如何使用 <xref:System.Linq.Enumerable.Sum%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="1cad7-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="1cad7-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="1cad7-123">Related Sections</span></span>  
 [<span data-ttu-id="1cad7-124">查询示例</span><span class="sxs-lookup"><span data-stu-id="1cad7-124">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)  
 <span data-ttu-id="1cad7-125">提供指向 Visual Basic 和 C# 中 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的链接。</span><span class="sxs-lookup"><span data-stu-id="1cad7-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="1cad7-126">查询概念</span><span class="sxs-lookup"><span data-stu-id="1cad7-126">Query Concepts</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)  
 <span data-ttu-id="1cad7-127">提供指向特定主题的链接，这些主题解释有关在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中设计 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的一些概念。</span><span class="sxs-lookup"><span data-stu-id="1cad7-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="1cad7-128">LINQ 查询简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="1cad7-128">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="1cad7-129">解释 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中查询的工作原理。</span><span class="sxs-lookup"><span data-stu-id="1cad7-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
