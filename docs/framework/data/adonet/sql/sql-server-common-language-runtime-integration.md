---
title: SQL Server 公共语言运行时集成
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 77b40c6a1576b87d9bb4a7eb4b1ee3df8828b892
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780858"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="40073-102">SQL Server 公共语言运行时集成</span><span class="sxs-lookup"><span data-stu-id="40073-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="40073-103">SQL Server 2005 引入了 Microsoft Windows 的 .NET Framework 的公共语言运行库 (CLR) 组件的集成。</span><span class="sxs-lookup"><span data-stu-id="40073-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="40073-104">这意味着您可以使用任意 .NET Framework 语言（包括 Microsoft Visual Basic .NET 和 Microsoft Visual C#）编写存储过程、触发器、用户定义类型、用户定义函数、用户定义聚合函数以及流处理表值函数。</span><span class="sxs-lookup"><span data-stu-id="40073-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="40073-105"><xref:Microsoft.SqlServer.Server> 命名空间包含一组新的应用程序编程接口 (API)，使托管代码可以与 Microsoft SQL Server 环境交互。</span><span class="sxs-lookup"><span data-stu-id="40073-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="40073-106">本节介绍 SQL Server 公共语言运行库 (CLR) 集成特定的功能和行为以及 SQL Server 进程中专用的 ADO.NET 扩展。</span><span class="sxs-lookup"><span data-stu-id="40073-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="40073-107">本节只是为了提供足够的信息，以便开始使用 SQL Server CLR 集成编程，而并非为了提供完整的信息。</span><span class="sxs-lookup"><span data-stu-id="40073-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="40073-108">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="40073-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="40073-109">**SQL Server 联机丛书**</span><span class="sxs-lookup"><span data-stu-id="40073-109">**SQL Server Books Online**</span></span>  
  
1. [<span data-ttu-id="40073-110">公共语言运行时（CLR）集成编程概念</span><span class="sxs-lookup"><span data-stu-id="40073-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](https://go.microsoft.com/fwlink/?LinkId=115240)  
  
## <a name="in-this-section"></a><span data-ttu-id="40073-111">本节内容</span><span class="sxs-lookup"><span data-stu-id="40073-111">In This Section</span></span>  
 [<span data-ttu-id="40073-112">SQL Server CLR 集成简介</span><span class="sxs-lookup"><span data-stu-id="40073-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="40073-113">简介 SQL Server CLR 集成。</span><span class="sxs-lookup"><span data-stu-id="40073-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="40073-114">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="40073-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="40073-115">CLR 用户定义的函数</span><span class="sxs-lookup"><span data-stu-id="40073-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="40073-116">描述如何实现和使用各种类型的 CLR 函数：表值函数、标量值函数以及用户定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="40073-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="40073-117">CLR 用户定义的类型</span><span class="sxs-lookup"><span data-stu-id="40073-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="40073-118">描述如何实现和使用 CLR 用户定义类型。</span><span class="sxs-lookup"><span data-stu-id="40073-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="40073-119">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="40073-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="40073-120">CLR 存储过程</span><span class="sxs-lookup"><span data-stu-id="40073-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="40073-121">描述如何实现和使用 CLR 存储过程。</span><span class="sxs-lookup"><span data-stu-id="40073-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="40073-122">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="40073-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="40073-123">CLR 触发器</span><span class="sxs-lookup"><span data-stu-id="40073-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="40073-124">描述如何实现和使用 CLR 触发器。</span><span class="sxs-lookup"><span data-stu-id="40073-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="40073-125">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="40073-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="40073-126">上下文连接</span><span class="sxs-lookup"><span data-stu-id="40073-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="40073-127">介绍上下文连接。</span><span class="sxs-lookup"><span data-stu-id="40073-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="40073-128">ADO.NET 的 SQL Server 进程内特定行为</span><span class="sxs-lookup"><span data-stu-id="40073-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="40073-129">介绍 SQL Server 进程中专用的 ADO.NET 扩展以及上下文连接。</span><span class="sxs-lookup"><span data-stu-id="40073-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="40073-130">提供指向其他主题的链接。</span><span class="sxs-lookup"><span data-stu-id="40073-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40073-131">请参阅</span><span class="sxs-lookup"><span data-stu-id="40073-131">See also</span></span>

- [<span data-ttu-id="40073-132">SQL Server 和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="40073-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="40073-133">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="40073-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
