---
title: "开发通道"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0513af9f-a0c2-457b-9a50-5b6bfee48513
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 42c89ae71078a3ddfbe7e85273a6f62879781c80
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="developing-channels"></a><span data-ttu-id="3511e-102">开发通道</span><span class="sxs-lookup"><span data-stu-id="3511e-102">Developing Channels</span></span>
<span data-ttu-id="3511e-103">开发可以与 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 应用程序层一起使用的协议或传输通道需要多个步骤。</span><span class="sxs-lookup"><span data-stu-id="3511e-103">To develop a protocol or transport channel that can be used with the [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] application layer requires several steps.</span></span> <span data-ttu-id="3511e-104">本主题介绍这些步骤并为您指出特定主题以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="3511e-104">This topic describes those steps and points you to specific topics for more information.</span></span> <span data-ttu-id="3511e-105">若要了解通道模型和本主题中提到的各种类型，请参阅[通道模型概述](../../../../docs/framework/wcf/extending/channel-model-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-105">To understand the channel model and the various types that are mentioned in this topic, see [Channel Model Overview](../../../../docs/framework/wcf/extending/channel-model-overview.md).</span></span> <span data-ttu-id="3511e-106">有关完整的传输通道示例，请参阅[传输： UDP](../../../../docs/framework/wcf/samples/transport-udp.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-106">For a complete transport channel sample, see [Transport: UDP](../../../../docs/framework/wcf/samples/transport-udp.md).</span></span>  
  
## <a name="the-channel-development-task-list"></a><span data-ttu-id="3511e-107">通道开发任务列表</span><span class="sxs-lookup"><span data-stu-id="3511e-107">The Channel Development Task List</span></span>  
 <span data-ttu-id="3511e-108">创建用户定义的通道的步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="3511e-108">The steps to create a user-defined channel are as follows.</span></span> <span data-ttu-id="3511e-109">所有通道必须：</span><span class="sxs-lookup"><span data-stu-id="3511e-109">All channels must:</span></span>  
  
1.  <span data-ttu-id="3511e-110">确定您的 <xref:System.ServiceModel.Channels.IOutputChannel> 和 <xref:System.ServiceModel.Channels.IInputChannel> 将支持哪种通道消息交换模式（<xref:System.ServiceModel.Channels.IDuplexChannel>、<xref:System.ServiceModel.Channels.IRequestChannel>、<xref:System.ServiceModel.Channels.IReplyChannel>、<xref:System.ServiceModel.Channels.IChannelFactory> 或 <xref:System.ServiceModel.Channels.IChannelListener>），以及该模式是否支持这些接口的会话变体。</span><span class="sxs-lookup"><span data-stu-id="3511e-110">Decide which of the channel Message Exchange Patterns (<xref:System.ServiceModel.Channels.IOutputChannel>, <xref:System.ServiceModel.Channels.IInputChannel>, <xref:System.ServiceModel.Channels.IDuplexChannel>, <xref:System.ServiceModel.Channels.IRequestChannel>, or <xref:System.ServiceModel.Channels.IReplyChannel>) your <xref:System.ServiceModel.Channels.IChannelFactory> and <xref:System.ServiceModel.Channels.IChannelListener> will support, as well as whether it will support the sessionful variations of these interfaces.</span></span> <span data-ttu-id="3511e-111">有关详细信息，请参阅[选择消息交换模式](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-111">For details, see [Choosing a Message Exchange Pattern](../../../../docs/framework/wcf/extending/choosing-a-message-exchange-pattern.md).</span></span>  
  
2.  <span data-ttu-id="3511e-112">创建支持您的消息交换模式的通道工厂和侦听器（<xref:System.ServiceModel.Channels.IChannelFactory> 和 <xref:System.ServiceModel.Channels.IChannelListener>）。</span><span class="sxs-lookup"><span data-stu-id="3511e-112">Create a channel factory and listener (<xref:System.ServiceModel.Channels.IChannelFactory> and <xref:System.ServiceModel.Channels.IChannelListener>) that support your message exchange pattern.</span></span> <span data-ttu-id="3511e-113">有关开发工厂的详细信息，请参阅[客户端： 通道工厂和通道](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-113">For details about developing factories, see [Client: Channel Factories and Channels](../../../../docs/framework/wcf/extending/client-channel-factories-and-channels.md).</span></span> <span data-ttu-id="3511e-114">有关开发侦听器的详细信息，请参阅[服务： 通道侦听器和通道](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-114">For details about developing listeners, see [Service: Channel Listeners and Channels](../../../../docs/framework/wcf/extending/service-channel-listeners-and-channels.md).</span></span>  
  
3.  <span data-ttu-id="3511e-115">确保将任何特定于网络的异常规范化为 <xref:System.TimeoutException?displayProperty=nameWithType> 或 <xref:System.ServiceModel.CommunicationException> 的相应派生类。</span><span class="sxs-lookup"><span data-stu-id="3511e-115">Ensure that any network-specific exceptions are normalized to either <xref:System.TimeoutException?displayProperty=nameWithType> or the appropriate derived class of <xref:System.ServiceModel.CommunicationException>.</span></span> <span data-ttu-id="3511e-116">有关详细信息，请参阅[处理异常和错误](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-116">For details, see [Handling Exceptions and Faults](../../../../docs/framework/wcf/extending/handling-exceptions-and-faults.md).</span></span>  
  
4.  <span data-ttu-id="3511e-117">若要从应用程序层使用通道，请添加一个可将自定义通道添加到通道堆栈的 <xref:System.ServiceModel.Channels.BindingElement>。</span><span class="sxs-lookup"><span data-stu-id="3511e-117">To enable use from the application layer, add a <xref:System.ServiceModel.Channels.BindingElement> that adds the custom channel to a channel stack.</span></span> <span data-ttu-id="3511e-118">有关详细信息，请参阅[创建 BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-118">For more information, see [Creating a BindingElement](../../../../docs/framework/wcf/extending/creating-a-bindingelement.md).</span></span>  
  
 <span data-ttu-id="3511e-119">要在应用程序层启用更完全的支持，需要执行以下附加步骤：</span><span class="sxs-lookup"><span data-stu-id="3511e-119">The following additional steps are required to enable more complete support at the application layer:</span></span>  
  
1.  <span data-ttu-id="3511e-120">添加一个绑定元素扩展部分，以便将新的绑定元素公开到配置系统。</span><span class="sxs-lookup"><span data-stu-id="3511e-120">Add a binding element extension section to expose the new binding element to the configuration system.</span></span> <span data-ttu-id="3511e-121">有关详细信息，请参阅[配置和元数据支持](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-121">For more information, see [Configuration and Metadata Support](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).</span></span>  
  
2.  <span data-ttu-id="3511e-122">添加元数据扩展以将各种功能传递给其他终结点。</span><span class="sxs-lookup"><span data-stu-id="3511e-122">Add metadata extensions to communicate capabilities to other endpoints.</span></span> <span data-ttu-id="3511e-123">有关详细信息，请参阅[配置和元数据支持](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-123">For more information, see [Configuration and Metadata Support](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).</span></span>  
  
3.  <span data-ttu-id="3511e-124">添加一个绑定，该绑定根据定义完善的配置文件来预配置绑定元素堆栈。</span><span class="sxs-lookup"><span data-stu-id="3511e-124">Add a binding that pre-configures a stack of binding elements according to a well-defined profile.</span></span> <span data-ttu-id="3511e-125">有关详细信息，请参阅[创建用户定义绑定](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-125">For more information, see [Creating User-Defined Bindings](../../../../docs/framework/wcf/extending/creating-user-defined-bindings.md).</span></span>  
  
4.  <span data-ttu-id="3511e-126">添加一个绑定部分和绑定配置元素，以便将该绑定公开到配置系统。</span><span class="sxs-lookup"><span data-stu-id="3511e-126">Add a binding section and binding configuration element to expose the binding to the configuration system.</span></span> <span data-ttu-id="3511e-127">有关详细信息，请参阅[配置和元数据支持](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md)。</span><span class="sxs-lookup"><span data-stu-id="3511e-127">For more information, see [Configuration and Metadata Support](../../../../docs/framework/wcf/extending/configuration-and-metadata-support.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3511e-128">请参阅</span><span class="sxs-lookup"><span data-stu-id="3511e-128">See Also</span></span>  
 [<span data-ttu-id="3511e-129">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="3511e-129">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
