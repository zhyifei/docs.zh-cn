---
title: 如何：配置自定义 WS-Metadata Exchange 绑定
ms.date: 03/30/2017
helpviewer_keywords:
- WS-Metadata Exchange [WCF]
- WS-Metadata Exchange [WCF], configuring a custom binding
ms.assetid: cdba4d73-da64-4805-bc56-9822becfd1e4
ms.openlocfilehash: 9676ae4053553b84488602627b28790aae22eff6
ms.sourcegitcommit: 59e36e65ac81cdd094a5a84617625b2a0ff3506e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2020
ms.locfileid: "80345284"
---
# <a name="how-to-configure-a-custom-ws-metadata-exchange-binding"></a><span data-ttu-id="db6ae-102">如何：配置自定义 WS-Metadata Exchange 绑定</span><span class="sxs-lookup"><span data-stu-id="db6ae-102">How to: Configure a Custom WS-Metadata Exchange Binding</span></span>
<span data-ttu-id="db6ae-103">本主题将说明如何配置自定义 WS-Metadata 交换绑定。</span><span class="sxs-lookup"><span data-stu-id="db6ae-103">This topic will explain how to configure a custom WS-Metadata exchange binding.</span></span> <span data-ttu-id="db6ae-104">Windows 通信基础 （WCF） 包括四个系统定义的元数据绑定，但您可以使用所需的任何绑定发布元数据。</span><span class="sxs-lookup"><span data-stu-id="db6ae-104">Windows Communication Foundation (WCF) includes four system-defined metadata bindings, but you can publish metadata using any binding you want.</span></span> <span data-ttu-id="db6ae-105">本主题将演示如何使用 `wsHttpBinding` 发布元数据。</span><span class="sxs-lookup"><span data-stu-id="db6ae-105">This topic will show you how to publish metadata using the `wsHttpBinding`.</span></span> <span data-ttu-id="db6ae-106">此绑定提供了以安全方式公开元数据的选择。</span><span class="sxs-lookup"><span data-stu-id="db6ae-106">This binding gives you the option of exposing metadata in a secure way.</span></span> <span data-ttu-id="db6ae-107">本文中的代码基于[入门](../samples/getting-started-sample.md)。</span><span class="sxs-lookup"><span data-stu-id="db6ae-107">The code in this article is based on the [Getting Started](../samples/getting-started-sample.md).</span></span>  
  
### <a name="using-a-configuration-file"></a><span data-ttu-id="db6ae-108">使用配置文件</span><span class="sxs-lookup"><span data-stu-id="db6ae-108">Using a configuration file</span></span>  
  
1. <span data-ttu-id="db6ae-109">在服务的配置文件中，添加一个包含 `serviceMetadata` 标记的服务行为：</span><span class="sxs-lookup"><span data-stu-id="db6ae-109">In the service's configuration file, add a service behavior that contains the `serviceMetadata` tag:</span></span>  
  
    ```xml  
    <behaviors>  
       <serviceBehaviors>  
         <behavior name="CalculatorServiceBehavior">  
           <serviceMetadata httpGetEnabled="True"/>  
         </behavior>  
       </serviceBehaviors>  
    </behaviors>  
    ```  
  
2. <span data-ttu-id="db6ae-110">将一个 `behaviorConfiguration` 属性添加到该服务标记，该属性引用这一新行为：</span><span class="sxs-lookup"><span data-stu-id="db6ae-110">Add a `behaviorConfiguration` attribute to the service tag that references this new behavior:</span></span>  
  
    ```xml  
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
    behaviorConfiguration="CalculatorServiceBehavior" />
    ```  
  
3. <span data-ttu-id="db6ae-111">添加一个元数据终结点，该终结点将 mex 指定为地址，将 `wsHttpBinding` 指定为绑定，并将 <xref:System.ServiceModel.Description.IMetadataExchange> 指定为协定：</span><span class="sxs-lookup"><span data-stu-id="db6ae-111">Add a metadata endpoint specifying mex as the address, `wsHttpBinding` as the binding, and <xref:System.ServiceModel.Description.IMetadataExchange> as the contract:</span></span>  
  
    ```xml  
    <endpoint address="mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange" />  
    ```  
  
4. <span data-ttu-id="db6ae-112">若要验证元数据交换终结点是否能够正常工作，请在客户端配置文件中添加一个终结点标记：</span><span class="sxs-lookup"><span data-stu-id="db6ae-112">To verify the metadata exchange endpoint is working correctly add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
5. <span data-ttu-id="db6ae-113">在客户端的 Main() 方法中，创建一个新的 <xref:System.ServiceModel.Description.MetadataExchangeClient> 实例，将该实例的 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 属性设置为 `true`，调用 <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>，然后循环访问返回的元数据集合：</span><span class="sxs-lookup"><span data-stu-id="db6ae-113">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set its <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
### <a name="configuring-by-code"></a><span data-ttu-id="db6ae-114">通过代码进行配置</span><span class="sxs-lookup"><span data-stu-id="db6ae-114">Configuring by code</span></span>  
  
1. <span data-ttu-id="db6ae-115">创建一个 <xref:System.ServiceModel.WSHttpBinding> 绑定实例：</span><span class="sxs-lookup"><span data-stu-id="db6ae-115">Create a <xref:System.ServiceModel.WSHttpBinding> binding instance:</span></span>  
  
    ```csharp  
    WSHttpBinding binding = new WSHttpBinding();  
    ```  
  
2. <span data-ttu-id="db6ae-116">创建一个 <xref:System.ServiceModel.ServiceHost> 实例：</span><span class="sxs-lookup"><span data-stu-id="db6ae-116">Create a <xref:System.ServiceModel.ServiceHost> instance:</span></span>  
  
    ```csharp  
    ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress);  
    ```  
  
3. <span data-ttu-id="db6ae-117">添加一个服务终结点，并添加一个 <xref:System.ServiceModel.Description.ServiceMetadataBehavior> 实例：</span><span class="sxs-lookup"><span data-stu-id="db6ae-117">Add a service endpoint and add a <xref:System.ServiceModel.Description.ServiceMetadataBehavior> instance:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(ICalculator), binding, baseAddress);  
    ServiceMetadataBehavior smb = new ServiceMetadataBehavior();  
    smb.HttpGetEnabled = true;  
    serviceHost.Description.Behaviors.Add(smb);  
    ```  
  
4. <span data-ttu-id="db6ae-118">添加一个元数据交换终结点，并且指定先前创建的 <xref:System.ServiceModel.WSHttpBinding>：</span><span class="sxs-lookup"><span data-stu-id="db6ae-118">Add a metadata exchange endpoint, specifying the <xref:System.ServiceModel.WSHttpBinding> created earlier:</span></span>  
  
    ```csharp  
    serviceHost.AddServiceEndpoint(typeof(IMetadataExchange), binding, mexAddress);  
    ```  
  
5. <span data-ttu-id="db6ae-119">若要验证元数据交换终结点是否能够正常工作，请在客户端配置文件中添加一个终结点标记：</span><span class="sxs-lookup"><span data-stu-id="db6ae-119">To verify that the metadata exchange endpoint is working correctly, add an endpoint tag in the client configuration file:</span></span>  
  
    ```xml  
    <endpoint name="MyMexEndpoint"               address="http://localhost:8000/servicemodelsamples/service/mex"  
              binding="wsHttpBinding"  
              contract="IMetadataExchange"/>  
    ```  
  
6. <span data-ttu-id="db6ae-120">在客户端的 Main() 方法中，创建一个新的 <xref:System.ServiceModel.Description.MetadataExchangeClient> 实例，将该实例的 <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> 属性设置为 `true`，调用 <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A>，然后循环访问返回的元数据集合：</span><span class="sxs-lookup"><span data-stu-id="db6ae-120">In the client's Main() method, create a new <xref:System.ServiceModel.Description.MetadataExchangeClient> instance, set the <xref:System.ServiceModel.Description.MetadataExchangeClient.ResolveMetadataReferences%2A> property to `true`, call <xref:System.ServiceModel.Description.MetadataExchangeClient.GetMetadata%2A> and then iterate through the collection of metadata returned:</span></span>  
  
    ```csharp  
    string mexAddress = "http://localhost:8000/servicemodelsamples/service/mex";  
  
    MetadataExchangeClient mexClient = new MetadataExchangeClient("MyMexEndpoint");  
    mexClient.ResolveMetadataReferences = true;  
    MetadataSet mdSet = mexClient.GetMetadata(new EndpointAddress(mexAddress));  
    foreach (MetadataSection section in mdSet.MetadataSections)  
    Console.WriteLine("Metadata section: " + section.Dialect.ToString());  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="db6ae-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="db6ae-121">See also</span></span>

- [<span data-ttu-id="db6ae-122">元数据发布行为</span><span class="sxs-lookup"><span data-stu-id="db6ae-122">Metadata Publishing Behavior</span></span>](../samples/metadata-publishing-behavior.md)
- [<span data-ttu-id="db6ae-123">检索元数据</span><span class="sxs-lookup"><span data-stu-id="db6ae-123">Retrieve Metadata</span></span>](../samples/retrieve-metadata.md)
- [<span data-ttu-id="db6ae-124">元数据</span><span class="sxs-lookup"><span data-stu-id="db6ae-124">Metadata</span></span>](../feature-details/metadata.md)
- [<span data-ttu-id="db6ae-125">发布元数据</span><span class="sxs-lookup"><span data-stu-id="db6ae-125">Publishing Metadata</span></span>](../feature-details/publishing-metadata.md)
- [<span data-ttu-id="db6ae-126">发布元数据终结点</span><span class="sxs-lookup"><span data-stu-id="db6ae-126">Publishing Metadata Endpoints</span></span>](../publishing-metadata-endpoints.md)
