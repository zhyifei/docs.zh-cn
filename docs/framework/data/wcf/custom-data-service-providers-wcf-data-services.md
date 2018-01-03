---
title: "自定义数据服务提供程序（WCF 数据服务）"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF Data Services, providers
ms.assetid: e702ecdb-3419-4743-92a9-c3c0e7d44082
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d7db780b97c1a7eadffbfa71f60be4afe590ccb4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="custom-data-service-providers-wcf-data-services"></a><span data-ttu-id="0a684-102">自定义数据服务提供程序（WCF 数据服务）</span><span class="sxs-lookup"><span data-stu-id="0a684-102">Custom Data Service Providers (WCF Data Services)</span></span>
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="0a684-103"> 包括一组提供程序，用于基于后期绑定数据类型定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="0a684-103"> includes a set of providers that enables you to define a data model based on late-bound data types.</span></span>  
  
|<span data-ttu-id="0a684-104">提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-104">Provider</span></span>|<span data-ttu-id="0a684-105">描述</span><span class="sxs-lookup"><span data-stu-id="0a684-105">Description</span></span>|  
|--------------|-----------------|  
|<span data-ttu-id="0a684-106">元数据提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-106">Metadata provider</span></span>|<span data-ttu-id="0a684-107">这是核心的自定义数据服务提供程序，用于通过实现 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 接口在运行时定义自定义数据模型。</span><span class="sxs-lookup"><span data-stu-id="0a684-107">This is the core custom data service provider that enables you to define a custom data model at runtime by implementing the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span>|  
|<span data-ttu-id="0a684-108">查询提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-108">Query provider</span></span>|<span data-ttu-id="0a684-109">该提供程序用于对使用 <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> 接口定义的自定义数据模型执行查询。</span><span class="sxs-lookup"><span data-stu-id="0a684-109">This provider enables you to execute queries against a custom data model that is defined by using the <xref:System.Data.Services.Providers.IDataServiceMetadataProvider> interface.</span></span> <span data-ttu-id="0a684-110">查询提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceQueryProvider> 接口而创建。</span><span class="sxs-lookup"><span data-stu-id="0a684-110">The query provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceQueryProvider> interface.</span></span>|  
|<span data-ttu-id="0a684-111">更新提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-111">Update provider</span></span>|<span data-ttu-id="0a684-112">该提供程序用于更新在自定义数据服务提供程序中公开的类型和管理并发性。</span><span class="sxs-lookup"><span data-stu-id="0a684-112">This provider enables you to make updates to types that are exposed in a custom data service provider and to manage concurrency.</span></span> <span data-ttu-id="0a684-113">更新提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> 接口而创建。</span><span class="sxs-lookup"><span data-stu-id="0a684-113">An update provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceUpdateProvider> interface</span></span>|  
|<span data-ttu-id="0a684-114">分页提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-114">Paging provider</span></span>|<span data-ttu-id="0a684-115">该提供程序用于与自定义数据服务提供程序一起启用服务器驱动的分页支持。</span><span class="sxs-lookup"><span data-stu-id="0a684-115">This provider is used with the custom data service provider to enable server-driven paging support.</span></span> <span data-ttu-id="0a684-116">自定义数据服务的分页提供程序通过实现 <xref:System.Data.Services.Providers.IDataServicePagingProvider> 接口而创建。</span><span class="sxs-lookup"><span data-stu-id="0a684-116">A paging provider for a custom data service is created by implementing the <xref:System.Data.Services.Providers.IDataServicePagingProvider> interface.</span></span>|  
|<span data-ttu-id="0a684-117">流提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-117">Streaming provider</span></span>|<span data-ttu-id="0a684-118">此提供程序用于以流形式公开二进制大型对象数据类型。</span><span class="sxs-lookup"><span data-stu-id="0a684-118">This provider enables you to expose binary large object data types as a stream.</span></span> <span data-ttu-id="0a684-119">流提供程序通过实现 <xref:System.Data.Services.Providers.IDataServiceStreamProvider> 接口而创建。</span><span class="sxs-lookup"><span data-stu-id="0a684-119">A streaming provider is created by implementing the <xref:System.Data.Services.Providers.IDataServiceStreamProvider> interface.</span></span> <span data-ttu-id="0a684-120">流提供程序还可与实体框架提供程序和反射数据源提供程序一起使用。</span><span class="sxs-lookup"><span data-stu-id="0a684-120">The streaming provider can also be used with Entity Framework and reflection data source providers.</span></span> <span data-ttu-id="0a684-121">有关详细信息，请参阅[流提供程序](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="0a684-121">For more information, see [Streaming Provider](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).</span></span>|  
  
 <span data-ttu-id="0a684-122">有关详细信息，请参阅文章[自定义数据服务提供商](http://go.microsoft.com/fwlink/?LinkID=186850)和[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]中的提供程序工具包[OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069)。</span><span class="sxs-lookup"><span data-stu-id="0a684-122">For more information, see the article [Custom Data Service Providers](http://go.microsoft.com/fwlink/?LinkID=186850) and the [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] Provider Toolkit in the [OData SDK](http://go.microsoft.com/fwlink/?LinkId=186069).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a684-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="0a684-123">See Also</span></span>  
 [<span data-ttu-id="0a684-124">数据服务提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-124">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 [<span data-ttu-id="0a684-125">实体框架提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-125">Entity Framework Provider</span></span>](../../../../docs/framework/data/wcf/entity-framework-provider-wcf-data-services.md)  
 [<span data-ttu-id="0a684-126">反射提供程序</span><span class="sxs-lookup"><span data-stu-id="0a684-126">Reflection Provider</span></span>](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
