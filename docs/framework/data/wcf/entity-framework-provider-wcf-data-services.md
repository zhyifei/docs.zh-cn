---
title: "实体框架提供程序（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: f2ce54596cbfebd1a4b0a81819b34c6ffcddfb88
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="entity-framework-provider-wcf-data-services"></a><span data-ttu-id="d3d7d-102">实体框架提供程序（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="d3d7d-102">Entity Framework Provider (WCF Data Services)</span></span>
<span data-ttu-id="d3d7d-103">与 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 类似，ADO.NET 实体框架也基于实体数据模型（一种实体关系模型）。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-103">Like [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], the ADO.NET Entity Framework is based on the Entity Data Model, which is a type of entity-relationship model.</span></span> <span data-ttu-id="d3d7d-104">实体框架将针对实体数据模型中，调用其实现*概念模型*，转换为针对数据源的等效操作。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-104">The Entity Framework translates operations against its implementation of the Entity Data Model, which is called the *conceptual model*, into equivalent operations against a data source.</span></span> <span data-ttu-id="d3d7d-105">这使实体框架成为基于关系数据的数据服务的理想提供程序，任何具有支持实体框架的数据提供程序的数据库都可用于 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-105">This makes the Entity Framework an ideal provider for data services that are based on relational data, and any database that has a data provider that supports the Entity Framework can be used with [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span> <span data-ttu-id="d3d7d-106">有关当前支持实体框架的数据源的列表，请参阅[用于实体框架的第三方提供商](http://go.microsoft.com/fwlink/?LinkId=143699)。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-106">For a list of the data sources that currently support the Entity Framework, see [Third-Party Providers for the Entity Framework](http://go.microsoft.com/fwlink/?LinkId=143699).</span></span>  
  
 <span data-ttu-id="d3d7d-107">在概念模型中，实体容器是服务的根。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-107">In a conceptual model, the entity container is the root of the service.</span></span> <span data-ttu-id="d3d7d-108">必须先在实体框架中定义一个概念模型，数据服务才能公开数据。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-108">You must define a conceptual model in the Entity Framework before the data can be exposed by a data service.</span></span> <span data-ttu-id="d3d7d-109">有关详细信息，请参阅[如何： 创建数据服务使用 ADO.NET 实体框架数据源](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-109">For more information, see [How to: Create a Data Service Using an ADO.NET Entity Framework Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).</span></span>  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="d3d7d-110">支持开放式并发模型，使您能够定义并发标记的实体。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-110"> supports the optimistic concurrency model by enabling you to define a concurrency token for an entity.</span></span> <span data-ttu-id="d3d7d-111">这样一个包含一个或多个实体属性的并发标记由数据服务用来确定，正在请求、更新或删除的数据中是否发生了更改。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-111">This concurrency token, which includes one or more properties of the entity, is used by the data service to determine whether a change has occurred in the data that is being requested, updated, or deleted.</span></span> <span data-ttu-id="d3d7d-112">如果从请求的 eTag 中获取的标记值与实体的当前值不相同，则数据服务将引发异常。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-112">When token values obtained from the eTag in the request differ from the current values of the entity, an exception is raised by the data service.</span></span> <span data-ttu-id="d3d7d-113">若要指示某个属性为并发标记的一部分，必须在`ConcurrencyMode="Fixed"`提供程序所定义的数据模型中应用 [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] 特性。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-113">To indicate that a property is part of the concurrency token, you must apply the attribute `ConcurrencyMode="Fixed"` in the data model defined by the [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)] provider.</span></span> <span data-ttu-id="d3d7d-114">并发标记不能包含键属性或导航属性。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-114">The concurrency token cannot include a key property or a navigation property.</span></span> <span data-ttu-id="d3d7d-115">有关详细信息，请参阅[更新数据服务](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-115">For more information, see [Updating the Data Service](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="d3d7d-116">若要了解有关实体框架的详细信息，请参阅[实体框架概述](../../../../docs/framework/data/adonet/ef/overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d3d7d-116">To learn more about the Entity Framework, see [Entity Framework Overview](../../../../docs/framework/data/adonet/ef/overview.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3d7d-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d3d7d-117">See Also</span></span>  
 [<span data-ttu-id="d3d7d-118">数据服务提供程序</span><span class="sxs-lookup"><span data-stu-id="d3d7d-118">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="d3d7d-119">反射提供程序</span><span class="sxs-lookup"><span data-stu-id="d3d7d-119">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)  
 [<span data-ttu-id="d3d7d-120">实体数据模型</span><span class="sxs-lookup"><span data-stu-id="d3d7d-120">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
