---
title: "定义 WCF 数据服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 61b04be25f54ef22511f45b5752c3ccfa90d94ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="1fe00-102">定义 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="1fe00-102">Defining WCF Data Services</span></span>
<span data-ttu-id="1fe00-103">本部分介绍如何创建和配置[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]来公开数据作为[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源。</span><span class="sxs-lookup"><span data-stu-id="1fe00-103">This section describes how to create and configure [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="1fe00-104">创建数据服务时，所需的基本步骤，请参阅[公开数据作为一种服务恢复](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="1fe00-104"> the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1fe00-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="1fe00-105">In This Section</span></span>  
 [<span data-ttu-id="1fe00-106">配置数据服务</span><span class="sxs-lookup"><span data-stu-id="1fe00-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="1fe00-107">描述 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] 提供的数据服务配置选项。</span><span class="sxs-lookup"><span data-stu-id="1fe00-107">Describes the data service configuration options provided by [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)].</span></span>  
  
 [<span data-ttu-id="1fe00-108">数据服务提供程序</span><span class="sxs-lookup"><span data-stu-id="1fe00-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)  
 <span data-ttu-id="1fe00-109">描述用于将数据作为数据服务公开的提供程序模型。</span><span class="sxs-lookup"><span data-stu-id="1fe00-109">Describes the provider models for exposing data as a data service.</span></span>  
  
 [<span data-ttu-id="1fe00-110">服务操作</span><span class="sxs-lookup"><span data-stu-id="1fe00-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)  
 <span data-ttu-id="1fe00-111">描述如何定义在服务器上公开方法的服务操作。</span><span class="sxs-lookup"><span data-stu-id="1fe00-111">Describes how to define service operations that expose methods on the server.</span></span>  
  
 [<span data-ttu-id="1fe00-112">源自定义</span><span class="sxs-lookup"><span data-stu-id="1fe00-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)  
 <span data-ttu-id="1fe00-113">描述如何在数据服务提供程序定义的数据模型中的实体与数据源中的元素之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="1fe00-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>  
  
 [<span data-ttu-id="1fe00-114">侦听器</span><span class="sxs-lookup"><span data-stu-id="1fe00-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)  
 <span data-ttu-id="1fe00-115">描述如何定义侦听器方法用于对数据服务请求执行自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="1fe00-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>  
  
 [<span data-ttu-id="1fe00-116">开发和部署 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="1fe00-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)  
 <span data-ttu-id="1fe00-117">描述如何使用 Visual Studio 开发和部署数据服务。</span><span class="sxs-lookup"><span data-stu-id="1fe00-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>  
  
 [<span data-ttu-id="1fe00-118">确保 WCF Data Services 的安全</span><span class="sxs-lookup"><span data-stu-id="1fe00-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)  
 <span data-ttu-id="1fe00-119">描述数据服务的身份验证和授权以及其他安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="1fe00-119">Describes authentication and authorization for the data service and other security considerations.</span></span>  
  
 [<span data-ttu-id="1fe00-120">承载数据服务</span><span class="sxs-lookup"><span data-stu-id="1fe00-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="1fe00-121">描述如何为数据服务选择宿主。</span><span class="sxs-lookup"><span data-stu-id="1fe00-121">Describes how to select a host for your data service.</span></span>  
  
 [<span data-ttu-id="1fe00-122">数据服务版本控制</span><span class="sxs-lookup"><span data-stu-id="1fe00-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)  
 <span data-ttu-id="1fe00-123">描述如何使用其他版本的 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1fe00-123">Describes how to work with different versions of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)].</span></span>  
  
 [<span data-ttu-id="1fe00-124">WCF 数据服务协议实现详细信息</span><span class="sxs-lookup"><span data-stu-id="1fe00-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)  
 <span data-ttu-id="1fe00-125">描述 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 协议中 WCF 数据服务当前尚未实现的可选功能。</span><span class="sxs-lookup"><span data-stu-id="1fe00-125">Describes optional functionalities of the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] protocol that are not currently implemented by WCF Data Services.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fe00-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="1fe00-126">See Also</span></span>  
 [<span data-ttu-id="1fe00-127">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="1fe00-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)  
 [<span data-ttu-id="1fe00-128">访问数据服务资源</span><span class="sxs-lookup"><span data-stu-id="1fe00-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)  
 [<span data-ttu-id="1fe00-129">入门</span><span class="sxs-lookup"><span data-stu-id="1fe00-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
