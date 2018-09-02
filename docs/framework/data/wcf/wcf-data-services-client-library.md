---
title: WCF 数据服务客户端库
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
- DataServiceQuery class, about DataServiceQuery class
- DataServiceContext class, about DataServiceContext class
ms.assetid: 21075e50-8917-413e-a8ea-35a0f6e65aa5
ms.openlocfilehash: 4f389530b287d1c7a11a88972ef948347d3ea533
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2018
ms.locfileid: "43421590"
---
# <a name="wcf-data-services-client-library"></a><span data-ttu-id="63fcc-102">WCF 数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="63fcc-102">WCF Data Services Client Library</span></span>
<span data-ttu-id="63fcc-103">如果任一应用程序可发送 HTTP 请求并处理数据服务返回的 [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] 源，则该应用程序可与基于[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 的数据服务进行交互。</span><span class="sxs-lookup"><span data-stu-id="63fcc-103">Any application can interact with an [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]-based data service if it can send an HTTP request and process the [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed that a data service returns.</span></span> <span data-ttu-id="63fcc-104">通过这种互操作性，您可以从启用 Web 的诸多应用程序访问基于 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 的服务。</span><span class="sxs-lookup"><span data-stu-id="63fcc-104">This interoperability enables you to access [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-based services from a broad range of Web-enabled applications.</span></span> [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]<span data-ttu-id="63fcc-105"> 包括提供更丰富的编程体验，当您使用的客户端库[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源从.NET Framework 或基于 Silverlight 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="63fcc-105"> includes client libraries that provide a richer programming experience when you consume [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds from .NET Framework or Silverlight-based applications.</span></span>  
  
 <span data-ttu-id="63fcc-106">客户端库的两大主要类为 <xref:System.Data.Services.Client.DataServiceContext> 类和 <xref:System.Data.Services.Client.DataServiceQuery%601> 类。</span><span class="sxs-lookup"><span data-stu-id="63fcc-106">The two main classes of the client library are the <xref:System.Data.Services.Client.DataServiceContext> class and the <xref:System.Data.Services.Client.DataServiceQuery%601> class.</span></span> <span data-ttu-id="63fcc-107"><xref:System.Data.Services.Client.DataServiceContext> 类封装针对指定数据服务支持的操作。</span><span class="sxs-lookup"><span data-stu-id="63fcc-107">The <xref:System.Data.Services.Client.DataServiceContext> class encapsulates operations that are supported against a specified data service.</span></span> <span data-ttu-id="63fcc-108">尽管 [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] 服务是无状态的，但上下文不是。</span><span class="sxs-lookup"><span data-stu-id="63fcc-108">Although [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] services are stateless, the context is not.</span></span> <span data-ttu-id="63fcc-109">因此，可以使用<xref:System.Data.Services.Client.DataServiceContext>诸如更改管理的类，以保持与数据服务以便支持各种交互之间客户端的状态功能。</span><span class="sxs-lookup"><span data-stu-id="63fcc-109">Therefore, you can use the <xref:System.Data.Services.Client.DataServiceContext> class to maintain state on the client between interactions with the data service in order to support features such as change management.</span></span> <span data-ttu-id="63fcc-110">该类还对更改的标识和跟踪进行管理。</span><span class="sxs-lookup"><span data-stu-id="63fcc-110">This class also manages identities and tracks changes.</span></span> <span data-ttu-id="63fcc-111"><xref:System.Data.Services.Client.DataServiceQuery%601> 类表示一个针对特定实体集的查询。</span><span class="sxs-lookup"><span data-stu-id="63fcc-111">The <xref:System.Data.Services.Client.DataServiceQuery%601> class represents a query against a specific entity set.</span></span>  
  
 <span data-ttu-id="63fcc-112">本节介绍如何使用客户端库从 .NET Framework 客户端应用程序访问和更改数据。</span><span class="sxs-lookup"><span data-stu-id="63fcc-112">This section describes how to use client libraries to access and change data from a .NET Framework client application.</span></span> <span data-ttu-id="63fcc-113">有关如何使用详细信息[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]客户端库与基于 Silverlight 的应用程序，请参阅[WCF 数据服务 (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016)。</span><span class="sxs-lookup"><span data-stu-id="63fcc-113">For more information about how to use the [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] client library with a Silverlight-based application, see [WCF Data Services (Silverlight)](https://go.microsoft.com/fwlink/?LinkId=186016).</span></span> <span data-ttu-id="63fcc-114">其他客户端库可让你使用[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]源中其他类型的应用程序。</span><span class="sxs-lookup"><span data-stu-id="63fcc-114">Other client libraries are available that enable you to consume an [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed in other kinds of applications.</span></span> <span data-ttu-id="63fcc-115">有关详细信息，请参阅[OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796)。</span><span class="sxs-lookup"><span data-stu-id="63fcc-115">For more information, see the [OData SDK](https://go.microsoft.com/fwlink/?LinkID=185796).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="63fcc-116">本节内容</span><span class="sxs-lookup"><span data-stu-id="63fcc-116">In This Section</span></span>  
 [<span data-ttu-id="63fcc-117">生成数据服务客户端库</span><span class="sxs-lookup"><span data-stu-id="63fcc-117">Generating the Data Service Client Library</span></span>](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)  
 <span data-ttu-id="63fcc-118">介绍如何生成客户端库和客户端数据服务类基于[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]馈送。</span><span class="sxs-lookup"><span data-stu-id="63fcc-118">Describes how to generate a client library and client data service classes that are based on [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feeds.</span></span>  
  
 [<span data-ttu-id="63fcc-119">查询数据服务</span><span class="sxs-lookup"><span data-stu-id="63fcc-119">Querying the Data Service</span></span>](../../../../docs/framework/data/wcf/querying-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="63fcc-120">介绍如何使用客户端库从基于 .NET Framework 的应用程序查询数据服务。</span><span class="sxs-lookup"><span data-stu-id="63fcc-120">Describes how to query a data service from a .NET Framework-based application by using client libraries.</span></span>  
  
 [<span data-ttu-id="63fcc-121">加载延迟的内容</span><span class="sxs-lookup"><span data-stu-id="63fcc-121">Loading Deferred Content</span></span>](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)  
 <span data-ttu-id="63fcc-122">介绍如何加载未包含在初始查询响应中的附加内容。</span><span class="sxs-lookup"><span data-stu-id="63fcc-122">Describes how to load additional content not included in the initial query response.</span></span>  
  
 [<span data-ttu-id="63fcc-123">更新数据服务</span><span class="sxs-lookup"><span data-stu-id="63fcc-123">Updating the Data Service</span></span>](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md)  
 <span data-ttu-id="63fcc-124">介绍如何使用客户端库来创建、修改和删除实体和关系。</span><span class="sxs-lookup"><span data-stu-id="63fcc-124">Describes how to create, modify, and delete entities and relationships by using the client libraries.</span></span>  
  
 [<span data-ttu-id="63fcc-125">异步操作</span><span class="sxs-lookup"><span data-stu-id="63fcc-125">Asynchronous Operations</span></span>](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md)  
 <span data-ttu-id="63fcc-126">介绍客户端库提供的用于以异步方式使用数据服务的功能。</span><span class="sxs-lookup"><span data-stu-id="63fcc-126">Describes the facilities provided by the client libraries for working with a data service in an asynchronous manner.</span></span>  
  
 [<span data-ttu-id="63fcc-127">批处理操作</span><span class="sxs-lookup"><span data-stu-id="63fcc-127">Batching Operations</span></span>](../../../../docs/framework/data/wcf/batching-operations-wcf-data-services.md)  
 <span data-ttu-id="63fcc-128">介绍如何使用客户端库在一个批处理中向数据服务发送多个请求。</span><span class="sxs-lookup"><span data-stu-id="63fcc-128">Describes how to send multiple requests to the data service in a single batch by using the client libraries.</span></span>  
  
 [<span data-ttu-id="63fcc-129">将数据绑定到控件</span><span class="sxs-lookup"><span data-stu-id="63fcc-129">Binding Data to Controls</span></span>](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)  
 <span data-ttu-id="63fcc-130">介绍如何将控件绑定到[!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]数据服务返回的源。</span><span class="sxs-lookup"><span data-stu-id="63fcc-130">Describes how to bind controls to a [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] feed returned by a data service.</span></span>  
  
 [<span data-ttu-id="63fcc-131">调用服务操作</span><span class="sxs-lookup"><span data-stu-id="63fcc-131">Calling Service Operations</span></span>](../../../../docs/framework/data/wcf/calling-service-operations-wcf-data-services.md)  
 <span data-ttu-id="63fcc-132">介绍如何使用客户端库调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="63fcc-132">Describes how to use the client library to call service operations.</span></span>  
  
 [<span data-ttu-id="63fcc-133">管理数据服务上下文</span><span class="sxs-lookup"><span data-stu-id="63fcc-133">Managing the Data Service Context</span></span>](../../../../docs/framework/data/wcf/managing-the-data-service-context-wcf-data-services.md)  
 <span data-ttu-id="63fcc-134">介绍用于管理客户端库的行为的选项。</span><span class="sxs-lookup"><span data-stu-id="63fcc-134">Describes options for managing the behavior of the client library.</span></span>  
  
 [<span data-ttu-id="63fcc-135">处理二进制数据</span><span class="sxs-lookup"><span data-stu-id="63fcc-135">Working with Binary Data</span></span>](../../../../docs/framework/data/wcf/working-with-binary-data-wcf-data-services.md)  
 <span data-ttu-id="63fcc-136">介绍如何访问和更改数据服务作为数据流返回的二进制数据。</span><span class="sxs-lookup"><span data-stu-id="63fcc-136">Describes how to access and change binary data returned by the data service as a data stream.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fcc-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="63fcc-137">See Also</span></span>  
 [<span data-ttu-id="63fcc-138">定义 WCF Data Services</span><span class="sxs-lookup"><span data-stu-id="63fcc-138">Defining WCF Data Services</span></span>](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)  
 [<span data-ttu-id="63fcc-139">入门</span><span class="sxs-lookup"><span data-stu-id="63fcc-139">Getting Started</span></span>](../../../../docs/framework/data/wcf/getting-started-with-wcf-data-services.md)
