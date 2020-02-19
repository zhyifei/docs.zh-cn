---
title: SQL Server CLR 集成简介
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 41dd89af4f45c673cf6b7283fc39aaf91fd9963c
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452404"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="939da-102">SQL Server CLR 集成简介</span><span class="sxs-lookup"><span data-stu-id="939da-102">Introduction to SQL Server CLR Integration</span></span>
<span data-ttu-id="939da-103">公共语言运行库 (CLR) 是 Microsoft .NET Framework 的核心，为所有 .NET Framework 代码提供执行环境。</span><span class="sxs-lookup"><span data-stu-id="939da-103">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="939da-104">在 CLR 中运行的代码称为托管代码。</span><span class="sxs-lookup"><span data-stu-id="939da-104">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="939da-105">CLR 提供执行程序所需的各种函数和服务，包括实时 (JIT) 编译、分配和管理内存、强制类型安全性、异常处理、线程管理和安全性。</span><span class="sxs-lookup"><span data-stu-id="939da-105">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="939da-106">通过在 Microsoft SQL Server 中托管 CLR（称为 CLR 集成），可以在托管代码中编写存储过程、触发器、用户定义函数、用户定义类型和用户定义聚合函数。</span><span class="sxs-lookup"><span data-stu-id="939da-106">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="939da-107">因为托管代码在执行之前会编译为本机代码，所以，在有些方案中可以大大提高性能。</span><span class="sxs-lookup"><span data-stu-id="939da-107">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="939da-108">托管代码使用代码访问安全性 (CAS)、代码链接和应用程序域来阻止程序集执行某些操作。</span><span class="sxs-lookup"><span data-stu-id="939da-108">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="939da-109">SQL Server 使用 CAS 来帮助保证托管代码的安全，并避免操作系统或数据库服务器受到威胁。</span><span class="sxs-lookup"><span data-stu-id="939da-109">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="939da-110">本节只是为了提供足够的信息，以便开始使用 SQL Server CLR 集成编程，而并非为了提供完整的信息。</span><span class="sxs-lookup"><span data-stu-id="939da-110">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="939da-111">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="939da-111">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="939da-112">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="939da-112">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="939da-113">公共语言运行时 (CLR) 集成概述</span><span class="sxs-lookup"><span data-stu-id="939da-113">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="939da-114">启用 CLR 集成</span><span class="sxs-lookup"><span data-stu-id="939da-114">Enabling CLR Integration</span></span>  
 <span data-ttu-id="939da-115">默认情况下，Microsoft SQL Server 中禁用公共语言运行库 (CLR) 集成功能，必须启用才能使用通过 CLR 集成实现的对象。</span><span class="sxs-lookup"><span data-stu-id="939da-115">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="939da-116">要使用 Transact-SQL 启用 CLR 集成，请使用如下所示的 `clr enabled` 存储过程的 `sp_configure` 选项：</span><span class="sxs-lookup"><span data-stu-id="939da-116">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="939da-117">可以通过将 `clr enabled` 选项设置为 0 来禁用 CLR 集成。</span><span class="sxs-lookup"><span data-stu-id="939da-117">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="939da-118">在禁用 CLR 集成时，SQL Server 停止执行所有 CLR 例程并卸载所有应用程序域。</span><span class="sxs-lookup"><span data-stu-id="939da-118">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="939da-119">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="939da-119">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="939da-120">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="939da-120">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="939da-121">启用 CLR 集成</span><span class="sxs-lookup"><span data-stu-id="939da-121">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="939da-122">部署 CLR 程序集</span><span class="sxs-lookup"><span data-stu-id="939da-122">Deploying a CLR Assembly</span></span>  
 <span data-ttu-id="939da-123">在测试服务器上测试和验证 CLR 方法后，可以使用部署脚本将其分发到生产服务器。</span><span class="sxs-lookup"><span data-stu-id="939da-123">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="939da-124">部署脚本可以通过手动或使用 SQL Server Management Studio 生成。</span><span class="sxs-lookup"><span data-stu-id="939da-124">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="939da-125">有关更多详细信息，请参阅所使用 SQL Server 版本的 SQL Server 文档版本。</span><span class="sxs-lookup"><span data-stu-id="939da-125">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="939da-126">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="939da-126">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="939da-127">部署 CLR 数据库对象</span><span class="sxs-lookup"><span data-stu-id="939da-127">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="939da-128">CLR 集成安全性</span><span class="sxs-lookup"><span data-stu-id="939da-128">CLR Integration Security</span></span>  
 <span data-ttu-id="939da-129">Microsoft SQL Server 与 Microsoft .NET Framework 公共语言运行库 (CLR) 相集成，这种安全模型可管理和保护 SQL Server 中运行的不同类型 CLR 和非 CLR 对象之间的访问。</span><span class="sxs-lookup"><span data-stu-id="939da-129">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="939da-130">这些对象可以通过 Transact-SQL 语句或服务器中运行的其他 CLR 对象进行调用。</span><span class="sxs-lookup"><span data-stu-id="939da-130">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="939da-131">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="939da-131">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="939da-132">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="939da-132">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="939da-133">CLR 集成安全性</span><span class="sxs-lookup"><span data-stu-id="939da-133">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="939da-134">调试 CLR 程序集</span><span class="sxs-lookup"><span data-stu-id="939da-134">Debugging a CLR Assembly</span></span>  
 <span data-ttu-id="939da-135">Microsoft SQL Server 支持调试数据库中的 Transact-SQL 和公共语言运行库 (CLR) 对象。</span><span class="sxs-lookup"><span data-stu-id="939da-135">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="939da-136">跨语言调试工作：用户可以从 Transact-SQL 无缝地进入并单步执行 CLR 对象，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="939da-136">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="939da-137">有关更多详细信息，请参见您正在使用的 SQL Server 版本的“SQL Server 联机丛书”版本。</span><span class="sxs-lookup"><span data-stu-id="939da-137">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="939da-138">**SQL Server 文档**</span><span class="sxs-lookup"><span data-stu-id="939da-138">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="939da-139">调试 CLR 数据库对象</span><span class="sxs-lookup"><span data-stu-id="939da-139">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="939da-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="939da-140">See also</span></span>

- [<span data-ttu-id="939da-141">代码访问安全性和 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="939da-141">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="939da-142">ADO.NET 概述</span><span class="sxs-lookup"><span data-stu-id="939da-142">ADO.NET Overview</span></span>](../ado-net-overview.md)
