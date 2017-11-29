---
title: "如何：在可靠会话内交换消息"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
caps.latest.revision: "9"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 6207b526aa98fd01892b493ab5b6ad6a58abc3c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="ab61c-102">如何：在可靠会话内交换消息</span><span class="sxs-lookup"><span data-stu-id="ab61c-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="ab61c-103">本主题概述了使用系统提供的绑定之一来启用可靠会话所需的步骤。这些绑定支持可靠会话，但默认情况下不支持。</span><span class="sxs-lookup"><span data-stu-id="ab61c-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="ab61c-104">启用可靠会话使用代码以强制方式或配置文件中以声明方式。</span><span class="sxs-lookup"><span data-stu-id="ab61c-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="ab61c-105">此过程使用客户端和服务配置文件来启用可靠会话并规定消息到达与发送这些相同的顺序。</span><span class="sxs-lookup"><span data-stu-id="ab61c-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="ab61c-106">此过程的关键部分是终结点配置元素包含`bindingConfiguration`引用一个名为的绑定配置的属性`Binding1`。</span><span class="sxs-lookup"><span data-stu-id="ab61c-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="ab61c-107">[ **\<绑定 >** ](../../../../docs/framework/misc/binding.md)配置元素将引用此名称来启用可靠会话通过设置`enabled`属性[ **\<reliableSession >** ](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="ab61c-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](http://msdn.microsoft.com/en-us/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="ab61c-108">通过将 `ordered` 属性设置为 `true`，可为可靠会话指定有序传送保证。</span><span class="sxs-lookup"><span data-stu-id="ab61c-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="ab61c-109">此示例中的源副本，请参阅[WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)。</span><span class="sxs-lookup"><span data-stu-id="ab61c-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="ab61c-110">使用 WSHttpBinding 以使用可靠会话配置服务</span><span class="sxs-lookup"><span data-stu-id="ab61c-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="ab61c-111">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="ab61c-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="ab61c-112">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="ab61c-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="ab61c-113">请注意，该服务的实现内部未指定地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="ab61c-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="ab61c-114">你无需编写代码来从配置文件中检索的地址或绑定信息信息。</span><span class="sxs-lookup"><span data-stu-id="ab61c-114">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="ab61c-115">创建*Web.config*文件来配置的终结点`CalculatorService`使用<xref:System.ServiceModel.WSHttpBinding>与可靠会话启用和有序传送所需的消息。</span><span class="sxs-lookup"><span data-stu-id="ab61c-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="ab61c-116">创建*Service.svc*包含行的文件：</span><span class="sxs-lookup"><span data-stu-id="ab61c-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="ab61c-117">位置*Service.svc* Internet 信息服务 (IIS) 虚拟目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="ab61c-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="ab61c-118">使用 WSHttpBinding 以使用可靠会话配置客户端</span><span class="sxs-lookup"><span data-stu-id="ab61c-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="ab61c-119">使用[ServiceModel 元数据实用工具 (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)从命令行根据服务元数据生成代码：</span><span class="sxs-lookup"><span data-stu-id="ab61c-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="ab61c-120">生成的客户端包含`ICalculator`定义了客户端实现必须满足的服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="ab61c-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="ab61c-121">生成的客户端应用程序还包含 `ClientCalculator` 的实现。</span><span class="sxs-lookup"><span data-stu-id="ab61c-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="ab61c-122">请注意，使用任意位置服务的实现内部未指定地址和绑定信息。</span><span class="sxs-lookup"><span data-stu-id="ab61c-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="ab61c-123">你无需编写代码来从配置文件中检索的地址或绑定信息信息。</span><span class="sxs-lookup"><span data-stu-id="ab61c-123">You aren't required to write code to retrieve the address or binding information information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="ab61c-124">*Svcutil.exe*还会生成客户端使用的配置<xref:System.ServiceModel.WSHttpBinding>类。</span><span class="sxs-lookup"><span data-stu-id="ab61c-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="ab61c-125">将配置文件名称*App.config*时使用[!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ab61c-125">Name the configuration file *App.config* when using [!INCLUDE[vsprvs](../../../../includes/vsprvs-md.md)].</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="ab61c-126">创建的实例`ClientCalculator`应用程序中并调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="ab61c-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="ab61c-127">编译并运行客户端。</span><span class="sxs-lookup"><span data-stu-id="ab61c-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="ab61c-128">示例</span><span class="sxs-lookup"><span data-stu-id="ab61c-128">Example</span></span>

<span data-ttu-id="ab61c-129">默认情况下，有多种系统提供的绑定支持可靠会话。</span><span class="sxs-lookup"><span data-stu-id="ab61c-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="ab61c-130">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="ab61c-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="ab61c-131">有关如何创建支持可靠会话的自定义绑定的示例，请参阅[如何： 创建使用 HTTPS 的自定义的可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)。</span><span class="sxs-lookup"><span data-stu-id="ab61c-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="ab61c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="ab61c-132">See also</span></span>

[<span data-ttu-id="ab61c-133">可靠会话</span><span class="sxs-lookup"><span data-stu-id="ab61c-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
