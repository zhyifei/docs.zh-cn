---
title: "正在配置服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
caps.latest.revision: "19"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 0783107d22f2d64dd8ba7936ce7d2a283f6d8317
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="configuring-services"></a><span data-ttu-id="5a7cd-102">正在配置服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-102">Configuring Services</span></span>
<span data-ttu-id="5a7cd-103">在设计和实现服务协定后，即可配置服务。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="5a7cd-104">在其中可以定义和自定义如何向客户端公开服务，包括指定可以找到服务的地址、服务用于发送和接收消息的传输和消息编码，以及服务需要的安全类型。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="5a7cd-105">此处使用的配置包括在代码中以强制方式或通过使用配置文件定义和自定义服务的各个方面的所有方法，例如指定其终结点地址、使用的传输及其安全方案。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="5a7cd-106">实际上，编写配置是 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 应用程序编程的主要部分。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-106">In practice, writing configuration is a major part of programming [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="5a7cd-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="5a7cd-107">In This Section</span></span>  
 [<span data-ttu-id="5a7cd-108">简化配置</span><span class="sxs-lookup"><span data-stu-id="5a7cd-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="5a7cd-109">从 [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]开始， [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 附带一个新的默认配置模型，该模型简化了 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 配置要求。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] comes with a new default configuration model that simplifies [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration requirements.</span></span> <span data-ttu-id="5a7cd-110">如果您没有为特定服务提供任何 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 配置，运行时将自动使用默认终结点、绑定和行为配置您的服务。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-110">If you do not provide any [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="5a7cd-111">使用配置文件配置服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="5a7cd-112">可使用 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 配置技术对 [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] 服务进行配置。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-112">A [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] service is configurable using the [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] configuration technology.</span></span> <span data-ttu-id="5a7cd-113">通常情况下，向承载 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 服务的 Internet 信息服务 (IIS) 网站的 Web.config 文件添加 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="5a7cd-114">这些元素允许您更改详细信息，例如每台计算机上的终结点地址（用于与服务进行通信的实际地址）。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="5a7cd-115">绑定</span><span class="sxs-lookup"><span data-stu-id="5a7cd-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="5a7cd-116">此外，[!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 包括几个绑定形式的系统提供的常见配置，这些绑定使您可以快速为客户端和服务的通信方式选择最基本的功能，例如所使用的传输、安全性和消息编码。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-116">In addition, [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="5a7cd-117">终结点</span><span class="sxs-lookup"><span data-stu-id="5a7cd-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="5a7cd-118">与所有通信[!INCLUDE[indigo2](../../../includes/indigo2-md.md)]服务是通过*终结点*的服务。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-118">All communication with a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="5a7cd-119">终结点包含协定、在绑定中指定的配置信息，以及指示查找服务或获取该服务相关信息的位置的地址。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="5a7cd-120">保护服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="5a7cd-121">使用 [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] 和现有安全机制，可以将保密性、完整性、身份验证和授权实现到任何服务中。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-121">Using [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="5a7cd-122">还可以审核安全成功和安全失败。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="5a7cd-123">创建 WS-I 基本配置文件 1.1 交互服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="5a7cd-124">WS-I 基本配置文件 1.1 规范中概述了部署服务的需求，该服务可与其他任何平台或操作系统上的服务和客户端进行互操作。</span><span class="sxs-lookup"><span data-stu-id="5a7cd-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="5a7cd-125">参考</span><span class="sxs-lookup"><span data-stu-id="5a7cd-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="5a7cd-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="5a7cd-126">Related Sections</span></span>  
 [<span data-ttu-id="5a7cd-127">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="5a7cd-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="5a7cd-128">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="5a7cd-129">托管服务</span><span class="sxs-lookup"><span data-stu-id="5a7cd-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="5a7cd-130">生成客户端</span><span class="sxs-lookup"><span data-stu-id="5a7cd-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="5a7cd-131">扩展性简介</span><span class="sxs-lookup"><span data-stu-id="5a7cd-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="5a7cd-132">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="5a7cd-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="5a7cd-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a7cd-133">See Also</span></span>  
 [<span data-ttu-id="5a7cd-134">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="5a7cd-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)  
 [<span data-ttu-id="5a7cd-135">概念性概述</span><span class="sxs-lookup"><span data-stu-id="5a7cd-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)  
 [<span data-ttu-id="5a7cd-136">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="5a7cd-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
