---
title: 定义 WCF 数据服务
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: ac75f5fd91f68d9403dc7b42325bf8970f0c6794
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765643"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="2db8f-102">定义 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="2db8f-102">Defining WCF Data Services</span></span>

<span data-ttu-id="2db8f-103">本部分介绍如何创建和配置 WCF 数据服务能够将数据公开为[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]源。</span><span class="sxs-lookup"><span data-stu-id="2db8f-103">This section describes how to create and configure WCF Data Services to expose data as an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] feed.</span></span> <span data-ttu-id="2db8f-104">有关创建数据服务所需的基本步骤的详细信息，请参阅[公开数据作为服务恢复](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="2db8f-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](../../../../docs/framework/data/wcf/exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="2db8f-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="2db8f-105">In This Section</span></span>

 [<span data-ttu-id="2db8f-106">配置数据服务</span><span class="sxs-lookup"><span data-stu-id="2db8f-106">Configuring the Data Service</span></span>](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="2db8f-107">介绍由 WCF 数据服务提供的数据服务配置选项。</span><span class="sxs-lookup"><span data-stu-id="2db8f-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="2db8f-108">数据服务提供程序</span><span class="sxs-lookup"><span data-stu-id="2db8f-108">Data Services Providers</span></span>](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)

 <span data-ttu-id="2db8f-109">描述用于将数据作为数据服务公开的提供程序模型。</span><span class="sxs-lookup"><span data-stu-id="2db8f-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="2db8f-110">服务操作</span><span class="sxs-lookup"><span data-stu-id="2db8f-110">Service Operations</span></span>](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md)

 <span data-ttu-id="2db8f-111">描述如何定义在服务器上公开方法的服务操作。</span><span class="sxs-lookup"><span data-stu-id="2db8f-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="2db8f-112">源自定义</span><span class="sxs-lookup"><span data-stu-id="2db8f-112">Feed Customization</span></span>](../../../../docs/framework/data/wcf/feed-customization-wcf-data-services.md)

 <span data-ttu-id="2db8f-113">描述如何在数据服务提供程序定义的数据模型中的实体与数据源中的元素之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="2db8f-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="2db8f-114">侦听器</span><span class="sxs-lookup"><span data-stu-id="2db8f-114">Interceptors</span></span>](../../../../docs/framework/data/wcf/interceptors-wcf-data-services.md)

 <span data-ttu-id="2db8f-115">描述如何定义侦听器方法用于对数据服务请求执行自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="2db8f-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="2db8f-116">开发和部署 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="2db8f-116">Developing and Deploying WCF Data Services</span></span>](../../../../docs/framework/data/wcf/developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="2db8f-117">描述如何使用 Visual Studio 开发和部署数据服务。</span><span class="sxs-lookup"><span data-stu-id="2db8f-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="2db8f-118">确保 WCF Data Services 的安全</span><span class="sxs-lookup"><span data-stu-id="2db8f-118">Securing WCF Data Services</span></span>](../../../../docs/framework/data/wcf/securing-wcf-data-services.md)

 <span data-ttu-id="2db8f-119">描述数据服务的身份验证和授权以及其他安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="2db8f-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="2db8f-120">承载数据服务</span><span class="sxs-lookup"><span data-stu-id="2db8f-120">Hosting the Data Service</span></span>](../../../../docs/framework/data/wcf/hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="2db8f-121">描述如何为数据服务选择宿主。</span><span class="sxs-lookup"><span data-stu-id="2db8f-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="2db8f-122">数据服务版本控制</span><span class="sxs-lookup"><span data-stu-id="2db8f-122">Data Service Versioning</span></span>](../../../../docs/framework/data/wcf/data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="2db8f-123">介绍如何使用不同版本的 OData。</span><span class="sxs-lookup"><span data-stu-id="2db8f-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="2db8f-124">WCF 数据服务协议实现详细信息</span><span class="sxs-lookup"><span data-stu-id="2db8f-124">WCF Data Services Protocol Implementation Details</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="2db8f-125">描述当前未实现的 WCF 数据服务 OData 协议的可选功能。</span><span class="sxs-lookup"><span data-stu-id="2db8f-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="2db8f-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="2db8f-126">See also</span></span>

- [<span data-ttu-id="2db8f-127">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="2db8f-127">WCF Data Services Client Library</span></span>](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
- [<span data-ttu-id="2db8f-128">访问数据服务资源</span><span class="sxs-lookup"><span data-stu-id="2db8f-128">Accessing Data Service Resources</span></span>](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="2db8f-129">入门</span><span class="sxs-lookup"><span data-stu-id="2db8f-129">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
