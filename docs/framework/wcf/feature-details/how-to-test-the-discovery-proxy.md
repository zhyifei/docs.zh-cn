---
title: 如何：测试发现代理
ms.date: 03/30/2017
ms.assetid: d96e3fa2-3c42-4e5d-8244-2694081bdc32
ms.openlocfilehash: 856b86241299585b80d58c6d37582463736a5935
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61972908"
---
# <a name="how-to-test-the-discovery-proxy"></a><span data-ttu-id="2948d-102">如何：测试发现代理</span><span class="sxs-lookup"><span data-stu-id="2948d-102">How to: Test the Discovery Proxy</span></span>
<span data-ttu-id="2948d-103">本主题是演示如何实现发现代理的四个主题中的第四个。</span><span class="sxs-lookup"><span data-stu-id="2948d-103">This is the fourth of four topics that shows how to implement a discovery proxy.</span></span> <span data-ttu-id="2948d-104">在上一主题中，[如何：实现使用发现代理查找服务的客户端应用程序](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)，实现使用发现代理查找服务，然后调用该服务的 WCF 客户端应用。</span><span class="sxs-lookup"><span data-stu-id="2948d-104">In the previous topic, [How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md), you implemented a WCF client application that uses the discovery proxy to find a service and then calls the service.</span></span> <span data-ttu-id="2948d-105">本主题说明如何验证发现代理、服务以及客户端应用程序是否按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="2948d-105">This topic describes how to verify the discovery proxy, the service, and the client application work as expected.</span></span>  
  
### <a name="run-the-discovery-proxy"></a><span data-ttu-id="2948d-106">运行发现代理</span><span class="sxs-lookup"><span data-stu-id="2948d-106">Run the Discovery Proxy</span></span>  
  
1. <span data-ttu-id="2948d-107">作为管理员打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="2948d-107">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="2948d-108">可能会看到一个对话框，指出：Windows 防火墙已阻止此程序的某些功能。</span><span class="sxs-lookup"><span data-stu-id="2948d-108">You may see a dialog that says: Windows Firewall has blocked some features of this program.</span></span> <span data-ttu-id="2948d-109">如果看到此消息，请单击**解除阻止**按钮。</span><span class="sxs-lookup"><span data-stu-id="2948d-109">If you see this message, click the **Unblock** button.</span></span>  
  
3. <span data-ttu-id="2948d-110">在命令提示中，运行发现代理 DiscoveryProxy.exe。</span><span class="sxs-lookup"><span data-stu-id="2948d-110">Within the command prompt, run the discovery proxy, DiscoveryProxy.exe.</span></span>  
  
4. <span data-ttu-id="2948d-111">应用程序应显示以下文本：`Proxy started. Hit Enter to exit`。</span><span class="sxs-lookup"><span data-stu-id="2948d-111">The application should display the following text: `Proxy started. Hit Enter to exit`.</span></span>  
  
### <a name="run-the-discoverable-service"></a><span data-ttu-id="2948d-112">运行可检测服务</span><span class="sxs-lookup"><span data-stu-id="2948d-112">Run the Discoverable Service</span></span>  
  
1. <span data-ttu-id="2948d-113">作为管理员打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="2948d-113">Open a command prompt as an administrator.</span></span>  
  
2. <span data-ttu-id="2948d-114">在命令提示中，运行 Service.exe 可检测服务。</span><span class="sxs-lookup"><span data-stu-id="2948d-114">Within the command prompt, run the Service.exe discoverable service.</span></span>  
  
3. <span data-ttu-id="2948d-115">DiscoveryProxy.exe 应显示以下文本： `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` 。</span><span class="sxs-lookup"><span data-stu-id="2948d-115">The DiscoveryProxy.exe should display the following text: `******* Adding the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 3.******* Done *******` .</span></span>  
  
### <a name="run-the-client-application"></a><span data-ttu-id="2948d-116">运行客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2948d-116">Run the Client Application</span></span>  
  
1. <span data-ttu-id="2948d-117">打开命令提示。</span><span class="sxs-lookup"><span data-stu-id="2948d-117">Open a command prompt.</span></span>  
  
2. <span data-ttu-id="2948d-118">在命令提示中，运行 client.exe 应用程序。</span><span class="sxs-lookup"><span data-stu-id="2948d-118">Within the command prompt, run the client.exe application.</span></span>  
  
3. <span data-ttu-id="2948d-119">几秒钟后客户端应用程序显示以下文本：连接到 [服务终结点]。</span><span class="sxs-lookup"><span data-stu-id="2948d-119">After a few seconds the client application displays the following text: Connecting to [Service-Endpoint].</span></span>  
  
4. <span data-ttu-id="2948d-120">然后，service.exe 应显示以下文本：请求已收到的问候语，我将响应。</span><span class="sxs-lookup"><span data-stu-id="2948d-120">The service.exe should then display the following text: Greeting request received, I will respond.</span></span>  
  
5. <span data-ttu-id="2948d-121">然后，client.exe 应显示以下文本：客户端 hello ！</span><span class="sxs-lookup"><span data-stu-id="2948d-121">The client.exe should then display the following text: Hello Client!</span></span>  
  
### <a name="shut-down-the-applications"></a><span data-ttu-id="2948d-122">关闭应用程序</span><span class="sxs-lookup"><span data-stu-id="2948d-122">Shut Down the Applications</span></span>  
  
1. <span data-ttu-id="2948d-123">关闭客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="2948d-123">Shut down the client application.</span></span>  
  
2. <span data-ttu-id="2948d-124">关闭服务。</span><span class="sxs-lookup"><span data-stu-id="2948d-124">Shut down the service.</span></span> <span data-ttu-id="2948d-125">此时，发现代理显示以下文本：`******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`。</span><span class="sxs-lookup"><span data-stu-id="2948d-125">The discovery proxy displays the following text: `******* Removing the following service: ** [Service Contract Name] ** [Service Endpoint Addr] 2.3.******* Done *******`.</span></span>  
  
3. <span data-ttu-id="2948d-126">关闭发现代理。</span><span class="sxs-lookup"><span data-stu-id="2948d-126">Shut down the discovery proxy.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2948d-127">请参阅</span><span class="sxs-lookup"><span data-stu-id="2948d-127">See also</span></span>

- [<span data-ttu-id="2948d-128">WCF 发现概述</span><span class="sxs-lookup"><span data-stu-id="2948d-128">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [<span data-ttu-id="2948d-129">如何：实现发现代理</span><span class="sxs-lookup"><span data-stu-id="2948d-129">How to: Implement a Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/how-to-implement-a-discovery-proxy.md)
- [<span data-ttu-id="2948d-130">如何：实现向发现代理注册的可发现服务</span><span class="sxs-lookup"><span data-stu-id="2948d-130">How to: Implement a Discoverable Service that Registers with the Discovery Proxy</span></span>](../../../../docs/framework/wcf/feature-details/discoverable-service-that-registers-with-the-discovery-proxy.md)
- [<span data-ttu-id="2948d-131">如何：实现使用发现代理查找服务的客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="2948d-131">How to: Implement a Client Application that Uses the Discovery Proxy to Find a Service</span></span>](../../../../docs/framework/wcf/feature-details/client-app-discovery-proxy-to-find-a-service.md)
