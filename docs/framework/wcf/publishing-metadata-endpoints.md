---
title: 发布元数据终结点
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 42e0f82ca2c669bbde444cf6aac9ce8f0266f783
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="9a1d8-102">发布元数据终结点</span><span class="sxs-lookup"><span data-stu-id="9a1d8-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="9a1d8-103">Windows Communication Foundation (WCF) 服务通过发布一个或多个元数据终结点发布元数据。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="9a1d8-104">发布服务元数据之后，可以通过标准协议（如 WS-MetadataExchange (MEX) 和 HTTP/GET 请求）来使用该元数据。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="9a1d8-105">元数据终结点类似于其他服务终结点：它们都有一个地址、一个绑定和一个协定，并且它们都可通过配置或使用代码添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="9a1d8-106">若要启用发布元数据终结点，必须将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 服务行为添加到该服务。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="9a1d8-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="9a1d8-107">In This Section</span></span>  
 [<span data-ttu-id="9a1d8-108">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="9a1d8-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="9a1d8-109">演示如何配置 WCF 服务来发布元数据，使客户端可以检索使用 Ws-metadataexchange 或 HTTP/GET 请求使用的元数据`?wsdl`查询字符串。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="9a1d8-110">如何：使用代码发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="9a1d8-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="9a1d8-111">演示如何启用代码中的 WCF 服务的元数据发布，以便客户端能够检索使用 Ws-metadataexchange 或 HTTP/GET 请求使用的元数据`?wsdl`查询字符串。</span><span class="sxs-lookup"><span data-stu-id="9a1d8-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a1d8-112">请参阅</span><span class="sxs-lookup"><span data-stu-id="9a1d8-112">See Also</span></span>  
 [<span data-ttu-id="9a1d8-113">发布元数据</span><span class="sxs-lookup"><span data-stu-id="9a1d8-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
