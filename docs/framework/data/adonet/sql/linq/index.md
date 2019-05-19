---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 4a44bd3f55cf6c21bb785ff70bca80e2c003cd18
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2019
ms.locfileid: "65878267"
---
# <a name="linq-to-sql"></a><span data-ttu-id="d978b-102">LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="d978b-102">LINQ to SQL</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="d978b-103">是.NET Framework 版本 3.5，它提供用于管理关系数据作为对象的运行时基础结构的组件。</span><span class="sxs-lookup"><span data-stu-id="d978b-103">is a component of .NET Framework version 3.5 that provides a run-time infrastructure for managing relational data as objects.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d978b-104">关系数据显示为由二维表（关系或平面文件）组成的集合，其中公共列将表互相关联起来。</span><span class="sxs-lookup"><span data-stu-id="d978b-104">Relational data appears as a collection of two-dimensional tables (*relations* or *flat files*), where common columns relate tables to each other.</span></span> <span data-ttu-id="d978b-105">若要有效地使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，您必须略为熟悉关系数据库的基本原理。</span><span class="sxs-lookup"><span data-stu-id="d978b-105">To use [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] effectively, you must have some familiarity with the underlying principles of relational databases.</span></span>  
  
 <span data-ttu-id="d978b-106">在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。</span><span class="sxs-lookup"><span data-stu-id="d978b-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the data model of a relational database is mapped to an object model expressed in the programming language of the developer.</span></span> <span data-ttu-id="d978b-107">当应用程序运行时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将它们发送到数据库进行执行。</span><span class="sxs-lookup"><span data-stu-id="d978b-107">When the application runs, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates into SQL the language-integrated queries in the object model and sends them to the database for execution.</span></span> <span data-ttu-id="d978b-108">当数据库返回结果时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将它们转换回您可以用您自己的编程语言处理的对象。</span><span class="sxs-lookup"><span data-stu-id="d978b-108">When the database returns the results, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] translates them back to objects that you can work with in your own programming language.</span></span>  
  
 <span data-ttu-id="d978b-109">通常使用 Visual Studio 的开发人员使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]，它提供用于实现许多功能的用户界面[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d978b-109">Developers using Visual Studio typically use the [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)], which provides a user interface for implementing many of the features of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 <span data-ttu-id="d978b-110">此版本的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 附带的文档介绍了生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序所需的基本构造块、流程和技术。</span><span class="sxs-lookup"><span data-stu-id="d978b-110">The documentation that is included with this release of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] describes the basic building blocks, processes, and techniques you need for building [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="d978b-111">您还可以搜索 Microsoft Docs 特定问题，并且可以参与[LINQ 论坛](https://go.microsoft.com/fwlink/?LinkId=76488)，可以与专家们讨论更复杂的主题的详细信息。</span><span class="sxs-lookup"><span data-stu-id="d978b-111">You can also search Microsoft Docs for specific issues, and you can participate in the [LINQ Forum](https://go.microsoft.com/fwlink/?LinkId=76488), where you can discuss more complex topics in detail with experts.</span></span> <span data-ttu-id="d978b-112">最后， [LINQ to SQL： 关系数据的.net 语言集成查询](https://go.microsoft.com/fwlink/?LinkId=93205)白皮书详细介绍[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]技术并包含 Visual Basic 和 C# 代码示例。</span><span class="sxs-lookup"><span data-stu-id="d978b-112">Finally, the [LINQ to SQL: .NET Language-Integrated Query for Relational Data](https://go.microsoft.com/fwlink/?LinkId=93205) white paper details [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] technology, complete with Visual Basic and C# code examples.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="d978b-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="d978b-113">In This Section</span></span>  
 [<span data-ttu-id="d978b-114">入门</span><span class="sxs-lookup"><span data-stu-id="d978b-114">Getting Started</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 <span data-ttu-id="d978b-115">提供对 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的简要概述以及有关如何开始使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的信息。</span><span class="sxs-lookup"><span data-stu-id="d978b-115">Provides a condensed overview of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] along with information about how to get started using [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="d978b-116">编程指南</span><span class="sxs-lookup"><span data-stu-id="d978b-116">Programming Guide</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 <span data-ttu-id="d978b-117">提供映射、查询、更新、调试及类似任务的步骤。</span><span class="sxs-lookup"><span data-stu-id="d978b-117">Provides steps for mapping, querying, updating, debugging, and similar tasks.</span></span>  
  
 [<span data-ttu-id="d978b-118">引用</span><span class="sxs-lookup"><span data-stu-id="d978b-118">Reference</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 <span data-ttu-id="d978b-119">提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的多个方面的参考信息。</span><span class="sxs-lookup"><span data-stu-id="d978b-119">Provides reference information about several aspects of [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="d978b-120">相关主题包括“SQL-CLR 类型映射”、“标准查询运算符转换”等。</span><span class="sxs-lookup"><span data-stu-id="d978b-120">Topics include SQL-CLR Type Mapping, Standard Query Operator Translation, and more.</span></span>  
  
 [<span data-ttu-id="d978b-121">示例</span><span class="sxs-lookup"><span data-stu-id="d978b-121">Samples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 <span data-ttu-id="d978b-122">提供指向 Visual Basic 和 C# 示例。</span><span class="sxs-lookup"><span data-stu-id="d978b-122">Provides links to Visual Basic and C# samples.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="d978b-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="d978b-123">Related Sections</span></span>  
 <span data-ttu-id="d978b-124">[语言集成查询 (LINQ)-C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\\</span><span class="sxs-lookup"><span data-stu-id="d978b-124">[Language-Integrated Query (LINQ) - C#](../../../../../csharp/programming-guide/concepts/linq/index.md)\\</span></span>
 <span data-ttu-id="d978b-125">中的 LINQ 技术概述了C#。</span><span class="sxs-lookup"><span data-stu-id="d978b-125">Provides overviews of LINQ technologies in C#.</span></span>
 
 [<span data-ttu-id="d978b-126">语言集成查询 (LINQ) - Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d978b-126">Language-Integrated Query (LINQ) - Visual Basic</span></span>](../../../../../visual-basic/programming-guide/concepts/linq/index.md)  
 <span data-ttu-id="d978b-127">提供了在 Visual Basic 中的 LINQ 技术的概述。</span><span class="sxs-lookup"><span data-stu-id="d978b-127">Provides overviews of LINQ technologies in Visual Basic.</span></span>
  
 [<span data-ttu-id="d978b-128">LINQ</span><span class="sxs-lookup"><span data-stu-id="d978b-128">LINQ</span></span>](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 <span data-ttu-id="d978b-129">介绍[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]技术，可用于 Visual Basic 用户。</span><span class="sxs-lookup"><span data-stu-id="d978b-129">Describes [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] technologies for Visual Basic users.</span></span>  
  
 [<span data-ttu-id="d978b-130">LINQ 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d978b-130">LINQ and ADO.NET</span></span>](../../../../../../docs/framework/data/adonet/linq-and-ado-net.md)  
 <span data-ttu-id="d978b-131">ADO.NET 门户的链接。</span><span class="sxs-lookup"><span data-stu-id="d978b-131">Links to the ADO.NET portal.</span></span>  
  
 <span data-ttu-id="d978b-132">[LINQ to SQL 演练](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="d978b-132">[LINQ to SQL Walkthroughs](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/bb386295(v=vs.90))</span></span>  
 <span data-ttu-id="d978b-133">列出可用于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的演练。</span><span class="sxs-lookup"><span data-stu-id="d978b-133">Lists walkthroughs available for [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span>  
  
 [<span data-ttu-id="d978b-134">下载示例数据库</span><span class="sxs-lookup"><span data-stu-id="d978b-134">Downloading Sample Databases</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 <span data-ttu-id="d978b-135">介绍如何下载文档中使用的示例数据库。</span><span class="sxs-lookup"><span data-stu-id="d978b-135">Describes how to download sample databases used in the documentation.</span></span>  
  
 <span data-ttu-id="d978b-136">[LinqDataSource Web 服务器控件概述](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="d978b-136">[LinqDataSource Web Server Control Overview](https://docs.microsoft.com/previous-versions/aspnet/bb547113(v=vs.100))</span></span>  
 <span data-ttu-id="d978b-137">介绍如何<xref:System.Web.UI.WebControls.LinqDataSource>控件公开[!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)]Web 开发人员通过 ASP.NET 数据源控件体系结构。</span><span class="sxs-lookup"><span data-stu-id="d978b-137">Describes how the <xref:System.Web.UI.WebControls.LinqDataSource> control exposes [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] to Web developers through the ASP.NET data-source control architecture.</span></span>
