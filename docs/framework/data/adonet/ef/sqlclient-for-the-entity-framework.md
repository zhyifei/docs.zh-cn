---
title: "用于实体框架的 SqlClient"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9a5d6d39-d955-43a5-a5c2-931c239398f1
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 3cb7880621a849b7162ea5f86ee0786f6184ea58
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="sqlclient-for-the-entity-framework"></a><span data-ttu-id="9c56e-102">用于实体框架的 SqlClient</span><span class="sxs-lookup"><span data-stu-id="9c56e-102">SqlClient for the Entity Framework</span></span>
<span data-ttu-id="9c56e-103">本节介绍用于 SQL Server (SqlClient) 的 .NET Framework 数据提供程序，该提供程序使实体框架能够在 Microsoft SQL Server 上工作。</span><span class="sxs-lookup"><span data-stu-id="9c56e-103">This section describes the .NET Framework Data Provider for SQL Server (SqlClient), which enables the Entity Framework to work over Microsoft SQL Server.</span></span>  
  
## <a name="provider-schema-attribute"></a><span data-ttu-id="9c56e-104">Provider 架构属性</span><span class="sxs-lookup"><span data-stu-id="9c56e-104">Provider Schema Attribute</span></span>  
 <span data-ttu-id="9c56e-105">`Provider` 是以存储架构定义语言 (SSDL) 表示的 `Schema` 元素的一个特性。</span><span class="sxs-lookup"><span data-stu-id="9c56e-105">`Provider` is an attribute of the `Schema` element in store schema definition language (SSDL).</span></span>  
  
 <span data-ttu-id="9c56e-106">若要使用 SqlClient，请将字符串“System.Data.SqlClient”分配给 `Provider` 元素的 `Schema` 属性。</span><span class="sxs-lookup"><span data-stu-id="9c56e-106">To use SqlClient, assign the string "System.Data.SqlClient" to the `Provider` attribute of the `Schema` element.</span></span>  
  
## <a name="providermanifesttoken-schema-attribute"></a><span data-ttu-id="9c56e-107">ProviderManifestToken 架构属性</span><span class="sxs-lookup"><span data-stu-id="9c56e-107">ProviderManifestToken Schema Attribute</span></span>  
 <span data-ttu-id="9c56e-108">`ProviderManifestToken` 是以 SSDL 表示的 `Schema` 元素的一个必需特性。</span><span class="sxs-lookup"><span data-stu-id="9c56e-108">`ProviderManifestToken` is a required attribute of the `Schema` element in SSDL.</span></span> <span data-ttu-id="9c56e-109">此标记用于为脱机方案加载提供程序清单。</span><span class="sxs-lookup"><span data-stu-id="9c56e-109">This token is used to load the provider manifest for offline scenarios.</span></span> <span data-ttu-id="9c56e-110">有关详细信息`ProviderManifestToken`属性，请参阅[架构元素 (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222)。</span><span class="sxs-lookup"><span data-stu-id="9c56e-110">For more information about `ProviderManifestToken` attribute, see [Schema Element (SSDL)](http://msdn.microsoft.com/en-us/fec75ae4-7f16-4421-9265-9dac61509222).</span></span>  
  
 <span data-ttu-id="9c56e-111">SqlClient 可以用作不同版本 [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)] 的数据提供程序。</span><span class="sxs-lookup"><span data-stu-id="9c56e-111">SqlClient can be used as a data provider for different versions of [!INCLUDE[ssNoVersion](../../../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9c56e-112">这些版本具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="9c56e-112">These versions have different capabilities.</span></span> <span data-ttu-id="9c56e-113">例如，[!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] 不支持在 `varchar(max)` 中引入的 `nvarchar(max)` 和 [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)] 类型。</span><span class="sxs-lookup"><span data-stu-id="9c56e-113">For example, [!INCLUDE[ssVersion2000](../../../../../includes/ssversion2000-md.md)] does not support `varchar(max)` and `nvarchar(max)` types that were introduced with [!INCLUDE[ssVersion2005](../../../../../includes/ssversion2005-md.md)].</span></span>  
  
 <span data-ttu-id="9c56e-114">针对不同版本的 SQL Server，SqlClient 生成和接受以下提供程序清单标记。</span><span class="sxs-lookup"><span data-stu-id="9c56e-114">SqlClient produces and accepts the following provider manifest tokens for different versions of SQL Server.</span></span>  
  
|<span data-ttu-id="9c56e-115">SQL Server 2000</span><span class="sxs-lookup"><span data-stu-id="9c56e-115">SQL Server 2000</span></span>|<span data-ttu-id="9c56e-116">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="9c56e-116">SQL Server 2005</span></span>|<span data-ttu-id="9c56e-117">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9c56e-117">SQL Server 2008</span></span>|  
|-|-|-|  
|<span data-ttu-id="9c56e-118">2000</span><span class="sxs-lookup"><span data-stu-id="9c56e-118">2000</span></span>|<span data-ttu-id="9c56e-119">2005</span><span class="sxs-lookup"><span data-stu-id="9c56e-119">2005</span></span>|<span data-ttu-id="9c56e-120">2008</span><span class="sxs-lookup"><span data-stu-id="9c56e-120">2008</span></span>|  
  
> [!NOTE]
>  <span data-ttu-id="9c56e-121">从开始[!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)]2010， [ADO.NET 实体数据模型工具](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527)不支持 SQL Server 2000。</span><span class="sxs-lookup"><span data-stu-id="9c56e-121">Starting with [!INCLUDE[vsprvs](../../../../../includes/vsprvs-md.md)] 2010, the [ADO.NET Entity Data Model  Tools](http://msdn.microsoft.com/en-us/91076853-0881-421b-837a-f582f36be527) do not support SQL Server 2000.</span></span>  
  
## <a name="provider-namespace-name"></a><span data-ttu-id="9c56e-122">提供程序命名空间名称</span><span class="sxs-lookup"><span data-stu-id="9c56e-122">Provider Namespace Name</span></span>  
 <span data-ttu-id="9c56e-123">所有提供程序都必须指定一个命名空间。</span><span class="sxs-lookup"><span data-stu-id="9c56e-123">All providers must specify a namespace.</span></span> <span data-ttu-id="9c56e-124">实体框架通过此属性获知提供程序为特定构造（如类型和函数）使用哪个前缀。</span><span class="sxs-lookup"><span data-stu-id="9c56e-124">This property tells the Entity Framework which prefix is used by the provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="9c56e-125">SqlClient 提供程序清单的命名空间为 `SqlServer`。</span><span class="sxs-lookup"><span data-stu-id="9c56e-125">The namespace for SqlClient provider manifests is `SqlServer`.</span></span> <span data-ttu-id="9c56e-126">有关命名空间的详细信息，请参阅[命名空间](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md)。</span><span class="sxs-lookup"><span data-stu-id="9c56e-126">For more information about namespaces, see [Namespaces](../../../../../docs/framework/data/adonet/ef/language-reference/namespaces-entity-sql.md).</span></span>  
  
## <a name="types"></a><span data-ttu-id="9c56e-127">类型</span><span class="sxs-lookup"><span data-stu-id="9c56e-127">Types</span></span>  
 <span data-ttu-id="9c56e-128">实体框架的 SqlClient 提供程序提供概念模型类型与 SQL Server 类型之间的映射信息。</span><span class="sxs-lookup"><span data-stu-id="9c56e-128">The SqlClient provider for the Entity Framework provides mapping information between conceptual model types and SQL Server types.</span></span> <span data-ttu-id="9c56e-129">有关详细信息，请参阅[实体 FrameworkTypes 的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)。</span><span class="sxs-lookup"><span data-stu-id="9c56e-129">For more information, see [SqlClient for Entity FrameworkTypes](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md).</span></span>  
  
## <a name="functions"></a><span data-ttu-id="9c56e-130">函数</span><span class="sxs-lookup"><span data-stu-id="9c56e-130">Functions</span></span>  
 <span data-ttu-id="9c56e-131">实体框架的 SqlClient 提供程序定义提供程序支持的函数列表。</span><span class="sxs-lookup"><span data-stu-id="9c56e-131">The SqlClient provider for the Entity Framework defines the list of functions supported by the provider.</span></span> <span data-ttu-id="9c56e-132">有关受支持的函数的列表，请参阅[用于实体框架函数的 SqlClient](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)。</span><span class="sxs-lookup"><span data-stu-id="9c56e-132">For a list of the supported functions, see [SqlClient for Entity Framework Functions](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9c56e-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="9c56e-133">In This Section</span></span>  
 [<span data-ttu-id="9c56e-134">用于实体框架函数的 SqlClient</span><span class="sxs-lookup"><span data-stu-id="9c56e-134">SqlClient for Entity Framework Functions</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)  
  
 [<span data-ttu-id="9c56e-135">用于实体 FrameworkTypes 的 SqlClient</span><span class="sxs-lookup"><span data-stu-id="9c56e-135">SqlClient for Entity FrameworkTypes</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-types.md)  
  
 [<span data-ttu-id="9c56e-136">用于实体框架的 SqlClient 中的已知的问题</span><span class="sxs-lookup"><span data-stu-id="9c56e-136">Known Issues in SqlClient for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/known-issues-in-sqlclient-for-entity-framework.md)  
  
## <a name="see-also"></a><span data-ttu-id="9c56e-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9c56e-137">See Also</span></span>  
 [<span data-ttu-id="9c56e-138">实体 SQL 语言</span><span class="sxs-lookup"><span data-stu-id="9c56e-138">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)  
 [<span data-ttu-id="9c56e-139">语言参考</span><span class="sxs-lookup"><span data-stu-id="9c56e-139">Language Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/index.md)  
 [<span data-ttu-id="9c56e-140">用于实体框架的 SqlClient 提供程序中的已知问题</span><span class="sxs-lookup"><span data-stu-id="9c56e-140">Known Issues in SqlClient Provider for Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/sqlclient-for-the-entity-framework.md)
