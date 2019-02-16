---
title: 如何：配置基本 Windows Communication Foundation 客户端
ms.date: 09/14/2018
helpviewer_keywords:
- WCF clients [WCF], configuring
ms.assetid: d067b86d-afb0-47bf-94f6-45180a3d8d78
ms.openlocfilehash: 18acec48b2af78877f99335da38ccb0ae8942824
ms.sourcegitcommit: 0069cb3de8eed4e92b2195d29e5769a76111acdd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/16/2019
ms.locfileid: "56332309"
---
# <a name="how-to-configure-a-basic-windows-communication-foundation-client"></a><span data-ttu-id="b2374-102">如何：配置基本 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="b2374-102">How to: Configure a Basic Windows Communication Foundation Client</span></span>

<span data-ttu-id="b2374-103">这是创建基本 Windows Communication Foundation (WCF) 应用程序所需的六项任务的第 5 个。</span><span class="sxs-lookup"><span data-stu-id="b2374-103">This is the fifth of six tasks required to create a basic Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="b2374-104">有关全部六项任务的概述，请参阅[入门教程](../../../docs/framework/wcf/getting-started-tutorial.md)主题。</span><span class="sxs-lookup"><span data-stu-id="b2374-104">For an overview of all six of the tasks, see the [Getting Started Tutorial](../../../docs/framework/wcf/getting-started-tutorial.md) topic.</span></span>

<span data-ttu-id="b2374-105">本主题讨论使用生成的客户端配置文件**添加服务引用**Visual Studio 的功能或[ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)。</span><span class="sxs-lookup"><span data-stu-id="b2374-105">This topic discusses the client configuration file that was generated using the **Add Service Reference** functionality of Visual Studio or the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span> <span data-ttu-id="b2374-106">配置客户端包括指定客户端用于访问服务的终结点。</span><span class="sxs-lookup"><span data-stu-id="b2374-106">Configuring the client consists of specifying the endpoint that the client uses to access the service.</span></span> <span data-ttu-id="b2374-107">终结点有一个地址、 绑定和协定，并且必须配置客户端的过程中指定其中每项功能。</span><span class="sxs-lookup"><span data-stu-id="b2374-107">An endpoint has an address, a binding, and a contract, and each of these must be specified in the process of configuring the client.</span></span>

## <a name="configure-a-windows-communication-foundation-client"></a><span data-ttu-id="b2374-108">配置 Windows Communication Foundation 客户端</span><span class="sxs-lookup"><span data-stu-id="b2374-108">Configure a Windows Communication Foundation client</span></span>

<span data-ttu-id="b2374-109">从 GettingStartedClient 项目打开生成的配置文件 (App.config)。</span><span class="sxs-lookup"><span data-stu-id="b2374-109">Open the generated configuration file (App.config) from the GettingStartedClient project.</span></span> <span data-ttu-id="b2374-110">下面的示例显示了生成的配置文件。</span><span class="sxs-lookup"><span data-stu-id="b2374-110">The following example is a view of the generated configuration file.</span></span> <span data-ttu-id="b2374-111">下[ \<system.serviceModel >](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md)部分中，找到[\<终结点 >](../configure-apps/file-schema/wcf/endpoint-element.md)元素。</span><span class="sxs-lookup"><span data-stu-id="b2374-111">Under the [\<system.serviceModel>](../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, find the [\<endpoint>](../configure-apps/file-schema/wcf/endpoint-element.md) element.</span></span>

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

<span data-ttu-id="b2374-112">此示例将配置客户端用于访问位于以下地址的服务的终结点： `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`。</span><span class="sxs-lookup"><span data-stu-id="b2374-112">This example configures the endpoint that the client uses to access the service that is located at the following address: `http://localhost:8000/ServiceModelSamples/Service/CalculatorService`.</span></span>

<span data-ttu-id="b2374-113">该终结点元素指定 `ServiceReference1.ICalculator` 服务约定用于 WCF 客户端和服务之间的通信。</span><span class="sxs-lookup"><span data-stu-id="b2374-113">The endpoint element specifies that the `ServiceReference1.ICalculator` service contract is used for communication between the WCF client and service.</span></span> <span data-ttu-id="b2374-114">使用系统提供的 <xref:System.ServiceModel.WSHttpBinding> 配置 WCF 通道。</span><span class="sxs-lookup"><span data-stu-id="b2374-114">The WCF channel is configured with the system-provided <xref:System.ServiceModel.WSHttpBinding>.</span></span> <span data-ttu-id="b2374-115">此约定使用生成**添加服务引用**Visual Studio 中。</span><span class="sxs-lookup"><span data-stu-id="b2374-115">This contract was generated by using **Add Service Reference** in Visual Studio.</span></span> <span data-ttu-id="b2374-116">它基本上是在 GettingStartedLib 项目中定义的约定的副本。</span><span class="sxs-lookup"><span data-stu-id="b2374-116">It is essentially a copy of the contract that was defined in the GettingStartedLib project.</span></span> <span data-ttu-id="b2374-117">
  <xref:System.ServiceModel.WSHttpBinding> 绑定指定 HTTP 作为传输协议、可互操作安全性以及其他配置详细信息。</span><span class="sxs-lookup"><span data-stu-id="b2374-117">The <xref:System.ServiceModel.WSHttpBinding> binding specifies HTTP as the transport, interoperable security, and other configuration details.</span></span>

<span data-ttu-id="b2374-118">有关如何使用此配置中使用生成的客户端的详细信息，请参阅[如何：使用客户端](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="b2374-118">For more information about how to use the generated client with this configuration, see [How to: Use a Client](../../../docs/framework/wcf/how-to-use-a-wcf-client.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b2374-119">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b2374-119">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b2374-120">如何：使用 WCF 客户端</span><span class="sxs-lookup"><span data-stu-id="b2374-120">How to: Use a WCF client</span></span>](../../../docs/framework/wcf/how-to-use-a-wcf-client.md)

## <a name="see-also"></a><span data-ttu-id="b2374-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="b2374-121">See also</span></span>

- [<span data-ttu-id="b2374-122">使用绑定配置服务和客户端</span><span class="sxs-lookup"><span data-stu-id="b2374-122">Using Bindings to Configure Services and Clients</span></span>](../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="b2374-123">ServiceModel 元数据实用工具 (Svcutil.exe)</span><span class="sxs-lookup"><span data-stu-id="b2374-123">ServiceModel Metadata Utility Tool (Svcutil.exe)</span></span>](../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)
- [<span data-ttu-id="b2374-124">如何：创建客户端</span><span class="sxs-lookup"><span data-stu-id="b2374-124">How to: Create a Client</span></span>](../../../docs/framework/wcf/how-to-create-a-wcf-client.md)
- [<span data-ttu-id="b2374-125">入门</span><span class="sxs-lookup"><span data-stu-id="b2374-125">Getting Started</span></span>](../../../docs/framework/wcf/samples/getting-started-sample.md)
- [<span data-ttu-id="b2374-126">自承载</span><span class="sxs-lookup"><span data-stu-id="b2374-126">Self-Host</span></span>](../../../docs/framework/wcf/samples/self-host.md)