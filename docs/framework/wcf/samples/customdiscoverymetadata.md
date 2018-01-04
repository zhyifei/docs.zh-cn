---
title: CustomDiscoveryMetadata
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c42455fd-3652-4b7e-b698-ab3a2bb52e48
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c2e13fde338075d9ef16c205efcfcb452235f0af
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="customdiscoverymetadata"></a>CustomDiscoveryMetadata
此示例演示如何在发现元数据中针对服务公开的可发现终结点插入自定义 XML 元数据。 示例随后演示客户端如何搜索服务和提取此自定义数据。 此示例由两个项目组成，即服务项目和客户端项目。  
  
## <a name="service"></a>服务  
 在 `main` 方法中，示例演示一个 <xref:System.Xml.Linq.XElement> 类型的对象填充为所需的字段并添加到 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> 中。 此 <xref:System.ServiceModel.Discovery.EndpointDiscoveryBehavior> 会添加到特定终结点。 当发现该特定终结点时，发现元数据会包含此处添加的自定义数据。  
  
## <a name="client"></a>客户端  
 本示例演示对 <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> 调用的 <xref:System.ServiceModel.Discovery.DiscoveryClient> 方法。 随后对得到的 <xref:System.ServiceModel.Discovery.FindResponse> 进行查询以获得所需的合适 XML 元素。 这些元素随后会打印到控制台。  
  
#### <a name="to-use-this-sample"></a>使用此示例  
  
1.  在 [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] 中加载项目解决方案，然后生成项目。  
  
2.  首先运行在 [解决方案基目录]\service\bin\debug 中生成的服务应用程序，然后运行在 [解决方案基目录]\Client\bin\debug 中生成的客户端应用程序  
  
3.  请注意，服务会处于脱机状态，客户端定位服务并打印在终结点发布的元数据。  
  
> [!IMPORTANT]
>  您的计算机上可能已安装这些示例。 在继续操作之前，请先检查以下（默认）目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。 此示例位于以下目录：  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\DiscoveryExtensibility\CustomDiscoveryMetadata`  
  
## <a name="see-also"></a>请参阅
