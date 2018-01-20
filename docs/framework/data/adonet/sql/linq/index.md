---
title: LINQ to SQL
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 62f7a3b0fcefa9eb6f5b56d96217a9988a193104
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/19/2018
---
# <a name="linq-to-sql"></a><span data-ttu-id="737fa-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="737fa-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="737fa-103"> 是 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 3.5 版的一个组件，提供了用于将关系数据作为对象管理的运行时基础结构。</span><span class="sxs-lookup"><span data-stu-id="737fa-103"> is a component of [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="737fa-104">关系数据显示为由二维表（关系或平面文件）组成的集合，其中公共列将表互相关联起来。</span><span class="sxs-lookup"><span data-stu-id="737fa-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="737fa-105">若要有效地使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，您必须略为熟悉关系数据库的基本原理。</span><span class="sxs-lookup"><span data-stu-id="737fa-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="737fa-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。</span><span class="sxs-lookup"><span data-stu-id="737fa-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="737fa-107">当应用程序运行时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将它们发送到数据库进行执行。</span><span class="sxs-lookup"><span data-stu-id="737fa-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="737fa-108">当数据库返回结果时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将它们转换回您可以用您自己的编程语言处理的对象。</span><span class="sxs-lookup"><span data-stu-id="737fa-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="737fa-109">使用 [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] 的开发人员通常使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]，它提供了用于实现许多 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 功能的用户界面。</span><span class="sxs-lookup"><span data-stu-id="737fa-109">Developers using [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="737fa-110">此版本的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 附带的文档介绍了生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序所需的基本构造块、流程和技术。</span><span class="sxs-lookup"><span data-stu-id="737fa-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="737fa-111">你还可以搜索 Microsoft 文档的特定问题，并且可以参与[LINQ 论坛](http://go.microsoft.com/fwlink/?LinkId=76488)，可以与专家们讨论更复杂的主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="737fa-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](http://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="737fa-112">最后，[LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205)（LINQ to SQL：关系数据的 .NET 语言集成查询）白皮书详细介绍了 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 技术并包含了 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 和 C# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="737fa-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](http://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="737fa-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="737fa-113">In This Section</span></span>  
 [<span data-ttu-id="737fa-114">入门</span><span class="sxs-lookup"><span data-stu-id="737fa-114">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 <span data-ttu-id="737fa-115">提供对 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的简要概述以及有关如何开始使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的信息。</span><span class="sxs-lookup"><span data-stu-id="737fa-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="737fa-116">编程指南</span><span class="sxs-lookup"><span data-stu-id="737fa-116">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="737fa-117">提供映射、查询、更新、调试及类似任务的步骤。</span><span class="sxs-lookup"><span data-stu-id="737fa-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="737fa-118">参考</span><span class="sxs-lookup"><span data-stu-id="737fa-118">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 <span data-ttu-id="737fa-119">提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的多个方面的参考信息。</span><span class="sxs-lookup"><span data-stu-id="737fa-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="737fa-120">相关主题包括“SQL-CLR 类型映射”、“标准查询运算符转换”等。</span><span class="sxs-lookup"><span data-stu-id="737fa-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="737fa-121">示例</span><span class="sxs-lookup"><span data-stu-id="737fa-121">Samples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 <span data-ttu-id="737fa-122">提供指向 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 和 C# 示例的链接。</span><span class="sxs-lookup"><span data-stu-id="737fa-122">Provides links to [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="737fa-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="737fa-123">Related Sections</span></span>  
 [<span data-ttu-id="737fa-124">LINQ（语言集成查询）</span><span class="sxs-lookup"><span data-stu-id="737fa-124">LINQ (Language-Integrated Query)</span></span>](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 <span data-ttu-id="737fa-125">提供对 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 技术的概述。</span><span class="sxs-lookup"><span data-stu-id="737fa-125">Provides an overview of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies.</span></span>  
  
 [<span data-ttu-id="737fa-126">LINQ</span><span class="sxs-lookup"><span data-stu-id="737fa-126">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="737fa-127">介绍针对 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 用户的 [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] 技术。</span><span class="sxs-lookup"><span data-stu-id="737fa-127">Describes [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies for [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] users.</span></span>  
  
 [<span data-ttu-id="737fa-128">LINQ to ADO.NET</span><span class="sxs-lookup"><span data-stu-id="737fa-128">LINQ to ADO.NET</span></span>](http://msdn.microsoft.com/library/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 <span data-ttu-id="737fa-129">链接到 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 门户。</span><span class="sxs-lookup"><span data-stu-id="737fa-129">Links to the [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] portal.</span></span>  
  
 [<span data-ttu-id="737fa-130">LINQ to SQL 演练</span><span class="sxs-lookup"><span data-stu-id="737fa-130">LINQ to SQL Walkthroughs</span></span>](http://msdn.microsoft.com/library/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 <span data-ttu-id="737fa-131">列出可用于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的演练。</span><span class="sxs-lookup"><span data-stu-id="737fa-131">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="737fa-132">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="737fa-132">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 <span data-ttu-id="737fa-133">介绍如何下载文档中使用的示例数据库。</span><span class="sxs-lookup"><span data-stu-id="737fa-133">Describes how to download sample databases used in the documentation.</span></span>  
  
 [<span data-ttu-id="737fa-134">LinqDataSource 技术概述</span><span class="sxs-lookup"><span data-stu-id="737fa-134">LinqDataSource Technology Overview</span></span>](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)  
 <span data-ttu-id="737fa-135">介绍 <xref:System.Web.UI.WebControls.LinqDataSource> 控件如何通过 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 数据源控件结构向 Web 开发人员公开 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="737fa-135">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] to Web developers through the [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)] data-source control architecture.</span></span>
