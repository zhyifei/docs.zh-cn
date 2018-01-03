---
title: "SQL Server 公共语言运行时集成"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: de415a6282b1d27d803d448bd3225355c08e011b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="95da7-102">SQL Server 公共语言运行时集成</span><span class="sxs-lookup"><span data-stu-id="95da7-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="95da7-103">SQL Server 2005 引入了 Microsoft Windows 的 .NET Framework 的公共语言运行库 (CLR) 组件的集成。</span><span class="sxs-lookup"><span data-stu-id="95da7-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="95da7-104">这意味着您可以使用任意 .NET Framework 语言（包括 Microsoft Visual Basic .NET 和 Microsoft Visual C#）编写存储过程、触发器、用户定义类型、用户定义函数、用户定义聚合函数以及流处理表值函数。</span><span class="sxs-lookup"><span data-stu-id="95da7-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="95da7-105"><xref:Microsoft.SqlServer.Server> 命名空间包含一组新的应用程序编程接口 (API)，使托管代码可以与 Microsoft SQL Server 环境交互。</span><span class="sxs-lookup"><span data-stu-id="95da7-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="95da7-106">本节介绍 SQL Server 公共语言运行库 (CLR) 集成特定的功能和行为以及 SQL Server 进程中专用的 ADO.NET 扩展。</span><span class="sxs-lookup"><span data-stu-id="95da7-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="95da7-107">本节只是为了提供足够的信息，以便开始使用 SQL Server CLR 集成编程，而并非为了提供完整的信息。</span><span class="sxs-lookup"><span data-stu-id="95da7-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="95da7-108">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="95da7-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="95da7-109">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="95da7-109">**SQL Server Books Online**</span></span>  
  
1.  [<span data-ttu-id="95da7-110">公共语言运行时 (CLR) 集成编程概念</span><span class="sxs-lookup"><span data-stu-id="95da7-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](http://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="95da7-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="95da7-111">In This Section</span></span>  
 [<span data-ttu-id="95da7-112">SQL Server CLR 集成简介</span><span class="sxs-lookup"><span data-stu-id="95da7-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="95da7-113">简介 SQL Server CLR 集成。</span><span class="sxs-lookup"><span data-stu-id="95da7-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="95da7-114">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="95da7-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="95da7-115">CLR 用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="95da7-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="95da7-116">描述如何实现和使用各种类型的 CLR 函数：表值函数、标量值函数以及用户定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="95da7-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="95da7-117">CLR 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="95da7-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="95da7-118">描述如何实现和使用 CLR 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="95da7-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="95da7-119">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="95da7-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="95da7-120">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="95da7-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="95da7-121">描述如何实现和使用 CLR 存储过程。</span><span class="sxs-lookup"><span data-stu-id="95da7-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="95da7-122">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="95da7-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="95da7-123">CLR 触发器</span><span class="sxs-lookup"><span data-stu-id="95da7-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="95da7-124">描述如何实现和使用 CLR 触发器。</span><span class="sxs-lookup"><span data-stu-id="95da7-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="95da7-125">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="95da7-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="95da7-126">上下文连接</span><span class="sxs-lookup"><span data-stu-id="95da7-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="95da7-127">介绍上下文连接。</span><span class="sxs-lookup"><span data-stu-id="95da7-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="95da7-128">ADO.NET 的 SQL Server 进程内特定行为</span><span class="sxs-lookup"><span data-stu-id="95da7-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="95da7-129">介绍 SQL Server 进程中专用的 ADO.NET 扩展以及上下文连接。</span><span class="sxs-lookup"><span data-stu-id="95da7-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="95da7-130">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="95da7-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="95da7-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="95da7-131">See Also</span></span>  
 [<span data-ttu-id="95da7-132">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="95da7-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)  
 [<span data-ttu-id="95da7-133">在托管代码中创建 SQL Server 2005 对象</span><span class="sxs-lookup"><span data-stu-id="95da7-133">Creating SQL Server 2005 Objects In Managed Code</span></span>](http://msdn.microsoft.com/en-us/5358a825-e19b-49aa-8214-674ce5fed1da)  
 [<span data-ttu-id="95da7-134">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="95da7-134">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
