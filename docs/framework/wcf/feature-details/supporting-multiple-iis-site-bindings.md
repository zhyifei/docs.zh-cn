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
# <a name="supporting-multiple-iis-site-bindings"></a><span data-ttu-id="cc35c-102">支持多个 IIS 站点绑定</span><span class="sxs-lookup"><span data-stu-id="cc35c-102">Supporting Multiple IIS Site Bindings</span></span>
<span data-ttu-id="cc35c-103">在 Internet Information Services (IIS) 7.0 下承载 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务时，可能需要在同一站点上提供使用相同协议的多个基址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-103">When hosting a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service under Internet Information Services (IIS) 7.0, you may want to provide multiple base addresses that use the same protocol on the same site.</span></span> <span data-ttu-id="cc35c-104">这使得同一服务可以响应多个不同的 URI。</span><span class="sxs-lookup"><span data-stu-id="cc35c-104">This allows the same service to respond to a number of different URIs.</span></span> <span data-ttu-id="cc35c-105">这是有用的当你想要承载的服务在其侦听时http://www.contoso.com和http://contoso.com。在创建对于内部用户和外部用户使用不同基址的服务时，此功能也非常有用。</span><span class="sxs-lookup"><span data-stu-id="cc35c-105">This is useful when you want to host a service that listens on http://www.contoso.com and http://contoso.com. It is also useful to create a service that has a base address for internal users and a separate base address for external users.</span></span> <span data-ttu-id="cc35c-106">例如：http://internal.contoso.com和http://www.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="cc35c-106">For example: http://internal.contoso.com and http://www.contoso.com.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cc35c-107">此功能仅在使用 HTTP 协议时可用。</span><span class="sxs-lookup"><span data-stu-id="cc35c-107">This functionality is only available using the HTTP protocol.</span></span>  
  
## <a name="multiple-base-addresses"></a><span data-ttu-id="cc35c-108">多个基址</span><span class="sxs-lookup"><span data-stu-id="cc35c-108">Multiple Base Addresses</span></span>  
 <span data-ttu-id="cc35c-109">此功能仅适用于在 IIS 下承载的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务。</span><span class="sxs-lookup"><span data-stu-id="cc35c-109">This feature is only available to [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services that are hosted under IIS.</span></span> <span data-ttu-id="cc35c-110">默认情况下不启用此功能。</span><span class="sxs-lookup"><span data-stu-id="cc35c-110">This feature is not enabled by default.</span></span> <span data-ttu-id="cc35c-111">若要启用它必须添加`multipleSiteBindingsEnabled`属性设为 <`serviceHostingEnvironment`> 元素在 Web.config 文件并将其设置为`true`，下面的示例中所示。</span><span class="sxs-lookup"><span data-stu-id="cc35c-111">To enable it you must add the `multipleSiteBindingsEnabled` attribute to the <`serviceHostingEnvironment`> element in your Web.config file and set it to `true`, as shown in the following example.</span></span>  
  
```xml  
<serviceHostingEnvironment multipleSiteBindingsEnabled="true"/>  
```  
  
 <span data-ttu-id="cc35c-112">在 IIS 下承载 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 服务时，IIS 将根据包含应用程序的虚拟目录的 URI 创建一个基址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-112">When hosting a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service under IIS, IIS creates one base address for you based on the URI to the virtual directory that contains the application.</span></span> <span data-ttu-id="cc35c-113">您可以通过 Internet 信息服务管理器添加使用相同协议的其他基址，从而向网站添加一个或多个绑定。</span><span class="sxs-lookup"><span data-stu-id="cc35c-113">You can add additional base addresses that use the same protocol by using Internet Information Services Manager to add one or more bindings to your Web site.</span></span> <span data-ttu-id="cc35c-114">对于每个绑定，请指定协议（HTTP 或 HTTPS）、IP 地址、端口和主机名。</span><span class="sxs-lookup"><span data-stu-id="cc35c-114">For each binding specify a protocol (HTTP or HTTPS), an IP address, a port, and a host name.</span></span> <span data-ttu-id="cc35c-115">有关使用 Internet Information Services 管理器的详细信息，请参阅[IIS 管理器 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057)。</span><span class="sxs-lookup"><span data-stu-id="cc35c-115">For more information about using Internet Information Services Manager, see [IIS Manager (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164057).</span></span> <span data-ttu-id="cc35c-116">有关将绑定添加到站点的详细信息，请参阅[创建网站 (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)</span><span class="sxs-lookup"><span data-stu-id="cc35c-116">For more information about adding bindings to a site, see [Create a Web Site (IIS 7)](http://go.microsoft.com/fwlink/?LinkId=164060)</span></span>  
  
 <span data-ttu-id="cc35c-117">为同一站点指定多个基址会影响 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 帮助页的内容、导入架构和由服务生成的 WSDL/MEX 信息。</span><span class="sxs-lookup"><span data-stu-id="cc35c-117">Specifying multiple base addresses for the same site affects the content of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page, importing schema, and the WSDL/MEX information generated by the service.</span></span> <span data-ttu-id="cc35c-118">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 帮助页显示用于生成与服务通信的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端的命令行。</span><span class="sxs-lookup"><span data-stu-id="cc35c-118">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Help page displays the command line to use to generate a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that can communicate with the service.</span></span> <span data-ttu-id="cc35c-119">此命令行只包含在 IIS 绑定中为网站指定的第一个地址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-119">This command line contains only the first address specified in the IIS binding for the Web site.</span></span> <span data-ttu-id="cc35c-120">与导入方案时相似，只使用在 IIS 绑定中指定的第一个基址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-120">Similarly when importing schema, only the first base address specified in the IIS binding is used.</span></span> <span data-ttu-id="cc35c-121">WSDL 和 MEX 数据包含在 IIS 绑定中指定的所有基址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-121">WSDL and MEX data contain all the base addresses specified in the IIS bindings.</span></span>  
  
> [!WARNING]
>  <span data-ttu-id="cc35c-122">这意味着，如果某个服务有两个基址，其中一个供内部用户使用，另一个供外部用户使用，将在由该服务生成的 WSDL/MEX 信息中指定这两个基址。</span><span class="sxs-lookup"><span data-stu-id="cc35c-122">This means that if a service has two base addresses, one for internal users and one for external users, both are specified in the WSDL/MEX information generated by the service.</span></span>
