---
title: 编写实体框架数据提供程序
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 6c5e6e2859b48db6c982862381d223a4c9deb2c5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/04/2019
ms.locfileid: "70248193"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="e70e1-102">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="e70e1-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="e70e1-103">本节讨论如何编写[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序以支持除 SQL Server 之外的数据源。</span><span class="sxs-lookup"><span data-stu-id="e70e1-103">This section discusses how to write an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="e70e1-104">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]包括支持 SQL Server 的访问接口。</span><span class="sxs-lookup"><span data-stu-id="e70e1-104">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="e70e1-105">实体框架提供程序模型简介</span><span class="sxs-lookup"><span data-stu-id="e70e1-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="e70e1-106">[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]是独立于数据库的，您可以使用 ADO.NET 提供程序模型编写提供程序以连接到不同的数据源集。</span><span class="sxs-lookup"><span data-stu-id="e70e1-106">The [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="e70e1-107">实体框架数据提供程序（通过使用 ADO.NET 数据提供程序模型构建）具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="e70e1-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="e70e1-108">将实体数据模型 (EDM) 基元类型映射到提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="e70e1-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="e70e1-109">公开提供程序特定的函数。</span><span class="sxs-lookup"><span data-stu-id="e70e1-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="e70e1-110">为给定 DbQueryCommandTree 生成提供程序特定的命令以支持[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]查询。</span><span class="sxs-lookup"><span data-stu-id="e70e1-110">Generates provider-specific commands for a given DbQueryCommandTree to support [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] queries.</span></span>  
  
- <span data-ttu-id="e70e1-111">为给定 DbModificationCommandTree 生成提供程序特定的更新命令以支持[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]中的更新。</span><span class="sxs-lookup"><span data-stu-id="e70e1-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span>  
  
- <span data-ttu-id="e70e1-112">公开存储架构定义的映射文件以支持基于数据库的模型生成。</span><span class="sxs-lookup"><span data-stu-id="e70e1-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="e70e1-113">通过概念模型公开元数据（例如，表和视图）。</span><span class="sxs-lookup"><span data-stu-id="e70e1-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="e70e1-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="e70e1-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="e70e1-115">示例</span><span class="sxs-lookup"><span data-stu-id="e70e1-115">Sample</span></span>  
 <span data-ttu-id="e70e1-116">有关支持除 SQL Server 之外的数据源的[!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]提供程序的示例，请参阅[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)。</span><span class="sxs-lookup"><span data-stu-id="e70e1-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)] provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="e70e1-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="e70e1-117">In This Section</span></span>  
 [<span data-ttu-id="e70e1-118">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="e70e1-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="e70e1-119">修改 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="e70e1-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="e70e1-120">提供程序清单规范</span><span class="sxs-lookup"><span data-stu-id="e70e1-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="e70e1-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e70e1-121">See also</span></span>

- [<span data-ttu-id="e70e1-122">使用数据提供程序</span><span class="sxs-lookup"><span data-stu-id="e70e1-122">Working with Data Providers</span></span>](working-with-data-providers.md)
