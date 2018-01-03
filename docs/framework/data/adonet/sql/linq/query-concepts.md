---
title: "查询概念"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a125749-ccb5-49d5-999d-d2db7171d74d
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 907761184256b7cf51c7c0f20fa43ee603e0ab12
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="query-concepts"></a><span data-ttu-id="a6858-102">查询概念</span><span class="sxs-lookup"><span data-stu-id="a6858-102">Query Concepts</span></span>
<span data-ttu-id="a6858-103">本节介绍有关在 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中设计 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 查询的一些关键概念。</span><span class="sxs-lookup"><span data-stu-id="a6858-103">This section describes key concepts for designing [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6858-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="a6858-104">In This Section</span></span>  
 [<span data-ttu-id="a6858-105">LINQ to SQL 查询</span><span class="sxs-lookup"><span data-stu-id="a6858-105">LINQ to SQL Queries</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/linq-to-sql-queries.md)  
 <span data-ttu-id="a6858-106">参考一般性的 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 主题，并解释特定于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的项。</span><span class="sxs-lookup"><span data-stu-id="a6858-106">Refers to general [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] topics, and explains items specific to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="a6858-107">跨关系查询</span><span class="sxs-lookup"><span data-stu-id="a6858-107">Querying Across Relationships</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-across-relationships.md)  
 <span data-ttu-id="a6858-108">解释如何在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 对象模型中使用关联。</span><span class="sxs-lookup"><span data-stu-id="a6858-108">Explains how to use associations in the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] object model.</span></span>  
  
 [<span data-ttu-id="a6858-109">远程查询执行与本地执行</span><span class="sxs-lookup"><span data-stu-id="a6858-109">Remote vs. Local Execution</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/remote-vs-local-execution.md)  
 <span data-ttu-id="a6858-110">解释如何指定您希望执行查询的位置。</span><span class="sxs-lookup"><span data-stu-id="a6858-110">Explains how to specify where you want your query executed.</span></span>  
  
 [<span data-ttu-id="a6858-111">推迟加载与即时加载</span><span class="sxs-lookup"><span data-stu-id="a6858-111">Deferred versus Immediate Loading</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)  
 <span data-ttu-id="a6858-112">介绍如何指定加载相关对象的时间。</span><span class="sxs-lookup"><span data-stu-id="a6858-112">Describes how to specify when related objects are loaded.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a6858-113">相关章节</span><span class="sxs-lookup"><span data-stu-id="a6858-113">Related Sections</span></span>  
 [<span data-ttu-id="a6858-114">编程指南</span><span class="sxs-lookup"><span data-stu-id="a6858-114">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="a6858-115">包含指向解释 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 技术的主题的链接。</span><span class="sxs-lookup"><span data-stu-id="a6858-115">Contains links to topics that explain the [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology.</span></span>  
  
 [<span data-ttu-id="a6858-116">对象标识</span><span class="sxs-lookup"><span data-stu-id="a6858-116">Object Identity</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/object-identity.md)  
 <span data-ttu-id="a6858-117">解释 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中对象标识的概念。</span><span class="sxs-lookup"><span data-stu-id="a6858-117">Explains the concept of object identity in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="a6858-118">LINQ 查询简介 (C#)</span><span class="sxs-lookup"><span data-stu-id="a6858-118">Introduction to LINQ Queries (C#)</span></span>](~/docs/csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)  
 <span data-ttu-id="a6858-119">提供有关 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 中的查询操作的介绍。</span><span class="sxs-lookup"><span data-stu-id="a6858-119">Provides an introduction to query operations in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span>
