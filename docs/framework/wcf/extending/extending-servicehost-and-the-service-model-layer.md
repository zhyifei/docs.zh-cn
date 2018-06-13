---
title: 扩展 ServiceHost 和服务模块层
ms.date: 03/30/2017
helpviewer_keywords:
- extending service models [WCF]
ms.assetid: 954c138a-1cd0-45a0-8abe-e4d2b8ff5400
ms.openlocfilehash: 9e08b5b7b11848262d2cb7b6ed5715799d597889
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803471"
---
# <a name="extending-servicehost-and-the-service-model-layer"></a><span data-ttu-id="a0e86-102">扩展 ServiceHost 和服务模块层</span><span class="sxs-lookup"><span data-stu-id="a0e86-102">Extending ServiceHost and the Service Model Layer</span></span>
<span data-ttu-id="a0e86-103">服务模型层负责从基础通道拉取传入的消息，将它们翻译成应用程序代码形式的方法调用，并将结果发送回调用方。</span><span class="sxs-lookup"><span data-stu-id="a0e86-103">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span> <span data-ttu-id="a0e86-104">服务模型扩展将修改或实现执行或通信行为与功能，包括客户端或调度程序功能、自定义行为、消息和参数截获以及其他扩展功能。</span><span class="sxs-lookup"><span data-stu-id="a0e86-104">Service model extensions modify or implement execution or communication behavior and features involving client or dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a0e86-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="a0e86-105">In This Section</span></span>  
 [<span data-ttu-id="a0e86-106">扩展客户端</span><span class="sxs-lookup"><span data-stu-id="a0e86-106">Extending Clients</span></span>](../../../../docs/framework/wcf/extending/extending-clients.md)  
 <span data-ttu-id="a0e86-107">描述可以截获和修改客户端运行时的接口以及可以向其中插入客户端应用程序中的自定义扩展的类。</span><span class="sxs-lookup"><span data-stu-id="a0e86-107">Describes the interfaces that can intercept and modify the client runtime, as well as the classes into which you can insert your custom extensions in client applications.</span></span> <span data-ttu-id="a0e86-108">例如，您可以执行自定义客户端消息记录，执行自定义消息序列化，等等。</span><span class="sxs-lookup"><span data-stu-id="a0e86-108">For example, you can perform custom client message logging, perform custom message serialization, and so on.</span></span>  
  
 [<span data-ttu-id="a0e86-109">扩展调度程序</span><span class="sxs-lookup"><span data-stu-id="a0e86-109">Extending Dispatchers</span></span>](../../../../docs/framework/wcf/extending/extending-dispatchers.md)  
 <span data-ttu-id="a0e86-110">描述可以截获和修改服务运行时的接口以及可以向其中插入服务应用程序中的自定义扩展的类。</span><span class="sxs-lookup"><span data-stu-id="a0e86-110">Describes the interfaces that can intercept and modify the service runtime, as well as the classes into which you can insert your custom extensions in service applications.</span></span> <span data-ttu-id="a0e86-111">例如，您可以执行自定义服务记录、服务侧消息验证、自定义调度，等等。</span><span class="sxs-lookup"><span data-stu-id="a0e86-111">For example, you can perform custom service logging, service-side message validation, custom dispatching, and so on.</span></span>  
  
 [<span data-ttu-id="a0e86-112">可扩展对象</span><span class="sxs-lookup"><span data-stu-id="a0e86-112">Extensible Objects</span></span>](../../../../docs/framework/wcf/extending/extensible-objects.md)  
 <span data-ttu-id="a0e86-113">描述五个可扩展对象和 <xref:System.ServiceModel.IExtensibleObject%601> 模式。</span><span class="sxs-lookup"><span data-stu-id="a0e86-113">Describes the five extensible objects and the <xref:System.ServiceModel.IExtensibleObject%601> pattern.</span></span> <span data-ttu-id="a0e86-114">可扩展对象模式用于使用新功能扩展现有运行时类，或者向对象中添加新状态。</span><span class="sxs-lookup"><span data-stu-id="a0e86-114">The extensible object pattern is used to either extend existing runtime classes with new functionality or to add new state to an object.</span></span> <span data-ttu-id="a0e86-115">附加到可扩展对象之一的扩展名，在访问附加到公共可扩展对象的共享状态和功能过程的各个不同阶段启用行为，各可扩展对象可以访问该公共扩展对象。</span><span class="sxs-lookup"><span data-stu-id="a0e86-115">Extensions, attached to one of the extensible objects, enable behaviors at very different stages in processing to access shared state and functionality attached to a common extensible object that they can access.</span></span>  
  
 [<span data-ttu-id="a0e86-116">使用行为配置和扩展运行时</span><span class="sxs-lookup"><span data-stu-id="a0e86-116">Configuring and Extending the Runtime with Behaviors</span></span>](../../../../docs/framework/wcf/extending/configuring-and-extending-the-runtime-with-behaviors.md)  
 <span data-ttu-id="a0e86-117">若要更改设置或 WCF 运行时中插入扩展，你可以使用行为。</span><span class="sxs-lookup"><span data-stu-id="a0e86-117">To change settings on or insert extensions in the WCF runtime, you use Behaviors.</span></span> <span data-ttu-id="a0e86-118">WCF 包括系统实现的用于控制遏制、实例化和大量服务及操作的其他方面的行为。</span><span class="sxs-lookup"><span data-stu-id="a0e86-118">WCF includes system-implemented behaviors for controlling throttling, instancing, and many other aspects of services and operations.</span></span> <span data-ttu-id="a0e86-119">本节介绍如何通过编程方式和使用配置文件来创建您自己的自定义行为，以及如何使这些自定义行为变为可用。</span><span class="sxs-lookup"><span data-stu-id="a0e86-119">This section describes how to create your own custom behaviors and how to make them available for use both programmatically and using configuration files.</span></span>  
  
 [<span data-ttu-id="a0e86-120">使用 ServiceHostFactory 扩展宿主</span><span class="sxs-lookup"><span data-stu-id="a0e86-120">Extending Hosting Using ServiceHostFactory</span></span>](../../../../docs/framework/wcf/extending/extending-hosting-using-servicehostfactory.md)  
 <span data-ttu-id="a0e86-121">描述如何扩展 <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType> 和 <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType> 以及使用 <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> 类来自定义主机环境。</span><span class="sxs-lookup"><span data-stu-id="a0e86-121">Describes how to extend <xref:System.ServiceModel.ServiceHostBase?displayProperty=nameWithType>, <xref:System.ServiceModel.ServiceHost?displayProperty=nameWithType>, and use the <xref:System.ServiceModel.Activation.ServiceHostFactory?displayProperty=nameWithType> classes to customize the host environment.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="a0e86-122">参考</span><span class="sxs-lookup"><span data-stu-id="a0e86-122">Reference</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="a0e86-123">相关章节</span><span class="sxs-lookup"><span data-stu-id="a0e86-123">Related Sections</span></span>
