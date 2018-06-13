---
title: 发布元数据终结点
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 42e0f82ca2c669bbde444cf6aac9ce8f0266f783
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807074"
---
# <a name="publishing-metadata-endpoints"></a>发布元数据终结点
Windows Communication Foundation (WCF) 服务通过发布一个或多个元数据终结点发布元数据。 发布服务元数据之后，可以通过标准协议（如 WS-MetadataExchange (MEX) 和 HTTP/GET 请求）来使用该元数据。 元数据终结点类似于其他服务终结点：它们都有一个地址、一个绑定和一个协定，并且它们都可通过配置或使用代码添加到服务主机。 若要启用发布元数据终结点，必须将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 服务行为添加到该服务。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：使用配置文件发布服务的元数据](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 演示如何配置 WCF 服务来发布元数据，使客户端可以检索使用 Ws-metadataexchange 或 HTTP/GET 请求使用的元数据`?wsdl`查询字符串。  
  
 [如何：使用代码发布服务的元数据](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 演示如何启用代码中的 WCF 服务的元数据发布，以便客户端能够检索使用 Ws-metadataexchange 或 HTTP/GET 请求使用的元数据`?wsdl`查询字符串。  
  
## <a name="see-also"></a>请参阅  
 [发布元数据](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
