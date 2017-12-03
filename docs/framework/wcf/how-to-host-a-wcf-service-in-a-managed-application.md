---
title: "如何：在托管应用程序中承载 WCF 服务"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 5eb29db0-b6dc-4e77-8c68-0a62f79d743b
caps.latest.revision: "42"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: ddbf0df6e4fbf62ab0e7ec8c741a0f3be01c35ef
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-host-a-wcf-service-in-a-managed-application"></a><span data-ttu-id="77c13-102">如何：在托管应用程序中承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="77c13-102">How to: Host a WCF Service in a Managed Application</span></span>
<span data-ttu-id="77c13-103">若要在托管应用程序中承载某项服务，请在托管应用程序代码内嵌入该服务的代码，在代码中强制定义、通过配置以声明的方式定义或者使用默认终结点定义该服务的终结点，然后创建 <xref:System.ServiceModel.ServiceHost> 的实例。</span><span class="sxs-lookup"><span data-stu-id="77c13-103">To host a service inside a managed application, embed the code for the service inside the managed application code, define an endpoint for the service either imperatively in code, declaratively through configuration, or using default endpoints, and then create an instance of <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="77c13-104">若要开始接收消息，请调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="77c13-104">To start receiving messages, call <xref:System.ServiceModel.ICommunicationObject.Open%2A> on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="77c13-105">这样即可创建并打开服务的侦听器。</span><span class="sxs-lookup"><span data-stu-id="77c13-105">This creates and opens the listener for the service.</span></span> <span data-ttu-id="77c13-106">以这种方式承载服务的做法通常称为“自承载”，原因是托管的应用程序会自己处理承载工作。</span><span class="sxs-lookup"><span data-stu-id="77c13-106">Hosting a service in this way is often referred to as "self-hosting" because the managed application is doing the hosting work itself.</span></span> <span data-ttu-id="77c13-107">若要关闭服务，请调用 <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> 上的 <xref:System.ServiceModel.ServiceHost>。</span><span class="sxs-lookup"><span data-stu-id="77c13-107">To close the service, call <xref:System.ServiceModel.Channels.CommunicationObject.Close%2A?displayProperty=nameWithType> on <xref:System.ServiceModel.ServiceHost>.</span></span>  
  
 <span data-ttu-id="77c13-108">在托管的 Windows 服务中、在 Internet Information Services (IIS) 中或在 Windows 进程激活服务 (WAS) 中也可以承载服务。</span><span class="sxs-lookup"><span data-stu-id="77c13-108">A service can also be hosted in a managed Windows service, in Internet Information Services (IIS), or in Windows Process Activation Service (WAS).</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="77c13-109">承载服务的选项，请参阅[托管服务](../../../docs/framework/wcf/hosting-services.md)。</span><span class="sxs-lookup"><span data-stu-id="77c13-109"> hosting options for a service, see [Hosting Services](../../../docs/framework/wcf/hosting-services.md).</span></span>  
  
 <span data-ttu-id="77c13-110">在托管应用程序中承载服务是一个非常灵活的选项，因为采用此选项时，所需部署的基础结构最少。</span><span class="sxs-lookup"><span data-stu-id="77c13-110">Hosting a service in a managed application is the most flexible option because it requires the least infrastructure to deploy.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="77c13-111">承载服务中托管应用程序，请参阅[托管的应用程序中承载](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md)。</span><span class="sxs-lookup"><span data-stu-id="77c13-111"> hosting services in managed applications, see [Hosting in a Managed Application](../../../docs/framework/wcf/feature-details/hosting-in-a-managed-application.md).</span></span>  
  
 <span data-ttu-id="77c13-112">下面的过程演示如何在控制台应用程序中实现自承载的服务。</span><span class="sxs-lookup"><span data-stu-id="77c13-112">The following procedure demonstrates how to implement a self-hosted service in a console application.</span></span>  
  
### <a name="to-create-a-self-hosted-service"></a><span data-ttu-id="77c13-113">创建自承载服务</span><span class="sxs-lookup"><span data-stu-id="77c13-113">To create a self-hosted service</span></span>  
  
1.  <span data-ttu-id="77c13-114">打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]和选择**新建**，**项目...**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="77c13-114">Open [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] and select **New**, **Project...** from the **File** menu.</span></span>  
  
2.  <span data-ttu-id="77c13-115">在**已安装的模板**列表中，选择**Visual C#**， **Windows**或**Visual Basic**， **Windows**.</span><span class="sxs-lookup"><span data-stu-id="77c13-115">In the **Installed Templates** list, select **Visual C#**, **Windows** or **Visual Basic**, **Windows**.</span></span> <span data-ttu-id="77c13-116">具体取决于你[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]下可能会设置、 一个或这两种**其他语言**中的节点**已安装的模板**列表。</span><span class="sxs-lookup"><span data-stu-id="77c13-116">Depending on your [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] settings, one or both of these may be under the **Other Languages** node in the **Installed Templates** list.</span></span>  
  
3.  <span data-ttu-id="77c13-117">选择**控制台应用程序**从**Windows**列表。</span><span class="sxs-lookup"><span data-stu-id="77c13-117">Select **Console Application** from the **Windows** list.</span></span> <span data-ttu-id="77c13-118">类型`SelfHost`中**名称**框中，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="77c13-118">Type `SelfHost` in the **Name** box and click **OK**.</span></span>  
  
4.  <span data-ttu-id="77c13-119">右键单击**SelfHost**中**解决方案资源管理器**和选择**添加引用...**.选择**System.ServiceModel**从**.NET**选项卡，单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="77c13-119">Right-click **SelfHost** in **Solution Explorer** and select **Add Reference...**. Select **System.ServiceModel** from the **.NET** tab and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="77c13-120">如果**解决方案资源管理器**窗口不可见，则选择**解决方案资源管理器**从**视图**菜单。</span><span class="sxs-lookup"><span data-stu-id="77c13-120">If the **Solution Explorer** window is not visible, select **Solution Explorer** from the **View** menu.</span></span>  
  
5.  <span data-ttu-id="77c13-121">双击**Program.cs**或**Module1.vb**中**解决方案资源管理器**如果尚未打开在代码窗口中打开。</span><span class="sxs-lookup"><span data-stu-id="77c13-121">Double-click **Program.cs** or **Module1.vb** in **Solution Explorer** to open it in the code window if it is not already open.</span></span> <span data-ttu-id="77c13-122">将下面的语句添加到文件的顶部。</span><span class="sxs-lookup"><span data-stu-id="77c13-122">Add the following statements at the top of the file.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#1](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#1)]
     [!code-vb[CFX_SelfHost4#1](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#1)]  
  
6.  <span data-ttu-id="77c13-123">定义和实现服务协定。</span><span class="sxs-lookup"><span data-stu-id="77c13-123">Define and implement a service contract.</span></span> <span data-ttu-id="77c13-124">此示例定义了一个 `HelloWorldService`，它基于对服务的输入返回消息。</span><span class="sxs-lookup"><span data-stu-id="77c13-124">This example defines a `HelloWorldService` that returns a message based on the input to the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#2](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#2)]
     [!code-vb[CFX_SelfHost4#2](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#2)]  
  
    > [!NOTE]
    >  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="77c13-125">如何定义和实现服务接口，请参阅[如何： 定义服务协定](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)和[如何： 实现服务协定](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)。</span><span class="sxs-lookup"><span data-stu-id="77c13-125"> how to define and implement a service interface, see [How to: Define a Service Contract](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md) and [How to: Implement a Service Contract](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md).</span></span>  
  
7.  <span data-ttu-id="77c13-126">在 `Main` 方法的顶部，使用该服务的基址创建 <xref:System.Uri> 类的实例。</span><span class="sxs-lookup"><span data-stu-id="77c13-126">At the top of the `Main` method, create an instance of the <xref:System.Uri> class with the base address for the service.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#3](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#3)]
     [!code-vb[CFX_SelfHost4#3](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#3)]  
  
8.  <span data-ttu-id="77c13-127">创建 <xref:System.ServiceModel.ServiceHost> 类的实例，并将表示服务类型的 <xref:System.Type> 和基址统一资源标识符 (URI) 传递到 <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>。</span><span class="sxs-lookup"><span data-stu-id="77c13-127">Create an instance of the <xref:System.ServiceModel.ServiceHost> class, passing a <xref:System.Type> that represents the service type and the base address Uniform Resource Identifier (URI) to the <xref:System.ServiceModel.ServiceHost.%23ctor%28System.Type%2CSystem.Uri%5B%5D%29>.</span></span> <span data-ttu-id="77c13-128">启用元数据发布，然后调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost> 方法，以初始化服务并使其准备好接收消息。</span><span class="sxs-lookup"><span data-stu-id="77c13-128">Enable metadata publishing, and then call the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on the <xref:System.ServiceModel.ServiceHost> to initialize the service and prepare it to receive messages.</span></span>  
  
     [!code-csharp[CFX_SelfHost4#4](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#4)]
     [!code-vb[CFX_SelfHost4#4](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#4)]       
  
    > [!NOTE]
    >  <span data-ttu-id="77c13-129">此示例使用默认终结点，且该服务不需要任何配置文件。</span><span class="sxs-lookup"><span data-stu-id="77c13-129">This example uses default endpoints, and no configuration file is required for this service.</span></span> <span data-ttu-id="77c13-130">如果未配置任何终结点，则运行时会为该服务实现的每个服务协定的每个基地址创建一个终结点。</span><span class="sxs-lookup"><span data-stu-id="77c13-130">If no endpoints are configured, then the runtime creates one endpoint for each base address for each service contract implemented by the service.</span></span> [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="77c13-131">默认值为终结点，请参阅[简化配置](../../../docs/framework/wcf/simplified-configuration.md)和[简化配置 WCF 服务](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="77c13-131"> default endpoints, see [Simplified Configuration](../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="77c13-132">按 Ctrl+Shift+B 生成解决方案。</span><span class="sxs-lookup"><span data-stu-id="77c13-132">Press CTRL+SHIFT+B to build the solution.</span></span>  
  
### <a name="to-test-the-service"></a><span data-ttu-id="77c13-133">测试服务</span><span class="sxs-lookup"><span data-stu-id="77c13-133">To test the service</span></span>  
  
1.  <span data-ttu-id="77c13-134">按 Ctrl+F5 运行服务。</span><span class="sxs-lookup"><span data-stu-id="77c13-134">Press Ctrl + F5 to run the service.</span></span>  
  
2.  <span data-ttu-id="77c13-135">打开**WCF 测试客户端**。</span><span class="sxs-lookup"><span data-stu-id="77c13-135">Open **WCF Test Client**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="77c13-136">若要打开**WCF 测试客户端**，打开[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]命令提示符，然后执行**WcfTestClient.exe**。</span><span class="sxs-lookup"><span data-stu-id="77c13-136">To open **WCF Test Client**, open a [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] command prompt and execute **WcfTestClient.exe**.</span></span>  
  
3.  <span data-ttu-id="77c13-137">选择**添加服务...**从**文件**菜单。</span><span class="sxs-lookup"><span data-stu-id="77c13-137">Select **Add Service...** from the **File** menu.</span></span>  
  
4.  <span data-ttu-id="77c13-138">类型`http://localhost:8080/hello`到地址中，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="77c13-138">Type `http://localhost:8080/hello` into the address box and click **OK**.</span></span>  
  
    > [!TIP]
    >  <span data-ttu-id="77c13-139">确保服务正在运行，否则此步骤将失败。</span><span class="sxs-lookup"><span data-stu-id="77c13-139">Make sure the service is running or else this step fails.</span></span> <span data-ttu-id="77c13-140">如果已经更改了代码中的基址，则在此步骤中使用修改后的基址。</span><span class="sxs-lookup"><span data-stu-id="77c13-140">If you have changed the base address in the code, then use the modified base address in this step.</span></span>  
  
5.  <span data-ttu-id="77c13-141">双击**sayhello**下**我的服务项目**节点。</span><span class="sxs-lookup"><span data-stu-id="77c13-141">Double-click **SayHello** under the **My Service Projects** node.</span></span> <span data-ttu-id="77c13-142">键入您的姓名到**值**中的列**请求**列表，然后单击**Invoke**。</span><span class="sxs-lookup"><span data-stu-id="77c13-142">Type your name into the **Value** column in the **Request** list, and click **Invoke**.</span></span> <span data-ttu-id="77c13-143">答复消息将出现在**响应**列表。</span><span class="sxs-lookup"><span data-stu-id="77c13-143">A reply message appears in the **Response** list.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77c13-144">示例</span><span class="sxs-lookup"><span data-stu-id="77c13-144">Example</span></span>  
 <span data-ttu-id="77c13-145">下面的示例创建 <xref:System.ServiceModel.ServiceHost> 对象以承载 `HelloWorldService` 类型的服务，然后调用 <xref:System.ServiceModel.ICommunicationObject.Open%2A> 上的 <xref:System.ServiceModel.ServiceHost> 方法。</span><span class="sxs-lookup"><span data-stu-id="77c13-145">The following example creates a <xref:System.ServiceModel.ServiceHost> object to host a service of type `HelloWorldService`, and then calls the <xref:System.ServiceModel.ICommunicationObject.Open%2A> method on <xref:System.ServiceModel.ServiceHost>.</span></span> <span data-ttu-id="77c13-146">在代码中提供基址，启用元数据发布，并使用默认终结点。</span><span class="sxs-lookup"><span data-stu-id="77c13-146">A base address is provided in code, metadata publishing is enabled, and default endpoints are used.</span></span>  
  
 [!code-csharp[CFX_SelfHost4#5](../../../samples/snippets/csharp/VS_Snippets_CFX/cfx_selfhost4/cs/program.cs#5)]
 [!code-vb[CFX_SelfHost4#5](../../../samples/snippets/visualbasic/VS_Snippets_CFX/cfx_selfhost4/vb/module1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="77c13-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77c13-147">See Also</span></span>  
 <xref:System.Uri>  
 <xref:System.Configuration.ConfigurationManager.AppSettings%2A>  
 <xref:System.Configuration.ConfigurationManager>  
 [<span data-ttu-id="77c13-148">如何：在 IIS 中承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="77c13-148">How to: Host a WCF Service in IIS</span></span>](../../../docs/framework/wcf/feature-details/how-to-host-a-wcf-service-in-iis.md)  
 [<span data-ttu-id="77c13-149">自承载</span><span class="sxs-lookup"><span data-stu-id="77c13-149">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)  
 [<span data-ttu-id="77c13-150">托管服务</span><span class="sxs-lookup"><span data-stu-id="77c13-150">Hosting Services</span></span>](../../../docs/framework/wcf/hosting-services.md)  
 [<span data-ttu-id="77c13-151">如何：定义服务协定</span><span class="sxs-lookup"><span data-stu-id="77c13-151">How to: Define a Service Contract</span></span>](../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)  
 [<span data-ttu-id="77c13-152">如何：实现服务协定</span><span class="sxs-lookup"><span data-stu-id="77c13-152">How to: Implement a Service Contract</span></span>](../../../docs/framework/wcf/how-to-implement-a-wcf-contract.md)  
 [<span data-ttu-id="77c13-153">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="77c13-153">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="77c13-154">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="77c13-154">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="77c13-155">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="77c13-155">System-Provided Bindings</span></span>](../../../docs/framework/wcf/system-provided-bindings.md)
