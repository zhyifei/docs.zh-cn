---
title: 发布元数据
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 031a80c52c194f300d7785f05e73eabeebb296b7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="publishing-metadata"></a><span data-ttu-id="606dd-102">发布元数据</span><span class="sxs-lookup"><span data-stu-id="606dd-102">Publishing Metadata</span></span>
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]<span data-ttu-id="606dd-103"> 服务通过发布一个或多个元数据终结点来发布元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-103"> services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="606dd-104">发布服务元数据之后，可以通过标准协议（如 WS-MetadataExchange (MEX) 和 HTTP/GET 请求）来使用该元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="606dd-105">元数据终结点类似于其他服务终结点，因为它们都有一个地址、一个绑定和一个协定，并且它们都可通过配置或命令代码添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="606dd-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or imperative code.</span></span>  
  
## <a name="publishing-metadata-endpoints"></a><span data-ttu-id="606dd-106">发布元数据终结点</span><span class="sxs-lookup"><span data-stu-id="606dd-106">Publishing Metadata Endpoints</span></span>  
 <span data-ttu-id="606dd-107">若要发布 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务的终结点，首先必须将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 服务行为添加到该服务。</span><span class="sxs-lookup"><span data-stu-id="606dd-107">To publish metadata endpoints for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service, you first must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span> <span data-ttu-id="606dd-108">添加一个 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 实例将允许服务公开元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="606dd-108">Adding a <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> instance allows your service to expose metadata endpoints.</span></span> <span data-ttu-id="606dd-109">添加 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 服务行为之后，就可以公开支持 MEX 协议或响应 HTTP/GET 请求的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="606dd-109">Once you add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> service behavior, you can then expose metadata endpoints that support the MEX protocol or that respond to HTTP/GET requests.</span></span>  
  
 <span data-ttu-id="606dd-110"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 使用 <xref:System.ServiceModel.Description.WsdlExporter> 来导出服务中所有服务终结点的元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-110">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> uses a <xref:System.ServiceModel.Description.WsdlExporter> to export metadata for all service endpoints in your service.</span></span> <span data-ttu-id="606dd-111">有关从服务中导出元数据的详细信息，请参阅[导出和导入元数据](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)。</span><span class="sxs-lookup"><span data-stu-id="606dd-111">For more information about exporting metadata from a service, see [Exporting and Importing Metadata](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).</span></span>  
  
 <span data-ttu-id="606dd-112"><xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 添加一个 <xref:System.ServiceModel.Description.ServiceMetadataExtension> 实例作为服务主机的扩展。</span><span class="sxs-lookup"><span data-stu-id="606dd-112">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> adds a <xref:System.ServiceModel.Description.ServiceMetadataExtension> instance as an extension to your service host.</span></span> <span data-ttu-id="606dd-113"><xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> 提供了元数据发布协议的实现。</span><span class="sxs-lookup"><span data-stu-id="606dd-113">The <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> provides the implementation for the metadata publishing protocols.</span></span> <span data-ttu-id="606dd-114">还可以使用 <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> 通过访问 <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> 属性来在运行时获取服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-114">You can also use the <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> to get the service's metadata at runtime by accessing the <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType> property.</span></span>  
  
### <a name="mex-metadata-endpoints"></a><span data-ttu-id="606dd-115">MEX 元数据终结点</span><span class="sxs-lookup"><span data-stu-id="606dd-115">MEX Metadata Endpoints</span></span>  
 <span data-ttu-id="606dd-116">要添加使用 MEX 协议的元数据终结点，请将服务终结点添加到使用 `IMetadataExchange` 服务协定的服务主机。</span><span class="sxs-lookup"><span data-stu-id="606dd-116">To add metadata endpoints that use the MEX protocol, add service endpoints to your service host that use the `IMetadataExchange` service contract.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="606dd-117"> 包括 <xref:System.ServiceModel.Description.IMetadataExchange> 接口以及此服务协定名称，您可以将此名称用作 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 编程模型的一部分。</span><span class="sxs-lookup"><span data-stu-id="606dd-117"> includes an <xref:System.ServiceModel.Description.IMetadataExchange> interface with this service contract name that you can use as part of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] programming model.</span></span> <span data-ttu-id="606dd-118">WS-MetadataExchange 终结点，即 MEX 终结点，可以使用静态工厂方法在 <xref:System.ServiceModel.Description.MetadataExchangeBindings> 类中公开的四种默认绑定之一来匹配 Svcutil.exe 之类的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 工具所使用的默认绑定。</span><span class="sxs-lookup"><span data-stu-id="606dd-118">WS-MetadataExchange endpoints, or MEX endpoints, can use one of the four default bindings that the static factory methods expose on the <xref:System.ServiceModel.Description.MetadataExchangeBindings> class to match the default bindings used by [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] tools such as Svcutil.exe.</span></span> <span data-ttu-id="606dd-119">还可以使用自己的自定义绑定来配置 MEX 元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="606dd-119">You can also configure MEX metadata endpoints using your own custom binding.</span></span>  
  
### <a name="http-get-metadata-endpoints"></a><span data-ttu-id="606dd-120">HTTP GET 元数据终结点</span><span class="sxs-lookup"><span data-stu-id="606dd-120">HTTP GET Metadata Endpoints</span></span>  
 <span data-ttu-id="606dd-121">若要将元数据终结点添加到响应 HTTP/GET 请求的服务，请将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 属性设置为 `true`。</span><span class="sxs-lookup"><span data-stu-id="606dd-121">To add a metadata endpoint to your service that responds to HTTP/GET requests, set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span> <span data-ttu-id="606dd-122">将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> 属性设置为 `true` 还可以配置使用 HTTPS 的元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="606dd-122">You can also configure a metadata endpoint that uses HTTPS by setting the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> property on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> to `true`.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="606dd-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="606dd-123">In This Section</span></span>  
 [<span data-ttu-id="606dd-124">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="606dd-124">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="606dd-125">演示如何配置 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务来发布元数据，以使客户端可使用 WS-MetadataExchange 或包含 `?wsdl` 查询字符串的 HTTP/GET 请求来检索元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-125">Demonstrates how to configure a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="606dd-126">如何：使用代码发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="606dd-126">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="606dd-127">演示如何在代码中为 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务启用元数据发布，以使客户端可使用 WS-MetadataExchange 或包含 `?wsdl` 查询字符串的 HTTP/GET 请求来检索元数据。</span><span class="sxs-lookup"><span data-stu-id="606dd-127">Demonstrates how to enable metadata publishing for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="606dd-128">参考</span><span class="sxs-lookup"><span data-stu-id="606dd-128">Reference</span></span>  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a><span data-ttu-id="606dd-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="606dd-129">See Also</span></span>  
 [<span data-ttu-id="606dd-130">导出和导入元数据</span><span class="sxs-lookup"><span data-stu-id="606dd-130">Exporting and Importing Metadata</span></span>](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
