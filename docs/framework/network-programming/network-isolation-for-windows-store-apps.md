---
title: "Windows 应用商店应用的网络隔离"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b064497c-d956-46b8-838d-7a0223c7e200
caps.latest.revision: "7"
author: mcleblanc
ms.author: markl
manager: markl
ms.workload: dotnet
ms.openlocfilehash: ba7e480f50d3a339648229f17152eb28b28ec159
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="network-isolation-for-windows-store-apps"></a><span data-ttu-id="c24cf-102">Windows 应用商店应用的网络隔离</span><span class="sxs-lookup"><span data-stu-id="c24cf-102">Network Isolation for Windows Store Apps</span></span>
<span data-ttu-id="c24cf-103"><xref:System.Net>、<xref:System.Net.Http> 和 <xref:System.Net.Http.Headers> 命名空间中的类可用于开发 Windows 应用商店应用或桌面应用。</span><span class="sxs-lookup"><span data-stu-id="c24cf-103">Classes in the <xref:System.Net>,  <xref:System.Net.Http>, and <xref:System.Net.Http.Headers> namespaces can be used to develop Windows Store  apps  or desktop apps.</span></span> <span data-ttu-id="c24cf-104">在 Windows 应用商店应用中使用时，这些命名空间中的类会受到网络隔离（[!INCLUDE[win8](../../../includes/win8-md.md)] 使用的应用程序安全模型的一部分）的影响。</span><span class="sxs-lookup"><span data-stu-id="c24cf-104">When used in a Windows Store app, classes in these namespaces are affected by network isolation, part of the application security model used by the [!INCLUDE[win8](../../../includes/win8-md.md)].</span></span> <span data-ttu-id="c24cf-105">必须在应用清单中为 Windows 应用商店应用启用适当的网络功能，以便系统允许网络访问。</span><span class="sxs-lookup"><span data-stu-id="c24cf-105">The appropriate network capabilities must be enabled in the app manifest for a Windows Store app for the system to allow network access.</span></span>  
  
## <a name="checklist-for-network-isolation"></a><span data-ttu-id="c24cf-106">网络隔离的核对清单</span><span class="sxs-lookup"><span data-stu-id="c24cf-106">Checklist for Network Isolation</span></span>  
 <span data-ttu-id="c24cf-107">使用此清单以确保为 Windows 应用商店应用配置了网络隔离。</span><span class="sxs-lookup"><span data-stu-id="c24cf-107">Use this checklist to be sure that network isolation is configured for your Windows Store app.</span></span>  
  
1.  <span data-ttu-id="c24cf-108">确定应用所需网络访问请求的方向。</span><span class="sxs-lookup"><span data-stu-id="c24cf-108">Determine the direction of network access requests needed by the app.</span></span> <span data-ttu-id="c24cf-109">这可以是出站客户端发起的请求或入站主动提供的请求，也可以是这两种网络请求类型的组合。</span><span class="sxs-lookup"><span data-stu-id="c24cf-109">This can be either outbound client-initiated requests or inbound unsolicited requests or it could be a combination of both of these network request types.</span></span>  
  
2.  <span data-ttu-id="c24cf-110">确定该应用将与之通信的网络资源类型。</span><span class="sxs-lookup"><span data-stu-id="c24cf-110">Determine the type of network resources that that app will communicate with.</span></span> <span data-ttu-id="c24cf-111">应用可能需要与家庭或工作网络上受信任的资源进行通信。</span><span class="sxs-lookup"><span data-stu-id="c24cf-111">An app may need to communicate with trusted resources on a Home or Work network.</span></span> <span data-ttu-id="c24cf-112">应用可能需要与 Internet 上的资源进行通信。</span><span class="sxs-lookup"><span data-stu-id="c24cf-112">An app might need to communicate with resources on the Internet.</span></span> <span data-ttu-id="c24cf-113">应用可能需要访问两种类型的网络资源。</span><span class="sxs-lookup"><span data-stu-id="c24cf-113">An app might need access to both types of network resources.</span></span>  
  
3.  <span data-ttu-id="c24cf-114">在应用程序清单中配置最低要求的网络隔离功能。</span><span class="sxs-lookup"><span data-stu-id="c24cf-114">Configure the minimum-required networking isolation capabilities in the app manifest.</span></span>  
  
4.  <span data-ttu-id="c24cf-115">部署并运行应用，使用为故障排除提供的网络隔离工具进行测试。</span><span class="sxs-lookup"><span data-stu-id="c24cf-115">Deploy and run your app to test it using the network isolation tools provided for troubleshooting.</span></span>  
  
 <span data-ttu-id="c24cf-116">有关如何配置用于排除网络隔离的网络功能和隔离工具的详细信息，请参阅 [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] 开发人员文档中的[如何配置网络隔离功能](http://go.microsoft.com/fwlink/?LinkID=228265)。</span><span class="sxs-lookup"><span data-stu-id="c24cf-116">For more detailed information on how to configure network capabilities and isolation tools used for troubleshooting network isolation, see [How to configure network isolation capabilities](http://go.microsoft.com/fwlink/?LinkID=228265) in the [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] developer documentation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c24cf-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="c24cf-117">See Also</span></span>  
 [<span data-ttu-id="c24cf-118">连接到 web 服务</span><span class="sxs-lookup"><span data-stu-id="c24cf-118">Connecting to a web service</span></span>](http://go.microsoft.com/fwlink/?LinkID=245696)  
 [<span data-ttu-id="c24cf-119">指南和网络隔离的核对清单</span><span class="sxs-lookup"><span data-stu-id="c24cf-119">Guidelines and checklist for network isolation</span></span>](http://go.microsoft.com/fwlink/?LinkID=228265)  
 [<span data-ttu-id="c24cf-120">快速入门： 使用 HttpClient 进行连接</span><span class="sxs-lookup"><span data-stu-id="c24cf-120">Quickstart: Connecting using HttpClient</span></span>](http://go.microsoft.com/fwlink/?LinkId=245697)  
 [<span data-ttu-id="c24cf-121">如何使用 HttpClient 处理程序</span><span class="sxs-lookup"><span data-stu-id="c24cf-121">How to use HttpClient handlers</span></span>](http://go.microsoft.com/fwlink/?LinkId=245699)  
 [<span data-ttu-id="c24cf-122">如何保护 HttpClient 连接</span><span class="sxs-lookup"><span data-stu-id="c24cf-122">How to secure HttpClient connections</span></span>](http://go.microsoft.com/fwlink/?LinkId=245698)  
 [<span data-ttu-id="c24cf-123">HttpClient 示例</span><span class="sxs-lookup"><span data-stu-id="c24cf-123">HttpClient Sample</span></span>](http://go.microsoft.com/fwlink/?LinkId=242550)
