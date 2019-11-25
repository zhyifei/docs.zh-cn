---
title: 定义 WCF 数据服务
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 05006ff3-02dc-410e-831e-54ec3e7e24ef
ms.openlocfilehash: 26cfee95f7cd3b956ff263d90b713e9d70b98202
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2019
ms.locfileid: "73975331"
---
# <a name="defining-wcf-data-services"></a><span data-ttu-id="90cbb-102">定义 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="90cbb-102">Defining WCF Data Services</span></span>

<span data-ttu-id="90cbb-103">本部分介绍如何创建和配置 WCF 数据服务以将数据作为 Open Data Protocol （OData）源公开。</span><span class="sxs-lookup"><span data-stu-id="90cbb-103">This section describes how to create and configure WCF Data Services to expose data as an Open Data Protocol (OData) feed.</span></span> <span data-ttu-id="90cbb-104">有关创建数据服务所需的基本步骤的详细信息，请参阅[将数据作为服务公开](exposing-your-data-as-a-service-wcf-data-services.md)。</span><span class="sxs-lookup"><span data-stu-id="90cbb-104">For more information about the basic steps required to create a data service, see [Exposing Your Data as a Service](exposing-your-data-as-a-service-wcf-data-services.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="90cbb-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="90cbb-105">In This Section</span></span>

 [<span data-ttu-id="90cbb-106">配置数据服务</span><span class="sxs-lookup"><span data-stu-id="90cbb-106">Configuring the Data Service</span></span>](configuring-the-data-service-wcf-data-services.md)

 <span data-ttu-id="90cbb-107">介绍 WCF 数据服务提供的数据服务配置选项。</span><span class="sxs-lookup"><span data-stu-id="90cbb-107">Describes the data service configuration options provided by WCF Data Services.</span></span>

 [<span data-ttu-id="90cbb-108">数据服务提供程序</span><span class="sxs-lookup"><span data-stu-id="90cbb-108">Data Services Providers</span></span>](data-services-providers-wcf-data-services.md)

 <span data-ttu-id="90cbb-109">描述用于将数据作为数据服务公开的提供程序模型。</span><span class="sxs-lookup"><span data-stu-id="90cbb-109">Describes the provider models for exposing data as a data service.</span></span>

 [<span data-ttu-id="90cbb-110">服务操作</span><span class="sxs-lookup"><span data-stu-id="90cbb-110">Service Operations</span></span>](service-operations-wcf-data-services.md)

 <span data-ttu-id="90cbb-111">描述如何定义在服务器上公开方法的服务操作。</span><span class="sxs-lookup"><span data-stu-id="90cbb-111">Describes how to define service operations that expose methods on the server.</span></span>

 [<span data-ttu-id="90cbb-112">源自定义</span><span class="sxs-lookup"><span data-stu-id="90cbb-112">Feed Customization</span></span>](feed-customization-wcf-data-services.md)

 <span data-ttu-id="90cbb-113">描述如何在数据服务提供程序定义的数据模型中的实体与数据源中的元素之间创建映射。</span><span class="sxs-lookup"><span data-stu-id="90cbb-113">Describes how to create a mapping between entities in the data model defined by the data service provider and elements in the data feed.</span></span>

 [<span data-ttu-id="90cbb-114">侦听器</span><span class="sxs-lookup"><span data-stu-id="90cbb-114">Interceptors</span></span>](interceptors-wcf-data-services.md)

 <span data-ttu-id="90cbb-115">描述如何定义侦听器方法用于对数据服务请求执行自定义业务逻辑。</span><span class="sxs-lookup"><span data-stu-id="90cbb-115">Describes how to define interceptor methods to perform custom business logic on requests to the data service.</span></span>

 [<span data-ttu-id="90cbb-116">开发和部署 WCF 数据服务</span><span class="sxs-lookup"><span data-stu-id="90cbb-116">Developing and Deploying WCF Data Services</span></span>](developing-and-deploying-wcf-data-services.md)

 <span data-ttu-id="90cbb-117">描述如何使用 Visual Studio 开发和部署数据服务。</span><span class="sxs-lookup"><span data-stu-id="90cbb-117">Describes how to develop and deploy a data service by using Visual Studio.</span></span>

 [<span data-ttu-id="90cbb-118">确保 WCF Data Services 的安全</span><span class="sxs-lookup"><span data-stu-id="90cbb-118">Securing WCF Data Services</span></span>](securing-wcf-data-services.md)

 <span data-ttu-id="90cbb-119">描述数据服务的身份验证和授权以及其他安全注意事项。</span><span class="sxs-lookup"><span data-stu-id="90cbb-119">Describes authentication and authorization for the data service and other security considerations.</span></span>

 [<span data-ttu-id="90cbb-120">承载数据服务</span><span class="sxs-lookup"><span data-stu-id="90cbb-120">Hosting the Data Service</span></span>](hosting-the-data-service-wcf-data-services.md)

 <span data-ttu-id="90cbb-121">描述如何为数据服务选择宿主。</span><span class="sxs-lookup"><span data-stu-id="90cbb-121">Describes how to select a host for your data service.</span></span>

 [<span data-ttu-id="90cbb-122">数据服务版本控制</span><span class="sxs-lookup"><span data-stu-id="90cbb-122">Data Service Versioning</span></span>](data-service-versioning-wcf-data-services.md)

 <span data-ttu-id="90cbb-123">介绍如何使用不同版本的 OData。</span><span class="sxs-lookup"><span data-stu-id="90cbb-123">Describes how to work with different versions of the OData.</span></span>

 [<span data-ttu-id="90cbb-124">WCF 数据服务协议实现详细信息</span><span class="sxs-lookup"><span data-stu-id="90cbb-124">WCF Data Services Protocol Implementation Details</span></span>](wcf-data-services-protocol-implementation-details.md)

 <span data-ttu-id="90cbb-125">描述 WCF 数据服务当前未实现的 OData 协议的可选功能。</span><span class="sxs-lookup"><span data-stu-id="90cbb-125">Describes optional functionalities of the OData protocol that are not currently implemented by WCF Data Services.</span></span>

## <a name="see-also"></a><span data-ttu-id="90cbb-126">请参阅</span><span class="sxs-lookup"><span data-stu-id="90cbb-126">See also</span></span>

- [<span data-ttu-id="90cbb-127">WCF Data Services 客户端库</span><span class="sxs-lookup"><span data-stu-id="90cbb-127">WCF Data Services Client Library</span></span>](wcf-data-services-client-library.md)
- [<span data-ttu-id="90cbb-128">访问数据服务资源</span><span class="sxs-lookup"><span data-stu-id="90cbb-128">Accessing Data Service Resources</span></span>](accessing-data-service-resources-wcf-data-services.md)
- [<span data-ttu-id="90cbb-129">入门</span><span class="sxs-lookup"><span data-stu-id="90cbb-129">Getting Started</span></span>](getting-started-with-wcf-data-services.md)
