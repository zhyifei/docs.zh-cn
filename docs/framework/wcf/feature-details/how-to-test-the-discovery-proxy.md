---
title: "如何：测试发现代理"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 55a7fe72b34fc8c099d921e7e295c184817825a3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="fb2f2-102">如何：测试发现代理</span><span class="sxs-lookup"><span data-stu-id="fb2f2-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="fb2f2-103">本主题是演示如何实现发现代理的四个主题中的第四个。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="fb2f2-104">在前面的主题中，[如何： 实现的客户端应用程序使用发现代理查找服务](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)，你实现[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端应用程序使用发现代理查找服务，然后调用服务。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="fb2f2-105">本主题说明如何验证发现代理、服务以及客户端应用程序是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="fb2f2-106">运行发现代理</span><span class="sxs-lookup"><span data-stu-id="fb2f2-106">Run the Discovery Proxy</span></span>  
  
1.  <span data-ttu-id="fb2f2-107">作为管理员打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-107">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="fb2f2-108">您可能会看到显示如下内容的对话框：Windows 防火墙已经阻止此程序的部分功能。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="fb2f2-109">如果你看到此消息，请单击**解除阻止**按钮。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-109">If you see this message, click the **Unblock** button.</span></span>  
  
3.  <span data-ttu-id="fb2f2-110">在命令提示中，运行发现代理 DiscoveryProxy.exe。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4.  <span data-ttu-id="fb2f2-111">应用程序应显示以下文本：`Proxy started. Hit Enter to exit`。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="fb2f2-112">运行可检测服务</span><span class="sxs-lookup"><span data-stu-id="fb2f2-112">Run the Discoverable Service</span></span>  
  
1.  <span data-ttu-id="fb2f2-113">作为管理员打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-113">Open a command prompt as an administrator.</span></span>  
  
2.  <span data-ttu-id="fb2f2-114">在命令提示中，运行 Service.exe 可检测服务。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3.  <span data-ttu-id="fb2f2-115">DiscoveryProxy.exe 应显示以下文本： `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` 。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="fb2f2-116">运行客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fb2f2-116">Run the Client Application</span></span>  
  
1.  <span data-ttu-id="fb2f2-117">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-117">Open a command prompt.</span></span>  
  
2.  <span data-ttu-id="fb2f2-118">在命令提示中，运行 client.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-118">Within the command prompt, run the client.exe application.</span></span>  
  
3.  <span data-ttu-id="fb2f2-119">几秒钟后，客户端应用程序显示以下文本：Connecting to [Service-Endpoint]。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4.  <span data-ttu-id="fb2f2-120">然后，service.exe 应显示以下文本：Greeting request received, I will respond.</span><span class="sxs-lookup"><span data-stu-id="fb2f2-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5.  <span data-ttu-id="fb2f2-121">然后，client.exe 应显示以下文本：Hello Client!</span><span class="sxs-lookup"><span data-stu-id="fb2f2-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="fb2f2-122">关闭应用程序</span><span class="sxs-lookup"><span data-stu-id="fb2f2-122">Shut Down the Applications</span></span>  
  
1.  <span data-ttu-id="fb2f2-123">关闭客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-123">Shut down the client application.</span></span>  
  
2.  <span data-ttu-id="fb2f2-124">关闭服务。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-124">Shut down the service.</span></span> <span data-ttu-id="fb2f2-125">此时，发现代理显示以下文本：`******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3.  <span data-ttu-id="fb2f2-126">关闭发现代理。</span><span class="sxs-lookup"><span data-stu-id="fb2f2-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2f2-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb2f2-127">See Also</span></span>  
 [<span data-ttu-id="fb2f2-128">WCF Discovery 概述</span><span class="sxs-lookup"><span data-stu-id="fb2f2-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="fb2f2-129">如何： 实现发现代理</span><span class="sxs-lookup"><span data-stu-id="fb2f2-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)  
 [<span data-ttu-id="fb2f2-130">如何： 实现向发现代理注册的可发现服务</span><span class="sxs-lookup"><span data-stu-id="fb2f2-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)  
 [<span data-ttu-id="fb2f2-131">如何： 实现使用发现代理查找服务的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="fb2f2-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
