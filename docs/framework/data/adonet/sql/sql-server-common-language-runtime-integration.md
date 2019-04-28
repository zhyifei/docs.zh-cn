---
title: SQL Server 公共语言运行时集成
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: fd043aa6c7e5b9246a36146e000e5cba9e090d3e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61876338"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="af15a-102">SQL Server 公共语言运行时集成</span><span class="sxs-lookup"><span data-stu-id="af15a-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="af15a-103">SQL Server 2005 引入了 Microsoft Windows 的 .NET Framework 的公共语言运行库 (CLR) 组件的集成。</span><span class="sxs-lookup"><span data-stu-id="af15a-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="af15a-104">这意味着您可以使用任意 .NET Framework 语言（包括 Microsoft Visual Basic .NET 和 Microsoft Visual C#）编写存储过程、触发器、用户定义类型、用户定义函数、用户定义聚合函数以及流处理表值函数。</span><span class="sxs-lookup"><span data-stu-id="af15a-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="af15a-105"><xref:Microsoft.SqlServer.Server> 命名空间包含一组新的应用程序编程接口 (API)，使托管代码可以与 Microsoft SQL Server 环境交互。</span><span class="sxs-lookup"><span data-stu-id="af15a-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="af15a-106">本节介绍 SQL Server 公共语言运行库 (CLR) 集成特定的功能和行为以及 SQL Server 进程中专用的 ADO.NET 扩展。</span><span class="sxs-lookup"><span data-stu-id="af15a-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="af15a-107">本节只是为了提供足够的信息，以便开始使用 SQL Server CLR 集成编程，而并非为了提供完整的信息。</span><span class="sxs-lookup"><span data-stu-id="af15a-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="af15a-108">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="af15a-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="af15a-109">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="af15a-109">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="af15a-110">公共语言运行时 (CLR) 集成编程概念</span><span class="sxs-lookup"><span data-stu-id="af15a-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="af15a-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="af15a-111">In This Section</span></span>  
 [<span data-ttu-id="af15a-112">SQL Server CLR 集成简介</span><span class="sxs-lookup"><span data-stu-id="af15a-112">Introduction to SQL Server CLR Integration</span></span>](../../../../../docs/framework/data/adonet/sql/introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="af15a-113">简介 SQL Server CLR 集成。</span><span class="sxs-lookup"><span data-stu-id="af15a-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="af15a-114">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="af15a-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="af15a-115">CLR 用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="af15a-115">CLR User-Defined Functions</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-functions.md)  
 <span data-ttu-id="af15a-116">描述如何实现和使用各种类型的 CLR 函数：表值函数、标量值函数以及用户定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="af15a-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="af15a-117">CLR 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="af15a-117">CLR User-Defined Types</span></span>](../../../../../docs/framework/data/adonet/sql/clr-user-defined-types.md)  
 <span data-ttu-id="af15a-118">描述如何实现和使用 CLR 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="af15a-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="af15a-119">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="af15a-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="af15a-120">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="af15a-120">CLR Stored Procedures</span></span>](../../../../../docs/framework/data/adonet/sql/clr-stored-procedures.md)  
 <span data-ttu-id="af15a-121">描述如何实现和使用 CLR 存储过程。</span><span class="sxs-lookup"><span data-stu-id="af15a-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="af15a-122">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="af15a-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="af15a-123">CLR 触发器</span><span class="sxs-lookup"><span data-stu-id="af15a-123">CLR Triggers</span></span>](../../../../../docs/framework/data/adonet/sql/clr-triggers.md)  
 <span data-ttu-id="af15a-124">描述如何实现和使用 CLR 触发器。</span><span class="sxs-lookup"><span data-stu-id="af15a-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="af15a-125">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="af15a-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="af15a-126">上下文连接</span><span class="sxs-lookup"><span data-stu-id="af15a-126">The Context Connection</span></span>](../../../../../docs/framework/data/adonet/sql/the-context-connection.md)  
 <span data-ttu-id="af15a-127">介绍上下文连接。</span><span class="sxs-lookup"><span data-stu-id="af15a-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="af15a-128">ADO.NET 的 SQL Server 进程内特定行为</span><span class="sxs-lookup"><span data-stu-id="af15a-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="af15a-129">介绍 SQL Server 进程中专用的 ADO.NET 扩展以及上下文连接。</span><span class="sxs-lookup"><span data-stu-id="af15a-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="af15a-130">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="af15a-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af15a-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="af15a-131">See also</span></span>

- [<span data-ttu-id="af15a-132">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="af15a-132">SQL Server and ADO.NET</span></span>](../../../../../docs/framework/data/adonet/sql/index.md)
- [<span data-ttu-id="af15a-133">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="af15a-133">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
