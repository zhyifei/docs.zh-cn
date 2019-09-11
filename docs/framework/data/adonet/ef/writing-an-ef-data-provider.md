---
title: 编写实体框架数据提供程序
ms.date: 03/30/2017
ms.assetid: 092e88c4-a301-453a-b5c3-5740c6575a9f
ms.openlocfilehash: 29aa8cb1c6b31d9ada6b01860d76bcf03d37416c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854158"
---
# <a name="writing-an-entity-framework-data-provider"></a><span data-ttu-id="965dd-102">编写实体框架数据提供程序</span><span class="sxs-lookup"><span data-stu-id="965dd-102">Writing an Entity Framework Data Provider</span></span>
<span data-ttu-id="965dd-103">本部分讨论如何编写实体框架提供程序以支持除 SQL Server 之外的数据源。</span><span class="sxs-lookup"><span data-stu-id="965dd-103">This section discusses how to write an Entity Framework provider to support a data source other than SQL Server.</span></span> <span data-ttu-id="965dd-104">实体框架包含支持 SQL Server 的访问接口。</span><span class="sxs-lookup"><span data-stu-id="965dd-104">The Entity Framework includes a provider that supports SQL Server.</span></span>  
  
## <a name="introducing-the-entity-framework-provider-model"></a><span data-ttu-id="965dd-105">实体框架提供程序模型简介</span><span class="sxs-lookup"><span data-stu-id="965dd-105">Introducing the Entity Framework Provider Model</span></span>  
 <span data-ttu-id="965dd-106">实体框架是独立于数据库的，你可以使用 ADO.NET 提供程序模型来编写提供程序，以便连接到一组不同的数据源。</span><span class="sxs-lookup"><span data-stu-id="965dd-106">The Entity Framework is database independent, and you can write a provider by using the ADO.NET Provider Model to connect to a diverse set of data sources.</span></span>  
  
 <span data-ttu-id="965dd-107">实体框架数据提供程序（通过使用 ADO.NET 数据提供程序模型构建）具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="965dd-107">The Entity Framework data provider (built using the ADO.NET Data Provider model) performs the following functions:</span></span>  
  
- <span data-ttu-id="965dd-108">将实体数据模型 (EDM) 基元类型映射到提供程序类型。</span><span class="sxs-lookup"><span data-stu-id="965dd-108">Maps Entity Data Model (EDM) primitive types to provider types.</span></span>  
  
- <span data-ttu-id="965dd-109">公开提供程序特定的函数。</span><span class="sxs-lookup"><span data-stu-id="965dd-109">Exposes provider-specific functions.</span></span>  
  
- <span data-ttu-id="965dd-110">为给定的 DbQueryCommandTree 生成特定于提供程序的命令，以支持实体框架查询。</span><span class="sxs-lookup"><span data-stu-id="965dd-110">Generates provider-specific commands for a given DbQueryCommandTree to support Entity Framework queries.</span></span>  
  
- <span data-ttu-id="965dd-111">为给定 DbModificationCommandTree 生成特定于提供程序的更新命令，以支持通过实体框架更新。</span><span class="sxs-lookup"><span data-stu-id="965dd-111">Generates provider-specific update commands for a given DbModificationCommandTree to support updates through the Entity Framework.</span></span>  
  
- <span data-ttu-id="965dd-112">公开存储架构定义的映射文件以支持基于数据库的模型生成。</span><span class="sxs-lookup"><span data-stu-id="965dd-112">Exposes mapping files for the store schema definition, to support generation of a model based on a database.</span></span>  
  
- <span data-ttu-id="965dd-113">通过概念模型公开元数据（例如，表和视图）。</span><span class="sxs-lookup"><span data-stu-id="965dd-113">Exposes metadata (tables and views, for example) via a conceptual model.</span></span>  
  
 <span data-ttu-id="965dd-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span><span class="sxs-lookup"><span data-stu-id="965dd-114">![b42a7a5c&#45;0ac0&#45;4911&#45;86be&#45;0460a78760ba](./media/b42a7a5c-0ac0-4911-86be-0460a78760ba.gif "b42a7a5c-0ac0-4911-86be-0460a78760ba")</span></span>  
  
## <a name="sample"></a><span data-ttu-id="965dd-115">示例</span><span class="sxs-lookup"><span data-stu-id="965dd-115">Sample</span></span>  
 <span data-ttu-id="965dd-116">有关支持除 SQL Server 之外的数据源的实体框架提供程序的示例，请参阅[实体框架示例提供程序](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0)。</span><span class="sxs-lookup"><span data-stu-id="965dd-116">See the [Entity Framework Sample Provider](https://code.msdn.microsoft.com/windowsdesktop/Entity-Framework-Sample-6a9801d0) for a sample of an Entity Framework provider that supports a data source other than SQL Server.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="965dd-117">本节内容</span><span class="sxs-lookup"><span data-stu-id="965dd-117">In This Section</span></span>  
 [<span data-ttu-id="965dd-118">SQL 生成</span><span class="sxs-lookup"><span data-stu-id="965dd-118">SQL Generation</span></span>](sql-generation.md)  
  
 [<span data-ttu-id="965dd-119">修改 SQL 生成</span><span class="sxs-lookup"><span data-stu-id="965dd-119">Modification SQL Generation</span></span>](modification-sql-generation.md)  
  
 [<span data-ttu-id="965dd-120">提供程序清单规范</span><span class="sxs-lookup"><span data-stu-id="965dd-120">Provider Manifest Specification</span></span>](provider-manifest-specification.md)  
  
## <a name="see-also"></a><span data-ttu-id="965dd-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="965dd-121">See also</span></span>

- [<span data-ttu-id="965dd-122">使用数据提供程序</span><span class="sxs-lookup"><span data-stu-id="965dd-122">Working with Data Providers</span></span>](working-with-data-providers.md)
