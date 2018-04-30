---
title: 支持多个 IIS 站点绑定
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
caps.latest.revision: 8
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a4b586b4d5c3c37355bf7b05a8a0227565a5b5e5
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2018
---
# <a name="supporting-multiple-iis-site-bindings"></a>支持多个 IIS 站点绑定
在 Internet Information Services (IIS) 7.0 下承载 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务时，可能需要在同一站点上提供使用相同协议的多个基址。 这使得同一服务可以响应多个不同的 URI。 这是有用的当你想要承载的服务在其侦听时http://www.contoso.com和http://contoso.com。在创建对于内部用户和外部用户使用不同基址的服务时，此功能也非常有用。 例如：http://internal.contoso.com和http://www.contoso.com。  
  
> [!NOTE]
>  此功能仅在使用 HTTP 协议时可用。  
  
## <a name="multiple-base-addresses"></a>多个基址  
 此功能仅适用于在 IIS 下承载的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。 默认情况下不启用此功能。 若要启用它必须添加`multipleSiteBindingsEnabled`属性设为 <`serviceHostingEnvironment`> 元素在 Web.config 文件并将其设置为`true`，下面的示例中所示。  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 在 IIS 下承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时，IIS 将根据包含应用程序的虚拟目录的 URI 创建一个基址。 您可以通过 Internet 信息服务管理器添加使用相同协议的其他基址，从而向网站添加一个或多个绑定。 对于每个绑定，请指定协议（HTTP 或 HTTPS）、IP 地址、端口和主机名。 有关使用 Internet Information Services 管理器的详细信息，请参阅[IIS 管理器 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057)。 有关将绑定添加到站点的详细信息，请参阅[创建网站 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)  
  
 为同一站点指定多个基址会影响 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 帮助页的内容、导入架构和由服务生成的 WSDL/MEX 信息。 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 帮助页显示用于生成与服务通信的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端的命令行。 此命令行只包含在 IIS 绑定中为网站指定的第一个地址。 与导入方案时相似，只使用在 IIS 绑定中指定的第一个基址。 WSDL 和 MEX 数据包含在 IIS 绑定中指定的所有基址。  
  
> [!WARNING]
>  这意味着，如果某个服务有两个基址，其中一个供内部用户使用，另一个供外部用户使用，将在由该服务生成的 WSDL/MEX 信息中指定这两个基址。
