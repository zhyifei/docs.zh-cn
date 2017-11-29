---
title: "如何：配置 WCF 服务以便与 ASP.NET Web 服务客户端进行互操作"
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
ms.assetid: 48e1cd90-de80-4d6c-846e-631878955762
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: ce9c0ca82803654b2268ff0440bbacec4cb0d0dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-wcf-service-to-interoperate-with-aspnet-web-service-clients"></a><span data-ttu-id="afe19-102">如何：配置 WCF 服务以便与 ASP.NET Web 服务客户端进行互操作</span><span class="sxs-lookup"><span data-stu-id="afe19-102">How to: Configure WCF Service to Interoperate with ASP.NET Web Service Clients</span></span>
<span data-ttu-id="afe19-103">若要将 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务终结点配置为可与 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web 服务客户端进行互操作，请使用 <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> 类型作为服务终结点的绑定类型。</span><span class="sxs-lookup"><span data-stu-id="afe19-103">To configure a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service endpoint to be interoperable with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service clients, use the <xref:System.ServiceModel.BasicHttpBinding?displayProperty=nameWithType> type as the binding type for your service endpoint.</span></span>  
  
 <span data-ttu-id="afe19-104">您可以根据需要在该绑定上启用对 HTTPS 和传输级客户端身份验证的支持。</span><span class="sxs-lookup"><span data-stu-id="afe19-104">You can optionally enable support for HTTPS and transport-level client authentication on the binding.</span></span> [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]<span data-ttu-id="afe19-105"> Web 服务客户端不支持 MTOM 消息编码，所以应该使 <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> 属性保留其默认值，即 <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="afe19-105"> Web service clients do not support MTOM message encoding, so the <xref:System.ServiceModel.BasicHttpBinding.MessageEncoding%2A?displayProperty=nameWithType> property should be left as its default value, which is <xref:System.ServiceModel.WSMessageEncoding.Text?displayProperty=nameWithType>.</span></span> <span data-ttu-id="afe19-106">ASP.Net Web 服务客户端不支持 WS-Security，所以应将 <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> 设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>。</span><span class="sxs-lookup"><span data-stu-id="afe19-106">ASP.Net Web Service clients do not support WS-Security, so the <xref:System.ServiceModel.BasicHttpBinding.Security%2A?displayProperty=nameWithType> should be set to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span>  
  
 <span data-ttu-id="afe19-107">若要使元数据[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]适用于服务[!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)]Web 服务代理生成工具 (即， [Web 服务描述语言工具 (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833)， [Web 服务发现工具 (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834)，和 Visual Studio 中的添加 Web 引用功能)，应公开一个 HTTP/GET 元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-107">To make the metadata for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service available to [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service proxy generation tools (that is, [Web Services Description Language Tool (Wsdl.exe)](http://go.microsoft.com/fwlink/?LinkId=73833), [Web Services Discovery Tool (Disco.exe)](http://go.microsoft.com/fwlink/?LinkId=73834), and the Add Web Reference feature in Visual Studio), you should expose an HTTP/GET metadata endpoint.</span></span>  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-code"></a><span data-ttu-id="afe19-108">在代码中添加与 ASP.NET Web 服务客户端兼容的 WCF 终结点</span><span class="sxs-lookup"><span data-stu-id="afe19-108">To add a WCF endpoint that is compatible with ASP.NET Web service clients in code</span></span>  
  
1.  <span data-ttu-id="afe19-109">创建一个新的 <xref:System.ServiceModel.BasicHttpBinding> 实例。</span><span class="sxs-lookup"><span data-stu-id="afe19-109">Create a new <xref:System.ServiceModel.BasicHttpBinding> instance</span></span>  
  
2.  <span data-ttu-id="afe19-110">（可选）将此服务终结点绑定的安全模式设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>，从而为此绑定启用传输安全。</span><span class="sxs-lookup"><span data-stu-id="afe19-110">Optionally enable transport security for this service endpoint binding by setting the security mode for the binding to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span> <span data-ttu-id="afe19-111">有关详细信息，请参阅[传输安全](../../../../docs/framework/wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-111">For details, please see [Transport Security](../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
3.  <span data-ttu-id="afe19-112">使用刚创建的绑定实例，向服务主机添加一个新的应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-112">Add a new application endpoint to your service host using the binding instance that you just created.</span></span> <span data-ttu-id="afe19-113">有关如何在代码中添加服务终结点的详细信息，请参阅[如何： 在代码中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-113">For details about how to add a service endpoint in code, see the [How to: Create a Service Endpoint in Code](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md).</span></span>  
  
4.  <span data-ttu-id="afe19-114">为服务启用一个 HTTP/GET 元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-114">Enable an HTTP/GET metadata endpoint for your service.</span></span> <span data-ttu-id="afe19-115">有关详细信息，请参阅[如何： 发布元数据服务使用代码](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-115">For details see [How to: Publish Metadata for a Service Using Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md).</span></span>  
  
### <a name="to-add-a-wcf-endpoint-that-is-compatible-with-aspnet-web-service-clients-in-a-configuration-file"></a><span data-ttu-id="afe19-116">在配置文件中添加与 ASP.NET Web 服务客户端兼容的 WCF 终结点</span><span class="sxs-lookup"><span data-stu-id="afe19-116">To add a WCF endpoint that is compatible with ASP.NET Web service clients in a configuration file</span></span>  
  
1.  <span data-ttu-id="afe19-117">创建一个新的 <xref:System.ServiceModel.BasicHttpBinding> 绑定配置。</span><span class="sxs-lookup"><span data-stu-id="afe19-117">Create a new <xref:System.ServiceModel.BasicHttpBinding> binding configuration.</span></span> <span data-ttu-id="afe19-118">有关详细信息，请参阅[如何： 在配置中指定服务绑定](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-118">For details, see the [How to: Specify a Service Binding in Configuration](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md).</span></span>  
  
2.  <span data-ttu-id="afe19-119">（可选）将此服务终结点绑定的安全模式设置为 <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>，从而为此绑定配置启用传输安全。</span><span class="sxs-lookup"><span data-stu-id="afe19-119">Optionally enable transport security for this service endpoint binding configuration by setting the security mode for the binding to <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>.</span></span> <span data-ttu-id="afe19-120">有关详细信息，请参阅[传输安全](../../../../docs/framework/wcf/feature-details/transport-security.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-120">For details, see [Transport Security](../../../../docs/framework/wcf/feature-details/transport-security.md).</span></span>  
  
3.  <span data-ttu-id="afe19-121">使用刚创建的绑定配置，为服务配置一个新的应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-121">Configure a new application endpoint for your service using the binding configuration that you just created.</span></span> <span data-ttu-id="afe19-122">有关如何在配置文件中添加服务终结点的详细信息，请参阅[如何： 在配置中创建服务终结点](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-122">For details about how to add a service endpoint in a configuration file, see the [How to: Create a Service Endpoint in Configuration](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md).</span></span>  
  
4.  <span data-ttu-id="afe19-123">为服务启用一个 HTTP/GET 元数据终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-123">Enable an HTTP/GET metadata endpoint for your service.</span></span> <span data-ttu-id="afe19-124">有关详细信息，请参阅[如何： 使用配置文件服务的发布元数据](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)。</span><span class="sxs-lookup"><span data-stu-id="afe19-124">For details see the [How to: Publish Metadata for a Service Using a Configuration File](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="afe19-125">示例</span><span class="sxs-lookup"><span data-stu-id="afe19-125">Example</span></span>  
 <span data-ttu-id="afe19-126">下面的示例代码演示如何在代码（或配置文件）中添加一个与 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Web 服务客户端兼容的 [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 终结点。</span><span class="sxs-lookup"><span data-stu-id="afe19-126">The following example code demonstrates how to add a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] endpoint that is compatible with [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] Web service clients in code and alternatively in configuration files.</span></span>  
  
 [!code-csharp[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/cs/program.cs#0)] 
 [!code-vb[C_HowTo-WCFServiceAndASMXClient#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/vb/program.vb#0)] 
 [!code-xml[C_HowTo-WCFServiceAndASMXClient#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto-wcfserviceandasmxclient/common/app.config#1)]     
  
## <a name="see-also"></a><span data-ttu-id="afe19-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="afe19-127">See Also</span></span>  
 [<span data-ttu-id="afe19-128">如何： 在代码中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="afe19-128">How to: Create a Service Endpoint in Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-code.md)  
 [<span data-ttu-id="afe19-129">如何： 使用代码为服务中发布元数据</span><span class="sxs-lookup"><span data-stu-id="afe19-129">How to: Publish Metadata for a Service Using Code</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 [<span data-ttu-id="afe19-130">如何：在配置中指定服务绑定</span><span class="sxs-lookup"><span data-stu-id="afe19-130">How to: Specify a Service Binding in Configuration</span></span>](../../../../docs/framework/wcf/how-to-specify-a-service-binding-in-configuration.md)  
 [<span data-ttu-id="afe19-131">如何： 在配置中创建服务终结点</span><span class="sxs-lookup"><span data-stu-id="afe19-131">How to: Create a Service Endpoint in Configuration</span></span>](../../../../docs/framework/wcf/feature-details/how-to-create-a-service-endpoint-in-configuration.md)  
 [<span data-ttu-id="afe19-132">如何： 使用配置文件为服务中发布元数据</span><span class="sxs-lookup"><span data-stu-id="afe19-132">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 [<span data-ttu-id="afe19-133">传输安全</span><span class="sxs-lookup"><span data-stu-id="afe19-133">Transport Security</span></span>](../../../../docs/framework/wcf/feature-details/transport-security.md)  
 [<span data-ttu-id="afe19-134">使用元数据</span><span class="sxs-lookup"><span data-stu-id="afe19-134">Using Metadata</span></span>](../../../../docs/framework/wcf/feature-details/using-metadata.md)
