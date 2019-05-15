---
title: 配置 WCF 服务
ms.date: 03/30/2017
helpviewer_keywords:
- configuration [WCF]
ms.assetid: beac771e-f28e-4f84-9ff1-ad9251c726d3
ms.openlocfilehash: e8ac62809b1269ae810f026c003c7611b3ec548c
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593325"
---
# <a name="configuring-wcf-services"></a><span data-ttu-id="de5b6-102">配置 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-102">Configuring WCF services</span></span>

<span data-ttu-id="de5b6-103">在设计和实现服务协定后，即可配置服务。</span><span class="sxs-lookup"><span data-stu-id="de5b6-103">Once you have designed and implemented your service contract, you are ready to configure your service.</span></span> <span data-ttu-id="de5b6-104">在其中可以定义和自定义如何向客户端公开服务，包括指定可以找到服务的地址、服务用于发送和接收消息的传输和消息编码，以及服务需要的安全类型。</span><span class="sxs-lookup"><span data-stu-id="de5b6-104">This is where you define and customize how your service is exposed to clients, including specifying the address where it can be found, the transport and message encoding it uses to send and receive messages, and the type of security it requires.</span></span>  
  
 <span data-ttu-id="de5b6-105">此处使用的配置包括在代码中以强制方式或通过使用配置文件定义和自定义服务的各个方面的所有方法，例如指定其终结点地址、使用的传输及其安全方案。</span><span class="sxs-lookup"><span data-stu-id="de5b6-105">Configuration as used here includes all the ways, imperatively in code or by using a configuration file, in which you can define and customize the various aspects of a service, such as specifying its endpoint addresses, the transports used, and its security schemes.</span></span> <span data-ttu-id="de5b6-106">在实践中，编写配置是一个较大编程 WCF 应用程序的一部分。</span><span class="sxs-lookup"><span data-stu-id="de5b6-106">In practice, writing configuration is a major part of programming WCF applications.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="de5b6-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="de5b6-107">In This Section</span></span>  
 [<span data-ttu-id="de5b6-108">简化配置</span><span class="sxs-lookup"><span data-stu-id="de5b6-108">Simplified Configuration</span></span>](../../../docs/framework/wcf/simplified-configuration.md)  
 <span data-ttu-id="de5b6-109">从开始[!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)]，WCF 附带了一个新的默认配置模型，简化了 WCF 配置要求。</span><span class="sxs-lookup"><span data-stu-id="de5b6-109">Starting with [!INCLUDE[netfx40_long](../../../includes/netfx40-long-md.md)], WCF comes with a new default configuration model that simplifies WCF configuration requirements.</span></span> <span data-ttu-id="de5b6-110">如果未提供针对特定服务的任何 WCF 配置，运行时自动使用默认终结点、 绑定和行为配置你的服务。</span><span class="sxs-lookup"><span data-stu-id="de5b6-110">If you do not provide any WCF configuration for a particular service, the runtime automatically configures your service with default endpoints, bindings, and behaviors.</span></span>  
  
 [<span data-ttu-id="de5b6-111">使用配置文件配置服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-111">Configuring Services Using Configuration Files</span></span>](../../../docs/framework/wcf/configuring-services-using-configuration-files.md)  
 <span data-ttu-id="de5b6-112">Windows Communication Foundation (WCF) 服务是可配置使用.NET Framework 技术的配置。</span><span class="sxs-lookup"><span data-stu-id="de5b6-112">A Windows Communication Foundation (WCF) service is configurable using the .NET Framework configuration technology.</span></span> <span data-ttu-id="de5b6-113">大多数情况下，XML 元素添加到托管 WCF 服务的 Internet 信息服务 (IIS) 网站的 Web.config 文件中。</span><span class="sxs-lookup"><span data-stu-id="de5b6-113">Most commonly, XML elements are added to the Web.config file for an Internet Information Services (IIS) site that hosts a WCF service.</span></span> <span data-ttu-id="de5b6-114">这些元素允许您更改详细信息，例如每台计算机上的终结点地址（用于与服务进行通信的实际地址）。</span><span class="sxs-lookup"><span data-stu-id="de5b6-114">The elements allow you to change details, such as the endpoint addresses (the actual addresses used to communicate with the service) on a machine-by-machine basis.</span></span>  
  
 [<span data-ttu-id="de5b6-115">绑定</span><span class="sxs-lookup"><span data-stu-id="de5b6-115">Bindings</span></span>](../../../docs/framework/wcf/bindings.md)  
 <span data-ttu-id="de5b6-116">此外，WCF 绑定，您可以快速选择客户端和服务通信的方式，例如传输、 安全性和消息编码使用的最基本功能的窗体中包含多个系统提供的常见配置。</span><span class="sxs-lookup"><span data-stu-id="de5b6-116">In addition, WCF includes several system-provided common configurations in the form of bindings that allow you to quickly select the most basic features for how a client and service communicate, such as the transports, security, and message encodings used.</span></span>  
  
 [<span data-ttu-id="de5b6-117">终结点</span><span class="sxs-lookup"><span data-stu-id="de5b6-117">Endpoints</span></span>](../../../docs/framework/wcf/endpoints.md)  
 <span data-ttu-id="de5b6-118">通过与 WCF 服务的所有通信都进行*终结点*的服务。</span><span class="sxs-lookup"><span data-stu-id="de5b6-118">All communication with a WCF service occurs through the *endpoints* of the service.</span></span> <span data-ttu-id="de5b6-119">终结点包含协定、在绑定中指定的配置信息，以及指示查找服务或获取该服务相关信息的位置的地址。</span><span class="sxs-lookup"><span data-stu-id="de5b6-119">Endpoints contain the contract, the configuration information that is specified in the bindings, and the addresses that indicate where to find the service or where to obtain information about the service.</span></span>  
  
 [<span data-ttu-id="de5b6-120">保护服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-120">Securing Services</span></span>](../../../docs/framework/wcf/securing-services.md)  
 <span data-ttu-id="de5b6-121">使用 WCF 和现有安全机制，可以实现保密性、 完整性、 身份验证和授权到任何服务。</span><span class="sxs-lookup"><span data-stu-id="de5b6-121">Using WCF and existing security mechanisms, you can implement confidentiality, integrity, authentication, and authorization into any service.</span></span> <span data-ttu-id="de5b6-122">还可以审核安全成功和安全失败。</span><span class="sxs-lookup"><span data-stu-id="de5b6-122">You can also audit for security successes and failures.</span></span>  
  
 [<span data-ttu-id="de5b6-123">创建 WS-I 基本配置文件 1.1 交互服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-123">Creating WS-I Basic Profile 1.1 Interoperable Services</span></span>](../../../docs/framework/wcf/creating-ws-i-basic-profile-1-1-interoperable-services.md)  
 <span data-ttu-id="de5b6-124">WS-I 基本配置文件 1.1 规范中概述了部署服务的需求，该服务可与其他任何平台或操作系统上的服务和客户端进行互操作。</span><span class="sxs-lookup"><span data-stu-id="de5b6-124">The requirements for deploying a service that is interoperable with services and clients on any other platform or operating system are outlined in the WS-I Basic Profile 1.1 specification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="de5b6-125">参考</span><span class="sxs-lookup"><span data-stu-id="de5b6-125">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
## <a name="related-sections"></a><span data-ttu-id="de5b6-126">相关章节</span><span class="sxs-lookup"><span data-stu-id="de5b6-126">Related Sections</span></span>  
 [<span data-ttu-id="de5b6-127">基本编程生命周期</span><span class="sxs-lookup"><span data-stu-id="de5b6-127">Basic Programming Lifecycle</span></span>](../../../docs/framework/wcf/basic-programming-lifecycle.md)  
  
 [<span data-ttu-id="de5b6-128">设计和实现服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-128">Designing and Implementing Services</span></span>](../../../docs/framework/wcf/designing-and-implementing-services.md)  
  
 [<span data-ttu-id="de5b6-129">托管服务</span><span class="sxs-lookup"><span data-stu-id="de5b6-129">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
  
 [<span data-ttu-id="de5b6-130">生成客户端</span><span class="sxs-lookup"><span data-stu-id="de5b6-130">Building Clients</span></span>](../../../docs/framework/wcf/building-clients.md)  
  
 [<span data-ttu-id="de5b6-131">扩展性简介</span><span class="sxs-lookup"><span data-stu-id="de5b6-131">Introduction to Extensibility</span></span>](../../../docs/framework/wcf/introduction-to-extensibility.md)  
  
 [<span data-ttu-id="de5b6-132">管理和诊断</span><span class="sxs-lookup"><span data-stu-id="de5b6-132">Administration and Diagnostics</span></span>](../../../docs/framework/wcf/diagnostics/index.md)  
  
## <a name="see-also"></a><span data-ttu-id="de5b6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="de5b6-133">See also</span></span>

- [<span data-ttu-id="de5b6-134">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="de5b6-134">Basic WCF Programming</span></span>](../../../docs/framework/wcf/basic-wcf-programming.md)
- [<span data-ttu-id="de5b6-135">概念性概述</span><span class="sxs-lookup"><span data-stu-id="de5b6-135">Conceptual Overview</span></span>](../../../docs/framework/wcf/conceptual-overview.md)
- [<span data-ttu-id="de5b6-136">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="de5b6-136">WCF Feature Details</span></span>](../../../docs/framework/wcf/feature-details/index.md)
