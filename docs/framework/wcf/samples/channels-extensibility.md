---
title: "通道扩展性"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4cc3b20b-778a-4ae8-b58c-a3822fb13065
caps.latest.revision: "3"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 7e0cf92edc4ec05df3e5e8c25b90bcf253e94ed6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="channels-extensibility"></a><span data-ttu-id="a7166-102">通道扩展性</span><span class="sxs-lookup"><span data-stu-id="a7166-102">Channels Extensibility</span></span>
<span data-ttu-id="a7166-103">本节包含演示自定义通道的示例。</span><span class="sxs-lookup"><span data-stu-id="a7166-103">This section contains samples that demonstrate custom channels.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a7166-104">本节内容</span><span class="sxs-lookup"><span data-stu-id="a7166-104">In This Section</span></span>  
 [<span data-ttu-id="a7166-105">本地通道</span><span class="sxs-lookup"><span data-stu-id="a7166-105">Local Channel</span></span>](../../../../docs/framework/wcf/samples/local-channel.md)  
 <span data-ttu-id="a7166-106">演示本地通道，这是用于在相同应用程序域内进行通信的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 传输通道。</span><span class="sxs-lookup"><span data-stu-id="a7166-106">Demonstrates the local channel, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] transport channel that is used for communication within the same application domain.</span></span>  
  
 [<span data-ttu-id="a7166-107">可靠安全配置文件</span><span class="sxs-lookup"><span data-stu-id="a7166-107">Reliable Secure Profile</span></span>](../../../../docs/framework/wcf/samples/reliable-secure-profile.md)  
 <span data-ttu-id="a7166-108">演示如何编写 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 和可靠安全配置文件 (RSP)。</span><span class="sxs-lookup"><span data-stu-id="a7166-108">Demonstrates how to compose [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] and Reliable Secure Profile (RSP).</span></span>  
  
 [<span data-ttu-id="a7166-109">自定义通道调度程序</span><span class="sxs-lookup"><span data-stu-id="a7166-109">Custom Channel Dispatcher</span></span>](../../../../docs/framework/wcf/samples/custom-channel-dispatcher.md)  
 <span data-ttu-id="a7166-110">演示如何通过直接实现 <xref:System.ServiceModel.ServiceHostBase> 以自定义方式生成通道堆栈，以及如何在 Web 主机环境中创建自定义通道调度程序。</span><span class="sxs-lookup"><span data-stu-id="a7166-110">Demonstrates how to build the channel stack in a custom way by implementing <xref:System.ServiceModel.ServiceHostBase> directly and how to create a custom channel dispatcher in Web host environment.</span></span>  
  
 [<span data-ttu-id="a7166-111">通道分块</span><span class="sxs-lookup"><span data-stu-id="a7166-111">Chunking Channel</span></span>](../../../../docs/framework/wcf/samples/chunking-channel.md)  
 <span data-ttu-id="a7166-112">演示如何限制在使用 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 发送大型消息时用于缓冲这些消息的内存占用量。</span><span class="sxs-lookup"><span data-stu-id="a7166-112">Demonstrates how to limit the amount of memory used to buffer large messages sent using [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
 [<span data-ttu-id="a7166-113">HTTP 确认通道</span><span class="sxs-lookup"><span data-stu-id="a7166-113">HTTP Acknowledgement Channel</span></span>](../../../../docs/framework/wcf/samples/http-acknowledgement-channel.md)  
 <span data-ttu-id="a7166-114">演示更改单向消息传递模式的分层通道。</span><span class="sxs-lookup"><span data-stu-id="a7166-114">Demonstrates a layered channel which changes the one-way messaging pattern.</span></span>  
  
 [<span data-ttu-id="a7166-115">HttpCookieSession</span><span class="sxs-lookup"><span data-stu-id="a7166-115">HttpCookieSession</span></span>](../../../../docs/framework/wcf/samples/httpcookiesession.md)  
 <span data-ttu-id="a7166-116">演示如何生成自定义协议通道，以便使用 HTTP Cookie 进行会话管理。</span><span class="sxs-lookup"><span data-stu-id="a7166-116">Demonstrates how to build a custom protocol channel to use HTTP cookies for session management.</span></span>  
  
 [<span data-ttu-id="a7166-117">自定义消息拦截器</span><span class="sxs-lookup"><span data-stu-id="a7166-117">Custom Message Interceptor</span></span>](../../../../docs/framework/wcf/samples/custom-message-interceptor.md)  
 <span data-ttu-id="a7166-118">演示如何实现可创建通道工厂和通道侦听器的自定义绑定元素，以便在运行时堆栈的特定点截获所有传入和传出消息。</span><span class="sxs-lookup"><span data-stu-id="a7166-118">Demonstrates how to implement a custom binding element that creates channel factories and channel listeners to intercept all incoming and outgoing messages at a particular point in the run-time stack.</span></span>
