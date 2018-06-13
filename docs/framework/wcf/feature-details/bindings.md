---
title: Windows Communication Foundation 绑定
ms.date: 03/30/2017
helpviewer_keywords:
- WCF [WCF], bindings
- Windows Communication Foundation [WCF], bindings
- bindings [WCF]
ms.assetid: 83639133-89f7-43f0-b4ef-8d9e57c08d25
ms.openlocfilehash: 373f7feb64d69373630c942750f264d559643a63
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33489659"
---
# <a name="windows-communcation-foundation-bindings"></a><span data-ttu-id="dfce0-102">Windows Communication Foundation 绑定</span><span class="sxs-lookup"><span data-stu-id="dfce0-102">Windows Communcation Foundation Bindings</span></span>
<span data-ttu-id="dfce0-103">Windows Communication Foundation (WCF) 编写方式分离开来的软件应用程序是与其他软件的通信方式。</span><span class="sxs-lookup"><span data-stu-id="dfce0-103">Windows Communication Foundation (WCF) separates how the software for an application is written from how it communicates with other software.</span></span> <span data-ttu-id="dfce0-104">使用绑定指定客户端与服务彼此通信所需的传输、编码和协议详细信息。</span><span class="sxs-lookup"><span data-stu-id="dfce0-104">Bindings are used to specify the transport, encoding, and protocol details required for clients and services to communicate with each other.</span></span> <span data-ttu-id="dfce0-105">WCF 使用绑定来生成的终结点的基础网络表示，因此必须进行通信的各方达成大多数绑定详细信息。</span><span class="sxs-lookup"><span data-stu-id="dfce0-105">WCF uses bindings to generate the underlying wire representation of the endpoint, so most of the binding details must be agreed upon by the parties that are communicating.</span></span> <span data-ttu-id="dfce0-106">完成此任务的最简单方法是让服务的客户端使用该服务的终结点所使用的相同绑定。</span><span class="sxs-lookup"><span data-stu-id="dfce0-106">The easiest way to achieve this is for clients of a service to use the same binding that the endpoint for the service uses.</span></span> <span data-ttu-id="dfce0-107">有关如何执行此操作的详细信息，请参阅[到配置 Windows Communication Foundation 服务和客户端使用的绑定](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)。</span><span class="sxs-lookup"><span data-stu-id="dfce0-107">For more information about how to do this, see [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb).</span></span>  
  
 <span data-ttu-id="dfce0-108">绑定由绑定元素的集合组成。</span><span class="sxs-lookup"><span data-stu-id="dfce0-108">A binding is made up of a collection of binding elements.</span></span> <span data-ttu-id="dfce0-109">每个元素描述终结点与客户端的通信方式的某一方面。</span><span class="sxs-lookup"><span data-stu-id="dfce0-109">Each element describes some aspect of how the endpoint communicates with clients.</span></span> <span data-ttu-id="dfce0-110">一个绑定必须至少包括一个传输绑定元素，至少包括一个消息编码绑定元素（默认情况下，传输绑定元素可能提供该元素）以及包括任意数目的其他协议绑定元素。</span><span class="sxs-lookup"><span data-stu-id="dfce0-110">A binding must include at least one transport binding element, at least one message-encoding binding element (which the transport binding element can provide by default), and any number of other protocol binding elements.</span></span> <span data-ttu-id="dfce0-111">使用本说明中生成运行时的进程，每个绑定元素均可为该运行时提供代码。</span><span class="sxs-lookup"><span data-stu-id="dfce0-111">The process that builds a runtime out of this description allows each binding element to contribute code to that runtime.</span></span>  
  
 <span data-ttu-id="dfce0-112">WCF 提供包含常见绑定元素选择的绑定。</span><span class="sxs-lookup"><span data-stu-id="dfce0-112">WCF provides bindings that contain common selections of binding elements.</span></span> <span data-ttu-id="dfce0-113">这些绑定可以与其默认设置一起使用，您也可以根据用户需求修改这些默认值。</span><span class="sxs-lookup"><span data-stu-id="dfce0-113">These can be used with their default settings or you can modify those default values according to user requirements.</span></span> <span data-ttu-id="dfce0-114">这些系统提供的绑定具有一些属性，可以通过这些属性直接控制绑定元素及其设置。</span><span class="sxs-lookup"><span data-stu-id="dfce0-114">These system-provided bindings have properties that allow direct control over the binding elements and their settings.</span></span> <span data-ttu-id="dfce0-115">通过为绑定的每个版本提供其自己的名称，还可以轻松地并行使用该绑定的多个版本。</span><span class="sxs-lookup"><span data-stu-id="dfce0-115">You can also easily work side-by-side with multiple versions of a binding by giving each version of the binding its own name.</span></span> <span data-ttu-id="dfce0-116">有关详细信息，请参阅[Configuring System-Provided 绑定](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="dfce0-116">For details, see [Configuring System-Provided Bindings](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md).</span></span>  
  
 <span data-ttu-id="dfce0-117">如果需要的绑定元素集合不是由系统提供的这些绑定之一提供，则可以创建由所需绑定元素的集合组成的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="dfce0-117">If you need a collection of binding elements not provided by one of these system-provided bindings, you can create a custom binding that consists of the collection of binding elements required.</span></span> <span data-ttu-id="dfce0-118">这些自定义绑定易于创建且不需要新类，但是，它们不提供用于控制绑定元素或其设置的属性。</span><span class="sxs-lookup"><span data-stu-id="dfce0-118">These custom bindings are easy to create and do not require a new class, but they do not provide properties for controlling the binding elements or their settings.</span></span> <span data-ttu-id="dfce0-119">你可以访问这些绑定元素并通过包含它们的集合修改其设置。</span><span class="sxs-lookup"><span data-stu-id="dfce0-119">You can access the binding elements and modify their settings through the collection that contains them.</span></span> <span data-ttu-id="dfce0-120">有关详细信息，请参阅[自定义绑定](../../../../docs/framework/wcf/extending/custom-bindings.md)。</span><span class="sxs-lookup"><span data-stu-id="dfce0-120">For details, see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="dfce0-121">本节内容</span><span class="sxs-lookup"><span data-stu-id="dfce0-121">In This Section</span></span>  
 [<span data-ttu-id="dfce0-122">配置系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="dfce0-122">Configuring System-Provided Bindings</span></span>](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 <span data-ttu-id="dfce0-123">描述如何使用和修改 WCF 提供了来支持常用方案的绑定。</span><span class="sxs-lookup"><span data-stu-id="dfce0-123">Describes how to use and modify the bindings that WCF provides to support common scenarios.</span></span>  
  
 [<span data-ttu-id="dfce0-124">使用绑定来配置 Windows Communication Foundation 服务和客户端</span><span class="sxs-lookup"><span data-stu-id="dfce0-124">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 <span data-ttu-id="dfce0-125">描述如何在代码和使用配置以声明方式中强制定义 Windows Communication Foundation (WCF) 服务和客户端的绑定。</span><span class="sxs-lookup"><span data-stu-id="dfce0-125">Describes how to define Windows Communication Foundation (WCF) bindings for services and clients imperatively in code and declaratively using configuration.</span></span>  
  
 [<span data-ttu-id="dfce0-126">自定义绑定</span><span class="sxs-lookup"><span data-stu-id="dfce0-126">Custom Bindings</span></span>](../../../../docs/framework/wcf/extending/custom-bindings.md)  
 <span data-ttu-id="dfce0-127">描述什么是 <xref:System.ServiceModel.Channels.CustomBinding> 以及何时使用它。</span><span class="sxs-lookup"><span data-stu-id="dfce0-127">Describes what a <xref:System.ServiceModel.Channels.CustomBinding> is and when it is used.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="dfce0-128">参考</span><span class="sxs-lookup"><span data-stu-id="dfce0-128">Reference</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
  
 <xref:System.ServiceModel.Channels.BindingElement>  
  
 <xref:System.ServiceModel.Channels.CustomBinding>  
  
## <a name="related-sections"></a><span data-ttu-id="dfce0-129">相关章节</span><span class="sxs-lookup"><span data-stu-id="dfce0-129">Related Sections</span></span>  
 [<span data-ttu-id="dfce0-130">扩展绑定</span><span class="sxs-lookup"><span data-stu-id="dfce0-130">Extending Bindings</span></span>](../../../../docs/framework/wcf/extending/extending-bindings.md)
