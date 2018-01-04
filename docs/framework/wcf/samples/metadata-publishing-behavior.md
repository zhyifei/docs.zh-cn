---
title: "元数据发布行为"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0892a4716f67509836c8ad3b9ed66ad226a9e748
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="fdf9a-102">元数据发布行为</span><span class="sxs-lookup"><span data-stu-id="fdf9a-102">Metadata Publishing Behavior</span></span>
<span data-ttu-id="fdf9a-103">“元数据发布行为”示例演示如何控制服务的元数据发布功能。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-103">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="fdf9a-104">为了防止无意中泄露潜在的敏感服务元数据，[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务的默认配置将禁用元数据发布。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-104">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="fdf9a-105">默认情况下此行为是安全的，但也意味着您无法使用元数据导入工具（例如 Svcutil.exe）生成调用服务所需的客户端代码，除非在配置中显式启用服务的元数据发布行为。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-105">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fdf9a-106">为清楚起见，本示例演示如何创建不安全的元数据发布终结点。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-106">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="fdf9a-107">此类终结点或许可以供未通过身份验证的匿名使用者使用，因此在部署此类终结点之前，必须谨慎以确保适合公开透露服务元数据。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-107">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="fdf9a-108">请参阅[自定义安全元数据终结点](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md)示例有关保护元数据终结点的示例。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-108">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="fdf9a-109">示例基于[入门](../../../../docs/framework/wcf/samples/getting-started-sample.md)，该类实现`ICalculator`服务协定。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-109">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="fdf9a-110">在此示例中，客户端是一个控制台应用程序 (.exe)，服务是由 Internet 信息服务 (IIS) 承载的。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-110">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fdf9a-111">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="fdf9a-112">若要使服务公开元数据，必须在服务上配置 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-112">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="fdf9a-113">当存在此行为时，可以通过如下方法发布元数据：配置一个终结点，将 <xref:System.ServiceModel.Description.IMetadataExchange> 协定作为 WS-MetadataExchange (MEX) 协议的实现来公开。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-113">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="fdf9a-114">为方便起见，为此协定指定了缩写的配置名称“IMetadataExchange”。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-114">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="fdf9a-115">此示例使用的是 `mexHttpBinding`，这是一种便于使用的标准绑定，与安全模式设置为 `wsHttpBinding` 的 `None` 等效。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-115">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="fdf9a-116">在终结点中使用相对地址“mex”，当针对服务基址对其进行解析时将得到终结点地址 http://localhost/servicemodelsamples/service.svc/mex。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-116">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span> <span data-ttu-id="fdf9a-117">下面演示了行为配置：</span><span class="sxs-lookup"><span data-stu-id="fdf9a-117">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="fdf9a-118">下面演示了 MEX 终结点。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-118">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="fdf9a-119">此示例将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> 属性设置为 `true`，它还使用 HTTP GET 公开服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-119">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="fdf9a-120">若要启用 HTTP GET 元数据终结点，服务必须具有 HTTP 基址。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-120">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="fdf9a-121">在服务的基址中使用了查询字符串 `?wsdl` 以访问元数据。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-121">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="fdf9a-122">例如，若要在 Web 浏览器中查看服务的 WSDL，应使用地址 http://localhost/servicemodelsamples/service.svc?wsdl。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-122">For example, to see the WSDL for the service in a Web browser you would use the address http://localhost/servicemodelsamples/service.svc?wsdl.</span></span> <span data-ttu-id="fdf9a-123">或者，可以通过将 <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> 设置为 `true`，使用此行为通过 HTTPS 公开元数据。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-123">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="fdf9a-124">这需要一个 HTTPS 基址。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-124">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="fdf9a-125">若要访问服务的 MEX 终结点使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-125">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="fdf9a-126">这将根据服务的元数据生成一个客户端。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-126">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="fdf9a-127">若要使用 HTTP GET 访问服务的元数据，请将浏览器指向 http://localhost/servicemodelsamples/service.svc?wsdl。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-127">To access the service's metadata using HTTP GET, point your browser to http://localhost/servicemodelsamples/service.svc?wsdl.</span></span>  
  
 <span data-ttu-id="fdf9a-128">如果移除此行为并尝试打开服务，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-128">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="fdf9a-129">发生此错误是因为，如果没有该行为，使用 `IMetadataExchange` 协定配置的终结点则没有实现。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-129">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="fdf9a-130">如果将 `HttpGetEnabled` 设置为 `false`，您将看到 CalculatorService 帮助页面，而不是服务的元数据。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-130">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="fdf9a-131">设置、生成和运行示例</span><span class="sxs-lookup"><span data-stu-id="fdf9a-131">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="fdf9a-132">确保已执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="fdf9a-133">若要生成 C# 或 Visual Basic .NET 版本的解决方案，请按照 [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="fdf9a-134">若要在单或跨计算机配置上运行示例，请按照中的说明[运行 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/running-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="fdf9a-135">您的计算机上可能已安装这些示例。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="fdf9a-136">在继续操作之前，请先检查以下（默认）目录：</span><span class="sxs-lookup"><span data-stu-id="fdf9a-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="fdf9a-137">如果此目录不存在，请访问 [针对 .NET Framework 4 的 Windows Communication Foundation (WCF) 和 Windows Workflow Foundation (WF) 示例](http://go.microsoft.com/fwlink/?LinkId=150780) 以下载所有 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 和 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 示例。</span><span class="sxs-lookup"><span data-stu-id="fdf9a-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="fdf9a-138">此示例位于以下目录：</span><span class="sxs-lookup"><span data-stu-id="fdf9a-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## <a name="see-also"></a><span data-ttu-id="fdf9a-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="fdf9a-139">See Also</span></span>
