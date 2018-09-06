---
title: 编写实体框架数据提供程序
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 50c0555d84c5b5f180c8c49a8419e8a414a4befe
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863396"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="80bc8-102">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="80bc8-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="80bc8-103">本部分讨论如何编写[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序以支持 SQL Server 以外的数据源。</span><span class="sxs-lookup"><span data-stu-id="80bc8-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="80bc8-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]包括支持 SQL Server 的提供程序。</span><span class="sxs-lookup"><span data-stu-id="80bc8-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="80bc8-105">实体框架提供程序模型简介</span><span class="sxs-lookup"><span data-stu-id="80bc8-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="80bc8-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]是独立于数据库的，您可以使用 ADO.NET 提供程序模型编写提供程序以连接到不同的数据源集。</span><span class="sxs-lookup"><span data-stu-id="80bc8-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="80bc8-107">实体框架数据提供程序（通过使用 ADO.NET 数据提供程序模型构建）具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="80bc8-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
-   <span data-ttu-id="80bc8-108">将实体数据模型 (EDM) 基元类型映射到提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="80bc8-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
-   <span data-ttu-id="80bc8-109">公开提供程序特定的函数。</span><span class="sxs-lookup"><span data-stu-id="80bc8-109">Exposes provider-specific functions.</span></span>  
  
-   <span data-ttu-id="80bc8-110">为给定 DbQueryCommandTree 生成提供程序特定的命令以支持[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="80bc8-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
-   <span data-ttu-id="80bc8-111">为给定 DbModificationCommandTree 生成提供程序特定的更新命令以支持[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中的更新。</span><span class="sxs-lookup"><span data-stu-id="80bc8-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
-   <span data-ttu-id="80bc8-112">公开存储架构定义的映射文件以支持基于数据库的模型生成。</span><span class="sxs-lookup"><span data-stu-id="80bc8-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
-   <span data-ttu-id="80bc8-113">通过概念模型公开元数据（例如，表和视图）。</span><span class="sxs-lookup"><span data-stu-id="80bc8-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="80bc8-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="80bc8-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](../../../../../docs/framework/data/adonet/ef/media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="80bc8-115">示例</span><span class="sxs-lookup"><span data-stu-id="80bc8-115">Sample</span></span>  
 <span data-ttu-id="80bc8-116">请参阅[实体框架示例提供程序](https://go.microsoft.com/fwlink/?LinkId=180616)有关的示例[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]支持 SQL Server 以外的数据源的提供程序。</span><span class="sxs-lookup"><span data-stu-id="80bc8-116">See the [Entity Framework Sample Provider](https://go.microsoft.com/fwlink/?LinkId=180616) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="80bc8-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="80bc8-117">In This Section</span></span>  
 [<span data-ttu-id="80bc8-118">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="80bc8-118">SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/sql-generation.md)  
  
 [<span data-ttu-id="80bc8-119">修改 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="80bc8-119">Modification SQL Generation</span></span>](../../../../../docs/framework/data/adonet/ef/modification-sql-generation.md)  
  
 [<span data-ttu-id="80bc8-120">提供程序清单规范</span><span class="sxs-lookup"><span data-stu-id="80bc8-120">Provider Manifest Specification</span></span>](../../../../../docs/framework/data/adonet/ef/provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="80bc8-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="80bc8-121">See Also</span></span>  
 [<span data-ttu-id="80bc8-122">使用数据提供程序</span><span class="sxs-lookup"><span data-stu-id="80bc8-122">Working with Data Providers</span></span>](../../../../../docs/framework/data/adonet/ef/working-with-data-providers.md)
