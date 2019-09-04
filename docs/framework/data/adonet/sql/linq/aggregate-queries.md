---
title: 聚合查询
ms.date: 03/30/2017
ms.assetid: 13ec5580-05ce-4a1f-9d3d-8660be7891a2
ms.openlocfilehash: e61b16d6337c9b40f9e94052869a4c5592291d71
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248105"
---
# <a name="aggregate-queries"></a><span data-ttu-id="6a2fa-102">聚合查询</span><span class="sxs-lookup"><span data-stu-id="6a2fa-102">Aggregate Queries</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6a2fa-103">支持 `Average`、`Count`、`Max`、`Min` 和 `Sum` 聚合运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-103">supports the `Average`, `Count`, `Max`, `Min`, and `Sum` aggregate operators.</span></span> <span data-ttu-id="6a2fa-104">请注意 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中聚合运算符的以下特征：</span><span class="sxs-lookup"><span data-stu-id="6a2fa-104">Note the following characteristics of aggregate operators in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:</span></span>  
  
- <span data-ttu-id="6a2fa-105">聚合查询是立即执行的。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-105">Aggregate queries are executed immediately.</span></span>  
  
     <span data-ttu-id="6a2fa-106">有关详细信息，请参阅 [LINQ 查询简介 (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
- <span data-ttu-id="6a2fa-107">聚合查询通常返回一个数字，而非一个集合。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-107">Aggregate queries typically return a number instead of a collection.</span></span>  
  
     <span data-ttu-id="6a2fa-108">有关详细信息，请参阅[聚合运算](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120))。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-108">For more information, see [Aggregation Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb546138(v=vs.120)).</span></span>  
  
- <span data-ttu-id="6a2fa-109">不能对匿名类型调用聚合。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-109">You cannot call aggregates against anonymous types.</span></span>  
  
 <span data-ttu-id="6a2fa-110">以下主题中的示例来自 Northwind 示例数据库。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-110">The examples in the following topics derive from the Northwind sample database.</span></span> <span data-ttu-id="6a2fa-111">有关详细信息，请参阅[下载示例数据库](downloading-sample-databases.md)。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-111">For more information, see [Downloading Sample Databases](downloading-sample-databases.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6a2fa-112">本节内容</span><span class="sxs-lookup"><span data-stu-id="6a2fa-112">In This Section</span></span>  
 [<span data-ttu-id="6a2fa-113">从数值序列中返回平均值</span><span class="sxs-lookup"><span data-stu-id="6a2fa-113">Return the Average Value From a Numeric Sequence</span></span>](return-the-average-value-from-a-numeric-sequence.md)  
 <span data-ttu-id="6a2fa-114">演示如何使用 <xref:System.Linq.Enumerable.Average%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-114">Demonstrates how to use the <xref:System.Linq.Enumerable.Average%2A> operator.</span></span>  
  
 [<span data-ttu-id="6a2fa-115">对序列中元素的数目进行计数</span><span class="sxs-lookup"><span data-stu-id="6a2fa-115">Count the Number of Elements in a Sequence</span></span>](count-the-number-of-elements-in-a-sequence.md)  
 <span data-ttu-id="6a2fa-116">演示如何使用 <xref:System.Linq.Enumerable.Count%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-116">Demonstrates how to use the <xref:System.Linq.Enumerable.Count%2A> operator.</span></span>  
  
 [<span data-ttu-id="6a2fa-117">查找数值序列中的最大值</span><span class="sxs-lookup"><span data-stu-id="6a2fa-117">Find the Maximum Value in a Numeric Sequence</span></span>](find-the-maximum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="6a2fa-118">演示如何使用 <xref:System.Linq.Enumerable.Max%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-118">Demonstrates how to use the <xref:System.Linq.Enumerable.Max%2A> operator.</span></span>  
  
 [<span data-ttu-id="6a2fa-119">查找数值序列中的最小值</span><span class="sxs-lookup"><span data-stu-id="6a2fa-119">Find the Minimum Value in a Numeric Sequence</span></span>](find-the-minimum-value-in-a-numeric-sequence.md)  
 <span data-ttu-id="6a2fa-120">演示如何使用 <xref:System.Linq.Enumerable.Min%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-120">Demonstrates how to use the <xref:System.Linq.Enumerable.Min%2A> operator.</span></span>  
  
 [<span data-ttu-id="6a2fa-121">计算数值序列中值的和</span><span class="sxs-lookup"><span data-stu-id="6a2fa-121">Compute the Sum of Values in a Numeric Sequence</span></span>](compute-the-sum-of-values-in-a-numeric-sequence.md)  
 <span data-ttu-id="6a2fa-122">演示如何使用 <xref:System.Linq.Enumerable.Sum%2A> 运算符。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-122">Demonstrates how to use the <xref:System.Linq.Enumerable.Sum%2A> operator.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="6a2fa-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="6a2fa-123">Related Sections</span></span>  
 [<span data-ttu-id="6a2fa-124">查询示例</span><span class="sxs-lookup"><span data-stu-id="6a2fa-124">Query Examples</span></span>](query-examples.md)  
 <span data-ttu-id="6a2fa-125">提供指向 Visual Basic 和 C# 中 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的链接。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-125">Provides links to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries in Visual Basic and C#.</span></span>  
  
 [<span data-ttu-id="6a2fa-126">查询概念</span><span class="sxs-lookup"><span data-stu-id="6a2fa-126">Query Concepts</span></span>](query-concepts.md)  
 <span data-ttu-id="6a2fa-127">提供指向特定主题的链接，这些主题解释有关在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中设计 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的一些概念。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-127">Provides links to topics that explain concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="6a2fa-128">LINQ 查询简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="6a2fa-128">Introduction to LINQ Queries (C#)</span></span>](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="6a2fa-129">解释 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中查询的工作原理。</span><span class="sxs-lookup"><span data-stu-id="6a2fa-129">Explains how queries work in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
