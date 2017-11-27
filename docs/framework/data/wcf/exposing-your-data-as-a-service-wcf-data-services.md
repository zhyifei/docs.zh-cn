---
title: "将数据公开为服务（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
- getting started, WCF Data Services
- WCF Data Services, getting started
ms.assetid: df0bbcee-f66f-4a88-abb4-4e73c8b9c908
caps.latest.revision: "2"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 122d05d5e4bd7690f32b22453dccbfaab2fb7f13
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-your-data-as-a-service-wcf-data-services"></a><span data-ttu-id="1c726-102">将数据公开为服务（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="1c726-102">Exposing Your Data as a Service (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="1c726-103">与 Visual Studio 使你能够更轻松地定义服务以公开你的数据作为集成[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]馈送。</span><span class="sxs-lookup"><span data-stu-id="1c726-103"> integrates with Visual Studio to enable you to more easily define services to expose your data as [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feeds.</span></span> <span data-ttu-id="1c726-104">创建数据服务公开[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源涉及以下基本步骤：</span><span class="sxs-lookup"><span data-stu-id="1c726-104">Creating a data service that exposes an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed involves the following basic steps:</span></span>  
  
1.  <span data-ttu-id="1c726-105">**定义****数据模型**。</span><span class="sxs-lookup"><span data-stu-id="1c726-105">**Define** **the data model**.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="1c726-106">以本机方式支持数据模型在基于[ADO.NET 实体框架](../../../../docs/framework/data/adonet/ef/index.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-106"> natively supports data models that are based on the [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md).</span></span> <span data-ttu-id="1c726-107">有关详细信息，请参阅[如何： 创建数据服务使用 ADO.NET 实体框架数据源](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-107">For more information, see [How to: Create a Data Service Using an ADO.NET Entity Framework Data Source](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).</span></span>  
  
     [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="1c726-108"> 还支持基于公共语言运行时 (CLR) 对象的数据模型，这些对象返回 <xref:System.Linq.IQueryable%601> 接口的实例。</span><span class="sxs-lookup"><span data-stu-id="1c726-108"> also supports data models that are based on common language runtime (CLR) objects that return an instance of the <xref:System.Linq.IQueryable%601> interface.</span></span> <span data-ttu-id="1c726-109">通过此功能，您可以在 .NET Framework 中部署基于列表、数组和集合的数据服务。</span><span class="sxs-lookup"><span data-stu-id="1c726-109">This enables you to deploy data services that are based on lists, arrays, and collections in the .NET Framework.</span></span> <span data-ttu-id="1c726-110">若要启用针对这些数据结构的创建、更新和删除操作，还必须实现 <xref:System.Data.Services.IUpdatable> 接口。</span><span class="sxs-lookup"><span data-stu-id="1c726-110">To enable create, update, and delete operations over these data structures, you must also implement the <xref:System.Data.Services.IUpdatable> interface.</span></span> <span data-ttu-id="1c726-111">有关详细信息，请参阅[如何： 创建数据服务使用反射提供程序](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-111">For more information, see [How to: Create a Data Service Using the Reflection Provider](../../../../docs/framework/data/wcf/create-a-data-service-using-rp-wcf-data-services.md).</span></span>  
  
     <span data-ttu-id="1c726-112">对于更高级方案，[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]包括一套提供程序使您能够定义基于后期绑定数据类型的数据模型。</span><span class="sxs-lookup"><span data-stu-id="1c726-112">For more advanced scenarios, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] includes a set of providers that enable you to define a data model based on late-bound data types.</span></span> <span data-ttu-id="1c726-113">有关详细信息，请参阅[自定义数据服务提供商](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-113">For more information, see [Custom Data Service Providers](../../../../docs/framework/data/wcf/custom-data-service-providers-wcf-data-services.md).</span></span>  
  
2.  <span data-ttu-id="1c726-114">**创建数据服务。**</span><span class="sxs-lookup"><span data-stu-id="1c726-114">**Create the data service.**</span></span> <span data-ttu-id="1c726-115">大多数基本数据服务公开一个从 <xref:System.Data.Services.DataService%601> 类继承的类和一个作为实体容器的命名空间限定名称的 `T` 类型。</span><span class="sxs-lookup"><span data-stu-id="1c726-115">The most basic data service exposes a class that inherits from the <xref:System.Data.Services.DataService%601> class, with a type `T` that is the namespace-qualified name of the entity container.</span></span> <span data-ttu-id="1c726-116">有关详细信息，请参阅 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)的信息。</span><span class="sxs-lookup"><span data-stu-id="1c726-116">For more information, see [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md).</span></span>  
  
3.  <span data-ttu-id="1c726-117">**配置数据服务。**</span><span class="sxs-lookup"><span data-stu-id="1c726-117">**Configure the data service.**</span></span> <span data-ttu-id="1c726-118">默认情况下， [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 会禁用对实体容器所公开的资源的访问。</span><span class="sxs-lookup"><span data-stu-id="1c726-118">By default, [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] disables access to resources that are exposed by an entity container.</span></span> <span data-ttu-id="1c726-119">通过 <xref:System.Data.Services.DataServiceConfiguration> 接口可以配置对资源和服务操作的访问、指定支持的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 版本并定义其他服务范围的行为，例如批处理行为或可在单个响应中返回的最大实体数。</span><span class="sxs-lookup"><span data-stu-id="1c726-119">The <xref:System.Data.Services.DataServiceConfiguration> interface enables you to configure access to resources and service operations, specify the supported version of [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)], and to define other service-wide behaviors, such as batching behaviors or the maximum number of entities that can be returned in a single response.</span></span> <span data-ttu-id="1c726-120">有关详细信息，请参阅[配置数据服务](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-120">For more information, see [Configuring the Data Service](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).</span></span>  
  
 <span data-ttu-id="1c726-121">有关如何创建基于 Northwind 示例数据库的简单数据服务的示例，请参阅[快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1c726-121">For an example of how to create a simple data service that is based on the Northwind sample database, see [Quickstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c726-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c726-122">See Also</span></span>  
 [<span data-ttu-id="1c726-123">入门</span><span class="sxs-lookup"><span data-stu-id="1c726-123">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)  
 [<span data-ttu-id="1c726-124">概述</span><span class="sxs-lookup"><span data-stu-id="1c726-124">Overview</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-overview.md)
