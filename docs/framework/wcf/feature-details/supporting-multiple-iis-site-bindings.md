---
title: 支持多个 IIS 站点绑定
ms.date: 03/30/2017
ms.assetid: 40440495-254d-45c8-a8c6-b29f364892ba
ms.openlocfilehash: a1fc2de3a10641dfc1c6181c7258bd4160f900e2
ms.sourcegitcommit: 37616676fde89153f563a485fc6159fc57326fc2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2019
ms.locfileid: "69988636"
---
# <a name="supporting-multiple-iis-site-bindings"></a>支持多个 IIS 站点绑定
当在 Internet Information Services (IIS) 7.0 下承载 Windows Communication Foundation (WCF) 服务时, 您可能需要提供在同一站点上使用同一协议的多个基址。 这使得同一服务可以响应多个不同的 URI。 这是有用的当你想要承载的服务在其侦听时 `http://www.contoso.com` 和 `http://contoso.com` 。 在创建对于内部用户和外部用户使用不同基址的服务时，此功能也非常有用。 例如：`http://internal.contoso.com` 和 `http://www.contoso.com` 。  
  
> [!NOTE]
> 此功能仅在使用 HTTP 协议时可用。  
  
## <a name="multiple-base-addresses"></a>多个基址  
 此功能仅适用于在 IIS 下承载的 WCF 服务。 默认情况下不启用此功能。 若要启用它, 必须将`multipleSiteBindingsEnabled`特性添加到 web.config`serviceHostingEnvironment`文件中的 < > 元素, 并将其设置为`true`, 如下面的示例中所示。  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 当在 IIS 下承载 WCF 服务时, IIS 基于包含该应用程序的虚拟目录的 URI 为你创建一个基址。 您可以通过 Internet 信息服务管理器添加使用相同协议的其他基址，从而向网站添加一个或多个绑定。 对于每个绑定，请指定协议（HTTP 或 HTTPS）、IP 地址、端口和主机名。 有关使用 Internet Information Services 管理器的详细信息, 请参阅[Iis 管理器 (iis 7)](https://go.microsoft.com/fwlink/?LinkId=164057)。 有关将绑定添加到网站的详细信息, 请参阅[创建网站 (IIS 7)](https://go.microsoft.com/fwlink/?LinkId=164060)  
  
 为同一站点指定多个基址会影响 WCF 帮助页的内容、导入架构和服务生成的 WSDL/MEX 信息。 WCF 帮助页显示用于生成可与服务进行通信的 WCF 客户端的命令行。 此命令行只包含在 IIS 绑定中为网站指定的第一个地址。 与导入方案时相似，只使用在 IIS 绑定中指定的第一个基址。 WSDL 和 MEX 数据包含在 IIS 绑定中指定的所有基址。  
  
> [!WARNING]
> 这意味着，如果某个服务有两个基址，其中一个供内部用户使用，另一个供外部用户使用，将在由该服务生成的 WSDL/MEX 信息中指定这两个基址。
