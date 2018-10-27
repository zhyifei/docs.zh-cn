---
title: 如何：在可靠会话内交换消息
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 53e5661bf140540cd0fc7a9fcb739b67488b8491
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2018
ms.locfileid: "50038249"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a><span data-ttu-id="7674e-102">如何：在可靠会话内交换消息</span><span class="sxs-lookup"><span data-stu-id="7674e-102">How to: Exchange Messages Within a Reliable Session</span></span>

<span data-ttu-id="7674e-103">本主题概述了使用系统提供的绑定之一来启用可靠会话所需的步骤。这些绑定支持可靠会话，但默认情况下不支持。</span><span class="sxs-lookup"><span data-stu-id="7674e-103">This topic outlines the steps required to enable a reliable session using one of the system-provided bindings that support such a session, but not by default.</span></span> <span data-ttu-id="7674e-104">启用可靠会话使用代码以强制方式或配置文件中以声明方式。</span><span class="sxs-lookup"><span data-stu-id="7674e-104">You enable a reliable session imperatively using code or declaratively in your configuration file.</span></span> <span data-ttu-id="7674e-105">此过程使用客户端和服务配置文件来启用可靠会话并规定消息到达其中发送顺序相同。</span><span class="sxs-lookup"><span data-stu-id="7674e-105">This procedure uses the client and service configuration files to enable the reliable session and to stipulate that the messages arrive in the same order in which they were sent.</span></span>

<span data-ttu-id="7674e-106">此过程的关键部分是终结点配置元素包含`bindingConfiguration`引用一个名为的绑定配置的属性`Binding1`。</span><span class="sxs-lookup"><span data-stu-id="7674e-106">The key part of this procedure is that the endpoint configuration element contain a `bindingConfiguration` attribute that references a binding configuration named `Binding1`.</span></span> <span data-ttu-id="7674e-107">[ **\<绑定 >** ](../../../../docs/framework/misc/binding.md)配置元素将引用此名称来启用可靠会话通过设置`enabled`属性的[ **\<reliableSession >** ](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="7674e-107">The [**\<binding>**](../../../../docs/framework/misc/binding.md) configuration element references this name to enable reliable sessions by setting the `enabled` attribute of the [**\<reliableSession>**](https://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) element to `true`.</span></span> <span data-ttu-id="7674e-108">通过将 `ordered` 属性设置为 `true`，可为可靠会话指定有序传送保证。</span><span class="sxs-lookup"><span data-stu-id="7674e-108">You specify the ordered delivery assurances for the reliable session by setting the `ordered` attribute to `true`.</span></span>

<span data-ttu-id="7674e-109">此示例中的源副本，请参阅[WS 可靠会话](../../../../docs/framework/wcf/samples/ws-reliable-session.md)。</span><span class="sxs-lookup"><span data-stu-id="7674e-109">For the source copy of this example, see [WS Reliable Session](../../../../docs/framework/wcf/samples/ws-reliable-session.md).</span></span>

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="7674e-110">将服务配置为使用 WSHttpBinding 使用可靠会话</span><span class="sxs-lookup"><span data-stu-id="7674e-110">Configure the service with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="7674e-111">为该类型的服务定义服务协定。</span><span class="sxs-lookup"><span data-stu-id="7674e-111">Define a service contract for the type of service.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. <span data-ttu-id="7674e-112">在服务类中实现该服务协定。</span><span class="sxs-lookup"><span data-stu-id="7674e-112">Implement the service contract in a service class.</span></span> <span data-ttu-id="7674e-113">请注意，该服务的实现内部未指定地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="7674e-113">Note that the address or binding information isn't specified inside the implementation of the service.</span></span> <span data-ttu-id="7674e-114">您无需编写代码，以便从配置文件中检索的地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="7674e-114">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. <span data-ttu-id="7674e-115">创建*Web.config*文件以配置一个终结点`CalculatorService`，它使用<xref:System.ServiceModel.WSHttpBinding>与已启用并按序送达消息所需的可靠会话。</span><span class="sxs-lookup"><span data-stu-id="7674e-115">Create a *Web.config* file to configure an endpoint for the `CalculatorService` that uses the <xref:System.ServiceModel.WSHttpBinding> with reliable session enabled and ordered delivery of messages required.</span></span>

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. <span data-ttu-id="7674e-116">创建*Service.svc*包含行的文件：</span><span class="sxs-lookup"><span data-stu-id="7674e-116">Create a *Service.svc* file that contains the line:</span></span>

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  <span data-ttu-id="7674e-117">位置*Service.svc* Internet 信息服务 (IIS) 虚拟目录中的文件。</span><span class="sxs-lookup"><span data-stu-id="7674e-117">Place the *Service.svc* file in your Internet Information Services (IIS) virtual directory.</span></span>

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a><span data-ttu-id="7674e-118">使用 WSHttpBinding 使用可靠会话配置客户端</span><span class="sxs-lookup"><span data-stu-id="7674e-118">Configure the client with a WSHttpBinding to use a reliable session</span></span>

1. <span data-ttu-id="7674e-119">使用[ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)从命令行以从服务元数据生成代码：</span><span class="sxs-lookup"><span data-stu-id="7674e-119">Use the [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata:</span></span>

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. <span data-ttu-id="7674e-120">生成的客户端包含`ICalculator`定义客户端实现必须满足的服务协定的接口。</span><span class="sxs-lookup"><span data-stu-id="7674e-120">The generated client contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. <span data-ttu-id="7674e-121">生成的客户端应用程序还包含 `ClientCalculator` 的实现。</span><span class="sxs-lookup"><span data-stu-id="7674e-121">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="7674e-122">请注意，地址和绑定信息不内部，指定服务的实现。</span><span class="sxs-lookup"><span data-stu-id="7674e-122">Note that the address and binding information isn't specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="7674e-123">您无需编写代码，以便从配置文件中检索的地址或绑定信息。</span><span class="sxs-lookup"><span data-stu-id="7674e-123">You aren't required to write code to retrieve the address or binding information from the configuration file.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. <span data-ttu-id="7674e-124">*Svcutil.exe*还会生成使用的客户端的配置<xref:System.ServiceModel.WSHttpBinding>类。</span><span class="sxs-lookup"><span data-stu-id="7674e-124">*Svcutil.exe* also generates the configuration for the client that uses the <xref:System.ServiceModel.WSHttpBinding> class.</span></span> <span data-ttu-id="7674e-125">将配置文件名称*App.config*时使用 Visual Studio。</span><span class="sxs-lookup"><span data-stu-id="7674e-125">Name the configuration file *App.config* when using Visual Studio.</span></span>

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. <span data-ttu-id="7674e-126">创建的实例`ClientCalculator`应用程序中，并调用服务操作。</span><span class="sxs-lookup"><span data-stu-id="7674e-126">Create an instance of the `ClientCalculator` in an application and call the service operations.</span></span>

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. <span data-ttu-id="7674e-127">编译并运行客户端。</span><span class="sxs-lookup"><span data-stu-id="7674e-127">Compile and run the client.</span></span>

## <a name="example"></a><span data-ttu-id="7674e-128">示例</span><span class="sxs-lookup"><span data-stu-id="7674e-128">Example</span></span>

<span data-ttu-id="7674e-129">默认情况下，有多种系统提供的绑定支持可靠会话。</span><span class="sxs-lookup"><span data-stu-id="7674e-129">Several of the system-provided bindings support reliable sessions by default.</span></span> <span data-ttu-id="7674e-130">这些方法包括：</span><span class="sxs-lookup"><span data-stu-id="7674e-130">These include:</span></span>

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

<span data-ttu-id="7674e-131">有关如何创建支持可靠会话的自定义绑定的示例，请参阅[如何： 使用 HTTPS 创建自定义可靠会话绑定](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md)。</span><span class="sxs-lookup"><span data-stu-id="7674e-131">For an example of how to create a custom binding that supports reliable sessions, see [How to: Create a Custom Reliable Session Binding with HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="7674e-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="7674e-132">See also</span></span>

[<span data-ttu-id="7674e-133">可靠会话</span><span class="sxs-lookup"><span data-stu-id="7674e-133">Reliable Sessions</span></span>](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
