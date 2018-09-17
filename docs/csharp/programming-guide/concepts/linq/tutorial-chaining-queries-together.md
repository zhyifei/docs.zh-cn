---
title: 教程：将查询链接在一起 (C#)
ms.date: 07/20/2015
ms.assetid: 44f54444-c4c5-4c23-9d19-986b957b8eda
ms.openlocfilehash: cab012a6ae618bd731c26bc1a002c144b84d2169
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2018
ms.locfileid: "45609627"
---
# <a name="tutorial-chaining-queries-together-c"></a><span data-ttu-id="715a2-102">教程：将查询链接在一起 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-102">Tutorial: Chaining Queries Together (C#)</span></span>
<span data-ttu-id="715a2-103">本教程阐释将查询链接在一起时的处理模型。</span><span class="sxs-lookup"><span data-stu-id="715a2-103">This tutorial illustrates the processing model when you chain queries together.</span></span> <span data-ttu-id="715a2-104">将查询链接在一起是编写函数转换的一个关键部分。</span><span class="sxs-lookup"><span data-stu-id="715a2-104">Chaining queries together is a key part of writing functional transformations.</span></span> <span data-ttu-id="715a2-105">确切理解链接的查询如何工作非常重要。</span><span class="sxs-lookup"><span data-stu-id="715a2-105">It is important to understand exactly how chained queries work.</span></span>  
  
 <span data-ttu-id="715a2-106">处理 Office Open XML 文档的查询广泛使用了这种方法。</span><span class="sxs-lookup"><span data-stu-id="715a2-106">The queries that process Office Open XML documents use this technique extensively.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="715a2-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="715a2-107">In This Section</span></span>  
  
|<span data-ttu-id="715a2-108">主题</span><span class="sxs-lookup"><span data-stu-id="715a2-108">Topic</span></span>|<span data-ttu-id="715a2-109">描述</span><span class="sxs-lookup"><span data-stu-id="715a2-109">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="715a2-110">LINQ to XML 中的延迟执行和迟缓计算 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-110">Deferred Execution and Lazy Evaluation in LINQ to XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-and-lazy-evaluation-in-linq-to-xml.md)|<span data-ttu-id="715a2-111">描述延迟执行和迟缓计算的概念。</span><span class="sxs-lookup"><span data-stu-id="715a2-111">Describes the concepts of deferred execution and lazy evaluation.</span></span>|  
|[<span data-ttu-id="715a2-112">延迟执行示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-112">Deferred Execution Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/deferred-execution-example.md)|<span data-ttu-id="715a2-113">提供一个延迟执行的示例。</span><span class="sxs-lookup"><span data-stu-id="715a2-113">Provides an example of deferred execution.</span></span>|  
|[<span data-ttu-id="715a2-114">链接查询示例 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-114">Chaining Queries Example (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-queries-example.md)|<span data-ttu-id="715a2-115">演示在将查询链接在一起时延迟执行的工作方式。</span><span class="sxs-lookup"><span data-stu-id="715a2-115">Shows how deferred execution works when chaining queries together.</span></span>|  
|[<span data-ttu-id="715a2-116">中间具体化 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-116">Intermediate Materialization (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/intermediate-materialization.md)|<span data-ttu-id="715a2-117">确定和说明中间具体化的语义。</span><span class="sxs-lookup"><span data-stu-id="715a2-117">Identifies and illustrates the semantics of intermediate materialization.</span></span>|  
|[<span data-ttu-id="715a2-118">将标准查询运算符链接在一起 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-118">Chaining Standard Query Operators Together (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/chaining-standard-query-operators-together.md)|<span data-ttu-id="715a2-119">描述标准查询运算符的迟缓语义。</span><span class="sxs-lookup"><span data-stu-id="715a2-119">Describes the lazy semantics of the standard query operators.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="715a2-120">请参阅</span><span class="sxs-lookup"><span data-stu-id="715a2-120">See Also</span></span>

- [<span data-ttu-id="715a2-121">XML 的纯功能转换 (C#)</span><span class="sxs-lookup"><span data-stu-id="715a2-121">Pure Functional Transformations of XML (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/pure-functional-transformations-of-xml.md)
