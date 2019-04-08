---
title: 如何：使用代码发布服务的元数据
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 51407e6d-4d87-42d5-be7c-9887b8652006
ms.openlocfilehash: 5c17f5c399335a2c7cbcc6f4474982de591dd453
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59097998"
---
# <a name="how-to-publish-metadata-for-a-service-using-code"></a><span data-ttu-id="e0273-102">如何：使用代码发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="e0273-102">How to: Publish Metadata for a Service Using Code</span></span>
<span data-ttu-id="e0273-103">这是一个讨论 Windows Communication Foundation (WCF) 服务的发布元数据的两个操作指南主题。</span><span class="sxs-lookup"><span data-stu-id="e0273-103">This is one of two how-to topics that discuss publishing metadata for a Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="e0273-104">有两种方式可以指定服务应如何发布元数据：使用配置文件和使用代码。</span><span class="sxs-lookup"><span data-stu-id="e0273-104">There are two ways to specify how a service should publish metadata, using a configuration file and using code.</span></span> <span data-ttu-id="e0273-105">本主题演示如何使用代码发布服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="e0273-105">This topic shows how to publish metadata for a service using a code.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="e0273-106">本主题演示如何以不安全的方式发布元数据。</span><span class="sxs-lookup"><span data-stu-id="e0273-106">This topic shows how to publish metadata in an unsecure manner.</span></span> <span data-ttu-id="e0273-107">任何客户端都可以检索服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="e0273-107">Any client can retrieve the metadata from the service.</span></span> <span data-ttu-id="e0273-108">如果您要求服务以安全方式发布元数据，</span><span class="sxs-lookup"><span data-stu-id="e0273-108">If you require your service to publish metadata in a secure manner.</span></span> <span data-ttu-id="e0273-109">请参阅[自定义安全元数据终结点](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)。</span><span class="sxs-lookup"><span data-stu-id="e0273-109">see [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md).</span></span>  
  
 <span data-ttu-id="e0273-110">有关配置文件中的发布元数据的详细信息，请参阅[如何：发布使用配置文件服务的元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="e0273-110">For more information about publishing metadata in a configuration file, see [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span> <span data-ttu-id="e0273-111">通过发布元数据，客户端可以使用 WS-Transfer GET 请求或使用 `?wsdl` 查询字符串的 HTTP/GET 来检索元数据。</span><span class="sxs-lookup"><span data-stu-id="e0273-111">Publishing metadata allows clients to retrieve the metadata using a WS-Transfer GET request or an HTTP/GET request using the `?wsdl` query string.</span></span> <span data-ttu-id="e0273-112">若要确保代码能够工作，必须创建一个基本的 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0273-112">To be sure that the code is working you must create a basic WCF service.</span></span> <span data-ttu-id="e0273-113">在以下代码中提供了一个基本的自承载服务。</span><span class="sxs-lookup"><span data-stu-id="e0273-113">A basic self-hosted service is provided in the following code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#0)]
 [!code-vb[htPublishMetadataCode#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#0)]  
  
### <a name="to-publish-metadata-in-code"></a><span data-ttu-id="e0273-114">在代码中发布元数据</span><span class="sxs-lookup"><span data-stu-id="e0273-114">To publish metadata in code</span></span>  
  
1.  <span data-ttu-id="e0273-115">在控制台应用程序的主方法中，通过传入服务类型和基址来实例化 <xref:System.ServiceModel.ServiceHost> 对象。</span><span class="sxs-lookup"><span data-stu-id="e0273-115">Within the main method of a console application, instantiate a <xref:System.ServiceModel.ServiceHost> object by passing in the service type and the base address.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#1)]
     [!code-vb[htPublishMetadataCode#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#1)]  
  
2.  <span data-ttu-id="e0273-116">紧接在步骤 1 的代码下面创建一个 try 块，这将捕获在服务运行过程中引发的任何异常。</span><span class="sxs-lookup"><span data-stu-id="e0273-116">Create a try block immediately below the code for step 1, this catches any exceptions that get thrown while the service is running.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#2)]
     [!code-vb[htPublishMetadataCode#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#2)]  
  
     [!code-csharp[htPublishMetadataCode#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#3)]
     [!code-vb[htPublishMetadataCode#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#3)]  
  
3.  <span data-ttu-id="e0273-117">检查服务主机是否已经包含一个 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>，如果没有，则创建一个新的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例。</span><span class="sxs-lookup"><span data-stu-id="e0273-117">Check to see whether the service host already contains a <xref:System.ServiceModel.Description.ServiceMetadataBehavior>, if not, create a new <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#4)]
     [!code-vb[htPublishMetadataCode#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#4)]  
  
4.  <span data-ttu-id="e0273-118">设置<xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>属性</span><span class="sxs-lookup"><span data-stu-id="e0273-118">Set the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to</span></span> `true.`  
  
     [!code-csharp[htPublishMetadataCode#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#5)]
     [!code-vb[htPublishMetadataCode#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#5)]  
  
5.  <span data-ttu-id="e0273-119"><xref:System.ServiceModel.Description.ServiceMetadataBehavior> 包含一个 <xref:System.ServiceModel.Description.MetadataExporter> 属性。</span><span class="sxs-lookup"><span data-stu-id="e0273-119">The <xref:System.ServiceModel.Description.ServiceMetadataBehavior> contains a <xref:System.ServiceModel.Description.MetadataExporter> property.</span></span> <span data-ttu-id="e0273-120"><xref:System.ServiceModel.Description.MetadataExporter> 包含一个 <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="e0273-120">The <xref:System.ServiceModel.Description.MetadataExporter> contains a <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property.</span></span> <span data-ttu-id="e0273-121">将 <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 属性的值设置为 <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>。</span><span class="sxs-lookup"><span data-stu-id="e0273-121">Set the value of the <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>.</span></span> <span data-ttu-id="e0273-122">还可以将 <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> 属性设置为 <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>。</span><span class="sxs-lookup"><span data-stu-id="e0273-122">The <xref:System.ServiceModel.Description.MetadataExporter.PolicyVersion%2A> property can also be set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A>.</span></span> <span data-ttu-id="e0273-123">如果设置为<xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A>元数据导出程序会生成与元数据的策略信息的"符合 Ws-policy 1.5。</span><span class="sxs-lookup"><span data-stu-id="e0273-123">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy15%2A> the metadata exporter generates policy information with the metadata that" conforms to WS-Policy 1.5.</span></span> <span data-ttu-id="e0273-124">当设置为 <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> 时，元数据导出程序会生成符合 WS-Policy 1.2 的策略信息。</span><span class="sxs-lookup"><span data-stu-id="e0273-124">When set to <xref:System.ServiceModel.Description.PolicyVersion.Policy12%2A> the metadata exporter generates policy information that conforms to WS-Policy 1.2.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#6)]
     [!code-vb[htPublishMetadataCode#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#6)]  
  
6.  <span data-ttu-id="e0273-125">将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例添加到服务主机的行为集合。</span><span class="sxs-lookup"><span data-stu-id="e0273-125">Add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance to the service host's behaviors collection.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#7)]
     [!code-vb[htPublishMetadataCode#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#7)]  
  
7.  <span data-ttu-id="e0273-126">将元数据交换终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="e0273-126">Add the metadata exchange endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#8)]
     [!code-vb[htPublishMetadataCode#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#8)]  
  
8.  <span data-ttu-id="e0273-127">将应用程序终结点添加到服务主机。</span><span class="sxs-lookup"><span data-stu-id="e0273-127">Add an application endpoint to the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#9)]
     [!code-vb[htPublishMetadataCode#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#9)]  
  
    > [!NOTE]
    >  <span data-ttu-id="e0273-128">如果您不希望向服务添加任何终结点，则运行时为您添加默认终结点。</span><span class="sxs-lookup"><span data-stu-id="e0273-128">If you do not add any endpoints to the service, the runtime adds default endpoints for you.</span></span> <span data-ttu-id="e0273-129">在此示例中，由于服务的 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 设置为 `true`，所以服务还启用了发布元数据。</span><span class="sxs-lookup"><span data-stu-id="e0273-129">In this example, because the service has a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> set to `true`, the service has publishing metadata enabled.</span></span> <span data-ttu-id="e0273-130">有关默认终结点的详细信息，请参阅[Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md)并[WCF 服务的简化配置](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md)。</span><span class="sxs-lookup"><span data-stu-id="e0273-130">For more information about default endpoints, see [Simplified Configuration](../../../../docs/framework/wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../../docs/framework/wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>  
  
9. <span data-ttu-id="e0273-131">打开服务主机并等待传入调用。</span><span class="sxs-lookup"><span data-stu-id="e0273-131">Open the service host and wait for incoming calls.</span></span> <span data-ttu-id="e0273-132">当用户按 Enter 时，关闭服务主机。</span><span class="sxs-lookup"><span data-stu-id="e0273-132">When the user presses ENTER, close the service host.</span></span>  
  
     [!code-csharp[htPublishMetadataCode#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#10)]
     [!code-vb[htPublishMetadataCode#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#10)]  
  
10. <span data-ttu-id="e0273-133">生成并运行控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="e0273-133">Build and run the console application.</span></span>  
  
11. <span data-ttu-id="e0273-134">使用 Internet Explorer 浏览到该服务的基址 (http://localhost:8001/MetadataSample在此示例中)，并验证是否已打开元数据发布。</span><span class="sxs-lookup"><span data-stu-id="e0273-134">Use Internet Explorer to browse to the base address of the service (http://localhost:8001/MetadataSample in this sample) and verify that the metadata publishing is turned on.</span></span> <span data-ttu-id="e0273-135">你应会看到一个网页，该网页顶部显示“Simple Service”（简单服务），其下面紧接着显示“You have created a service”（已经创建服务）。</span><span class="sxs-lookup"><span data-stu-id="e0273-135">You should see a Web page displayed that says "Simple Service" at the top and immediately below "You have created a service."</span></span> <span data-ttu-id="e0273-136">如果没有，则显示一条消息，在生成的页面的顶部："元数据发布，此服务当前已禁用。"</span><span class="sxs-lookup"><span data-stu-id="e0273-136">If not, a message at the top of the resulting page displays: "Metadata publishing for this service is currently disabled."</span></span>  
  
## <a name="example"></a><span data-ttu-id="e0273-137">示例</span><span class="sxs-lookup"><span data-stu-id="e0273-137">Example</span></span>  
 <span data-ttu-id="e0273-138">下面的代码示例显示了基本的 WCF 服务代码中发布服务元数据的实现。</span><span class="sxs-lookup"><span data-stu-id="e0273-138">The following code example shows the implementation of a basic WCF service that publishes metadata for the service in code.</span></span>  
  
 [!code-csharp[htPublishMetadataCode#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htpublishmetadatacode/cs/program.cs#11)]
 [!code-vb[htPublishMetadataCode#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htpublishmetadatacode/vb/program.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="e0273-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0273-139">See also</span></span>

- [<span data-ttu-id="e0273-140">如何：在托管应用程序中承载 WCF 服务</span><span class="sxs-lookup"><span data-stu-id="e0273-140">How to: Host a WCF Service in a Managed Application</span></span>](../../../../docs/framework/wcf/how-to-host-a-wcf-service-in-a-managed-application.md)
- [<span data-ttu-id="e0273-141">自承载</span><span class="sxs-lookup"><span data-stu-id="e0273-141">Self-Host</span></span>](../../../../docs/framework/wcf/samples/self-host.md)
- [<span data-ttu-id="e0273-142">元数据体系结构概述</span><span class="sxs-lookup"><span data-stu-id="e0273-142">Metadata Architecture Overview</span></span>](../../../../docs/framework/wcf/feature-details/metadata-architecture-overview.md)
- [<span data-ttu-id="e0273-143">使用元数据</span><span class="sxs-lookup"><span data-stu-id="e0273-143">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
- [<span data-ttu-id="e0273-144">如何：使用配置文件发布服务的元数据</span><span class="sxs-lookup"><span data-stu-id="e0273-144">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)
