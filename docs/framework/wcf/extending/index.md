---
title: 扩展 WCF
ms.date: 03/30/2017
helpviewer_keywords:
- WCF, extensibility
- extensibility [WCF]
- Windows Communication Foundation, extensibility
ms.assetid: c145e2f6-f402-41f5-8b5a-eee03978737b
ms.openlocfilehash: 24ad74f04a3ac31d0b0d0d87f0d74f88c0521f50
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2018
ms.locfileid: "33803700"
---
# <a name="extending-wcf"></a><span data-ttu-id="ec20f-102">扩展 WCF</span><span class="sxs-lookup"><span data-stu-id="ec20f-102">Extending WCF</span></span>
<span data-ttu-id="ec20f-103">Windows Communication Foundation (WCF)，可修改和扩展运行的时组件，以便能够准确地控制和扩展基于服务的应用程序。</span><span class="sxs-lookup"><span data-stu-id="ec20f-103">Windows Communication Foundation (WCF) allows you to modify and extend run time components to precisely control and extend service-based applications.</span></span> <span data-ttu-id="ec20f-104">本节中的主题深入探讨了有关扩展性体系结构的内容。</span><span class="sxs-lookup"><span data-stu-id="ec20f-104">The topics in this section go in depth about the extensibility architecture.</span></span> <span data-ttu-id="ec20f-105">有关基本编程的详细信息，请参阅[基本 WCF 编程](../../../../docs/framework/wcf/basic-wcf-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="ec20f-105">For more information about basic programming, see [Basic WCF Programming](../../../../docs/framework/wcf/basic-wcf-programming.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="ec20f-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="ec20f-106">In This Section</span></span>  
 [<span data-ttu-id="ec20f-107">扩展 ServiceHost 和服务模块层</span><span class="sxs-lookup"><span data-stu-id="ec20f-107">Extending ServiceHost and the Service Model Layer</span></span>](../../../../docs/framework/wcf/extending/extending-servicehost-and-the-service-model-layer.md)  
 <span data-ttu-id="ec20f-108">服务模型层负责从基础通道拉取传入的消息，将它们翻译成应用程序代码形式的方法调用，并将结果发送回调用方。</span><span class="sxs-lookup"><span data-stu-id="ec20f-108">The service model layer is responsible for pulling incoming messages out of the underlying channels, translating them into method invocations in application code, and sending the results back to the caller.</span></span>  <span data-ttu-id="ec20f-109">服务模型扩展将修改或实现执行或通信行为，功能包括调度程序功能、自定义行为、消息和参数侦听以及其他扩展性功能。</span><span class="sxs-lookup"><span data-stu-id="ec20f-109">Service model extensions modify or implement execution or communication behavior and features involving dispatcher functionality, custom behaviors, message and parameter interception, and other extensibility functionality.</span></span>  
  
 [<span data-ttu-id="ec20f-110">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="ec20f-110">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)  
 <span data-ttu-id="ec20f-111">绑定是描述连接到终结点所需的通信详细信息的对象。</span><span class="sxs-lookup"><span data-stu-id="ec20f-111">Bindings are objects that describe the communication details required to connect to an endpoint.</span></span> <span data-ttu-id="ec20f-112">绑定扩展或自定义绑定实现了支持应用程序功能所需的自定义通信功能。</span><span class="sxs-lookup"><span data-stu-id="ec20f-112">Binding extensions or custom bindings implement custom communication functionality required to support application features.</span></span>  
  
 [<span data-ttu-id="ec20f-113">扩展通道层</span><span class="sxs-lookup"><span data-stu-id="ec20f-113">Extending the Channel Layer</span></span>](../../../../docs/framework/wcf/extending/extending-the-channel-layer.md)  
 <span data-ttu-id="ec20f-114">通道层位于服务模型层的下方并且负责客户端和服务之间的消息交换。</span><span class="sxs-lookup"><span data-stu-id="ec20f-114">The channel layer sits beneath the service model layer and is responsible for the exchange of messages between clients and services.</span></span> <span data-ttu-id="ec20f-115">通道扩展可以实现新的协议功能，例如安全性。</span><span class="sxs-lookup"><span data-stu-id="ec20f-115">Channel extensions can implement new protocol functionality, such as security.</span></span> <span data-ttu-id="ec20f-116">通道扩展也可以传输功能，例如实现新的网络传输以传送 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="ec20f-116">Channel extensions also transport functionality, such as implementing a new network transport to carry SOAP messages.</span></span>  
  
 [<span data-ttu-id="ec20f-117">扩展安全性</span><span class="sxs-lookup"><span data-stu-id="ec20f-117">Extending Security</span></span>](../../../../docs/framework/wcf/extending/extending-security.md)  
 <span data-ttu-id="ec20f-118">在 WCF 中的安全包含的传输安全 （完整性、 保密性和身份验证），访问控制 （授权） 和审核。</span><span class="sxs-lookup"><span data-stu-id="ec20f-118">Security in WCF consists of transfer security (integrity, confidentiality, and authentication), access control (authorization) and auditing.</span></span> <span data-ttu-id="ec20f-119">类中找到`IdentityModel`命名空间由 WCF 用于访问控制。</span><span class="sxs-lookup"><span data-stu-id="ec20f-119">The classes found in the `IdentityModel` namespace are used by WCF for access control.</span></span> <span data-ttu-id="ec20f-120">了解安全体系结构使您可以创建自定义声明类型，以便容纳自定义访问控制系统。</span><span class="sxs-lookup"><span data-stu-id="ec20f-120">Understanding the security architecture allows you to create custom claim types to accommodate custom access control systems.</span></span>  
  
 [<span data-ttu-id="ec20f-121">扩展元数据系统</span><span class="sxs-lookup"><span data-stu-id="ec20f-121">Extending the Metadata System</span></span>](../../../../docs/framework/wcf/extending/extending-the-metadata-system.md)  
 <span data-ttu-id="ec20f-122">WCF 元数据系统是一组类和表示实现基于服务的应用程序所需的元数据的接口。</span><span class="sxs-lookup"><span data-stu-id="ec20f-122">The WCF metadata system is a group of classes and interfaces that represent metadata required to implement service-based applications.</span></span> <span data-ttu-id="ec20f-123">修改或扩展这些类，或者实现和配置这些接口，以便导出和导入自定义元数据（如 Web 服务描述语言 (WSDL) 扩展或自定义的 WS-PolicyAttachments 断言）。</span><span class="sxs-lookup"><span data-stu-id="ec20f-123">Modify or extend the classes or implement and configure the interfaces to export and import custom metadata such as Web Services Description Language (WSDL) extensions or custom WS-PolicyAttachments assertions.</span></span>  
  
 [<span data-ttu-id="ec20f-124">扩展编码器和序列化程序</span><span class="sxs-lookup"><span data-stu-id="ec20f-124">Extending Encoders and Serializers</span></span>](../../../../docs/framework/wcf/extending/extending-encoders-and-serializers.md)  
 <span data-ttu-id="ec20f-125">编码器和序列化程序将数据从一种形式转换成另一种形式。</span><span class="sxs-lookup"><span data-stu-id="ec20f-125">Encoders and serializers translate data from one form to another.</span></span> <span data-ttu-id="ec20f-126">本节中的主题讨论如何扩展已提供的类以满足特殊需求。</span><span class="sxs-lookup"><span data-stu-id="ec20f-126">The topics in this section discuss how to extend the supplied classes to meet special requirements.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="ec20f-127">参考</span><span class="sxs-lookup"><span data-stu-id="ec20f-127">Reference</span></span>  
 <xref:System.ServiceModel>  
  
 <xref:System.ServiceModel.Channels>  
  
 <xref:System.ServiceModel.Description>  
  
 <xref:System.IdentityModel.Claims>  
  
 <xref:System.IdentityModel.Policy>  
  
 <xref:System.IdentityModel.Selectors>  
  
 <xref:System.IdentityModel.Tokens>  
  
## <a name="related-sections"></a><span data-ttu-id="ec20f-128">相关章节</span><span class="sxs-lookup"><span data-stu-id="ec20f-128">Related Sections</span></span>  
 [<span data-ttu-id="ec20f-129">基本 WCF 编程</span><span class="sxs-lookup"><span data-stu-id="ec20f-129">Basic WCF Programming</span></span>](../../../../docs/framework/wcf/basic-wcf-programming.md)  
  
 [<span data-ttu-id="ec20f-130">WCF 功能详细信息</span><span class="sxs-lookup"><span data-stu-id="ec20f-130">WCF Feature Details</span></span>](../../../../docs/framework/wcf/feature-details/index.md)  
  
 [<span data-ttu-id="ec20f-131">指南与最佳做法</span><span class="sxs-lookup"><span data-stu-id="ec20f-131">Guidelines and Best Practices</span></span>](../../../../docs/framework/wcf/guidelines-and-best-practices.md)
