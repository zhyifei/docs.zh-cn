---
title: "SQL Server 中的 CLR 集成安全性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 489fe096-fd1d-42de-8438-bf7aed46aea2
caps.latest.revision: "5"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: de4f4b1ae5ba252778d9463cba43a9ccb419600a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="clr-integration-security-in-sql-server"></a><span data-ttu-id="11a5e-102">SQL Server 中的 CLR 集成安全性</span><span class="sxs-lookup"><span data-stu-id="11a5e-102">CLR Integration Security in SQL Server</span></span>
<span data-ttu-id="11a5e-103">Microsoft SQL Server 提供 .NET Framework 的公共语言运行时 (CLR) 组件集成。</span><span class="sxs-lookup"><span data-stu-id="11a5e-103">Microsoft SQL Server provides the integration of the common language runtime (CLR) component of the .NET Framework.</span></span> <span data-ttu-id="11a5e-104">通过 CLR 集成，您可以使用任何 .NET Framework 语言（如 Microsoft Visual Basic .NET 或 Microsoft Visual C#）编写存储过程、触发器、用户定义的类型、用户定义的函数、用户定义的聚合以及流式表值函数。</span><span class="sxs-lookup"><span data-stu-id="11a5e-104">CLR integration allows you to write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, such as Microsoft Visual Basic .NET or Microsoft Visual C#.</span></span>  
  
 <span data-ttu-id="11a5e-105">CLR 支持一种用于托管代码的安全模型，称为代码访问安全性 (CAS)。</span><span class="sxs-lookup"><span data-stu-id="11a5e-105">The CLR supports a security model called code access security (CAS) for managed code.</span></span> <span data-ttu-id="11a5e-106">在此模型中，将根据元数据中代码提供的证据向程序集授予权限。</span><span class="sxs-lookup"><span data-stu-id="11a5e-106">In this model, permissions are granted to assemblies based on evidence supplied by the code in metadata.</span></span> <span data-ttu-id="11a5e-107">SQL Server 将 SQL Server 的基于用户的安全模型与 CLR 的基于代码启用的安全模型相集成。</span><span class="sxs-lookup"><span data-stu-id="11a5e-107">SQL Server integrates the user-based security model of SQL Server with the code access-based security model of the CLR.</span></span>  
  
## <a name="external-resources"></a><span data-ttu-id="11a5e-108">外部资源</span><span class="sxs-lookup"><span data-stu-id="11a5e-108">External Resources</span></span>  
 <span data-ttu-id="11a5e-109">有关 CLR 与 SQL Server 集成的更多信息，请参见下列资源。</span><span class="sxs-lookup"><span data-stu-id="11a5e-109">For more information on CLR integration with SQL Server, see the following resources.</span></span>  
  
|<span data-ttu-id="11a5e-110">资源</span><span class="sxs-lookup"><span data-stu-id="11a5e-110">Resource</span></span>|<span data-ttu-id="11a5e-111">描述</span><span class="sxs-lookup"><span data-stu-id="11a5e-111">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="11a5e-112">代码访问安全性</span><span class="sxs-lookup"><span data-stu-id="11a5e-112">Code Access Security</span></span>](http://msdn.microsoft.com/en-us/23a20143-241d-4fe5-9d9f-3933fd594c03)|<span data-ttu-id="11a5e-113">包含描述 .NET Framework 中 CAS 的主题。</span><span class="sxs-lookup"><span data-stu-id="11a5e-113">Contains topics describing CAS in the .NET Framework.</span></span>|  
|[<span data-ttu-id="11a5e-114">CLR 集成安全性</span><span class="sxs-lookup"><span data-stu-id="11a5e-114">CLR Integration Security</span></span>](http://go.microsoft.com/fwlink/?LinkId=59998)|<span data-ttu-id="11a5e-115">讨论在 SQL Server 内部执行的托管代码的安全模型。</span><span class="sxs-lookup"><span data-stu-id="11a5e-115">Discusses the security model for managed code executing inside of SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="11a5e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="11a5e-116">See Also</span></span>  
 [<span data-ttu-id="11a5e-117">保证 ADO.NET 应用程序的安全</span><span class="sxs-lookup"><span data-stu-id="11a5e-117">Securing ADO.NET Applications</span></span>](../../../../../docs/framework/data/adonet/securing-ado-net-applications.md)  
 [<span data-ttu-id="11a5e-118">SQL Server 中的应用程序安全方案</span><span class="sxs-lookup"><span data-stu-id="11a5e-118">Application Security Scenarios in SQL Server</span></span>](../../../../../docs/framework/data/adonet/sql/application-security-scenarios-in-sql-server.md)  
 [<span data-ttu-id="11a5e-119">SQL Server 公共语言运行时集成</span><span class="sxs-lookup"><span data-stu-id="11a5e-119">SQL Server Common Language Runtime Integration</span></span>](../../../../../docs/framework/data/adonet/sql/sql-server-common-language-runtime-integration.md)  
 [<span data-ttu-id="11a5e-120">ADO.NET 托管提供程序和数据集开发人员中心</span><span class="sxs-lookup"><span data-stu-id="11a5e-120">ADO.NET Managed Providers and DataSet Developer Center</span></span>](http://go.microsoft.com/fwlink/?LinkId=217917)
