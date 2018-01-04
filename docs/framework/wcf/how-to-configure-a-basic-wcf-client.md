---
title: "如何：配置基本 Windows Communication Foundation 客户端"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
caps.latest.revision: "47"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 377a67edb37ada5c9e1b022d50a4718b5740afd8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="5c8f9-102">如何：配置基本 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="5c8f9-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>
<span data-ttu-id="5c8f9-103">这是创建基本 [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] 应用程序所需的六项任务中的第五项任务。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-103">This is the fifth of six tasks required to create a basic [!INCLUDE[indigo1](../../../includes/indigo1-md.md)] application.</span></span> <span data-ttu-id="5c8f9-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>  
  
 <span data-ttu-id="5c8f9-105">此主题 disuccess 使用的添加服务引用功能生成的客户端配置文件[!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)]或[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-105">This topic disuccess the client configuration file that was generated using the Add Service Reference functionality of [!INCLUDE[vs_current_long](../../../includes/vs-current-long-md.md)] or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="5c8f9-106">配置客户端包括指定客户端用于访问服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="5c8f9-107">每个终结点都有一个地址、一个绑定和一个协定，所有这些元素都必须在配置客户端的过程中指定。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-107">An endpoint has an address, a binding and a contract, and each of these must be specified in the process of configuring the client.</span></span>  
  
### <a name="to-configure-a-windows-communication-foundation-client"></a><span data-ttu-id="5c8f9-108">配置 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="5c8f9-108">To configure a Windows Communication Foundation client</span></span>  
  
1.  <span data-ttu-id="5c8f9-109">从 GettingStartedClient 项目打开生成的配置文件 (App.config)。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="5c8f9-110">下面的示例显示了生成的配置文件。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="5c8f9-111">下[ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)部分中，找到[\<终结点 >](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017)元素。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](http://msdn.microsoft.com/en-us/13aa23b7-2f08-4add-8dbf-a99f8127c017) element.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
        <startup>   
          <!-- specifies the version of WCF to use-->  
            <supportedRuntime version="v4.0" sku=".NETFramework,Version=v4.5,Profile=Client" />  
        </startup>  
        <system.serviceModel>  
            <bindings>  
                <!-- Uses wsHttpBinding-->  
                <wsHttpBinding>  
                    <binding name="WSHttpBinding_ICalculator" />  
                </wsHttpBinding>  
            </bindings>  
            <client>  
                <!-- specifies the endpoint to use when calling the service -->  
                <endpoint address="http://localhost:8000/ServiceModelSamples/Service/CalculatorService"  
                    binding="wsHttpBinding" bindingConfiguration="WSHttpBinding_ICalculator"  
                    contract="ServiceReference1.ICalculator" name="WSHttpBinding_ICalculator">  
                    <identity>  
                        <userPrincipalName value="migree@redmond.corp.microsoft.com" />  
                    </identity>  
                </endpoint>  
            </client>  
        </system.serviceModel>  
    </configuration>   
    ```  
  
     <span data-ttu-id="5c8f9-112">此示例配置的终结点可供客户端在访问位于以下地址的服务时使用：http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span><span class="sxs-lookup"><span data-stu-id="5c8f9-112">This example configures the endpoint that the client uses to access the service that is located at the following address: http://localhost:8000/ServiceModelSamples/Service/CalculatorService</span></span>  
  
     <span data-ttu-id="5c8f9-113">该终结点元素指定 `ServiceReference1.ICalculator` 服务约定用于 WCF 客户端和服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="5c8f9-114">配置 WCF 通道时使用系统提供 <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-114">The WCF channel is configured with the system-provided <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`>.</span></span> <span data-ttu-id="5c8f9-115">此约定是使用 Visual Studio 中的“添加服务引用”生成的。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-115">This contract was generated by using Add Service Reference in Visual Studio.</span></span> <span data-ttu-id="5c8f9-116">它基本上是在 GettingStartedLib 项目中定义的约定的副本。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="5c8f9-117"><<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> 绑定指定 HTTP 作为传输协议、 可互操作安全性和其他配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-117">The <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>  
  
2.  [!INCLUDE[crabout](../../../includes/crabout-md.md)]<span data-ttu-id="5c8f9-118">如何使用生成的客户端在此配置，请参阅[如何： 使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="5c8f9-118"> how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c8f9-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="5c8f9-119">See Also</span></span>  
 [<span data-ttu-id="5c8f9-120">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="5c8f9-120">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="5c8f9-121">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="5c8f9-121">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)  
 [<span data-ttu-id="5c8f9-122">如何：创建客户端</span><span class="sxs-lookup"><span data-stu-id="5c8f9-122">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)  
 [<span data-ttu-id="5c8f9-123">入门</span><span class="sxs-lookup"><span data-stu-id="5c8f9-123">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)  
 [<span data-ttu-id="5c8f9-124">自承载</span><span class="sxs-lookup"><span data-stu-id="5c8f9-124">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)
