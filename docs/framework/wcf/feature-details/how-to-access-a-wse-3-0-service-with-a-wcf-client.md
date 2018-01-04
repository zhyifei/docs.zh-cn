---
title: "如何：使用 WCF 客户端访问 WSE 3.0 服务"
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
ms.assetid: 1f9bcd9b-8f8f-47fa-8f1e-0d47236eb800
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: c70b7df47cb3f367318fb388ceda2163f538cb32
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-access-a-wse-30-service-with-a-wcf-client"></a><span data-ttu-id="c6320-102">如何：使用 WCF 客户端访问 WSE 3.0 服务</span><span class="sxs-lookup"><span data-stu-id="c6320-102">How to: Access a WSE 3.0 Service with a WCF Client</span></span>
<span data-ttu-id="c6320-103">当 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端配置为使用 2004 年 8 月版的 WS-Addressing 规范时，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端在网络级别与 Web Services Enhancements (WSE) 3.0 for Microsoft .NET 服务兼容。</span><span class="sxs-lookup"><span data-stu-id="c6320-103">[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] clients are wire-level compatible with Web Services Enhancements (WSE) 3.0 for Microsoft .NET services when [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] clients are configured to use the August 2004 version of the WS-Addressing specification.</span></span> <span data-ttu-id="c6320-104">但是，WSE 3.0 服务不支持元数据交换 (MEX) 协议，因此当你使用[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端类的安全设置不适用于生成[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端。</span><span class="sxs-lookup"><span data-stu-id="c6320-104">However, WSE 3.0 services do not support the metadata exchange (MEX) protocol, so when you use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client class, the security settings are not applied to the generated [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span> <span data-ttu-id="c6320-105">因此，在生成 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端后，必须指定 WSE 3.0 服务要求的安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-105">Therefore, you must specify the security settings that the WSE 3.0 service requires after the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is generated.</span></span>  
  
 <span data-ttu-id="c6320-106">您可以在考虑 WSE 3.0 服务的要求以及 WSE 3.0 服务和 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端之间的互操作要求的情况下，使用自定义绑定来应用这些安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-106">You can apply these security settings by using a custom binding to take into account the WSE 3.0 service's requirements and the interoperable requirements between a WSE 3.0 service and a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client.</span></span> <span data-ttu-id="c6320-107">这些互操作性要求包括前面提到的使用 2004 年 8 月版的 WS-Addressing 规范和 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt> 的 WSE 3.0 默认消息保护。</span><span class="sxs-lookup"><span data-stu-id="c6320-107">These interoperability requirements include the aforementioned use of the August 2004 WS-Addressing specification and the  WSE 3.0default message protection of <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncrypt>.</span></span> <span data-ttu-id="c6320-108">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 的默认消息保护为 <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>。</span><span class="sxs-lookup"><span data-stu-id="c6320-108">The default message protection for [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] is <xref:System.ServiceModel.Security.MessageProtectionOrder.SignBeforeEncryptAndEncryptSignature>.</span></span> <span data-ttu-id="c6320-109">本主题详细介绍如何创建与 WSE 3.0 服务互操作的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 绑定。</span><span class="sxs-lookup"><span data-stu-id="c6320-109">This topic details how to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] binding that interoperates with a WSE 3.0 service.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="c6320-110"> 还提供了融入此绑定的示例。</span><span class="sxs-lookup"><span data-stu-id="c6320-110"> also provides a sample that incorporates this binding.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c6320-111">此示例中，请参阅[与 ASMX Web 服务互操作](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md)。</span><span class="sxs-lookup"><span data-stu-id="c6320-111"> this sample, see [Interoperating with ASMX Web Services](../../../../docs/framework/wcf/samples/interoperating-with-asmx-web-services.md).</span></span>  
  
### <a name="to-access-a-wse-30-web-service-with-a-wcf-client"></a><span data-ttu-id="c6320-112">使用 WCF 客户端访问 WSE 3.0 Web 服务</span><span class="sxs-lookup"><span data-stu-id="c6320-112">To access a WSE 3.0 Web service with a WCF client</span></span>  
  
1.  <span data-ttu-id="c6320-113">运行[ServiceModel 元数据实用工具 (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md)创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]WSE 3.0 Web 服务客户端。</span><span class="sxs-lookup"><span data-stu-id="c6320-113">Run the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) to create a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client for the WSE 3.0 Web service.</span></span>  
  
     <span data-ttu-id="c6320-114">对于 WSE 3.0 Web 服务，会创建一个 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端。</span><span class="sxs-lookup"><span data-stu-id="c6320-114">For a WSE 3.0 Web service, a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client is created.</span></span> <span data-ttu-id="c6320-115">因为 WSE 3.0 不支持 MEX 协议，因此不能使用该工具检索 Web 服务的安全要求。</span><span class="sxs-lookup"><span data-stu-id="c6320-115">Because WSE 3.0 does not support the MEX protocol, you cannot use the tool to retrieve the security requirements for the Web service.</span></span> <span data-ttu-id="c6320-116">应用程序开发人员必须为客户端添加安全设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-116">The application developer must add the security settings for the client.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="c6320-117">创建[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]客户端，请参阅[如何： 创建客户端](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md)。</span><span class="sxs-lookup"><span data-stu-id="c6320-117"> creating a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client, see the [How to: Create a Client](../../../../docs/framework/wcf/how-to-create-a-wcf-client.md).</span></span>  
  
2.  <span data-ttu-id="c6320-118">创建一个类，表示可与 WSE 3.0 Web 服务进行通信的绑定。</span><span class="sxs-lookup"><span data-stu-id="c6320-118">Create a class that represents a binding that can communicate with WSE 3.0 Web services.</span></span>  
  
     <span data-ttu-id="c6320-119">下面的类是的一部分[与 WSE 互操作性](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)示例：</span><span class="sxs-lookup"><span data-stu-id="c6320-119">The following class is part of the [Interoperating with WSE](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41) sample:</span></span>  
  
    1.  <span data-ttu-id="c6320-120">创建一个从 <xref:System.ServiceModel.Channels.Binding> 类派生的类。</span><span class="sxs-lookup"><span data-stu-id="c6320-120">Create a class that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         <span data-ttu-id="c6320-121">下面的代码示例创建一个从 `WseHttpBinding` 类派生的名为 <xref:System.ServiceModel.Channels.Binding> 的类。</span><span class="sxs-lookup"><span data-stu-id="c6320-121">The following code example creates a class named `WseHttpBinding` that derives from the <xref:System.ServiceModel.Channels.Binding> class.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#1)]
         [!code-vb[c_WCFClientToWSEService#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#1)]  
  
    2.  <span data-ttu-id="c6320-122">向该类中添加属性，用以指定 WSE 服务使用的 WSE 完整断言、是否需要派生密钥、是否使用安全会话、是否需要签名确认以及消息保护设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-122">Add properties to the class that specify the WSE turnkey assertion used by the WSE service, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings.</span></span> <span data-ttu-id="c6320-123">在 WSE 3.0 中，完整断言指定客户端或 Web 服务的安全要求，它类似于 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 中绑定的身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="c6320-123">In WSE 3.0, a turnkey assertion specifies the security requirements for a client or Web service—similar to the authentication mode of a binding in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span>  
  
         <span data-ttu-id="c6320-124">下面的代码示例定义了 `SecurityAssertion`、`RequireDerivedKeys`、`EstablishSecurityContext` 和 `MessageProtectionOrder` 属性，这些属性分别指定 WSE 完整断言、是否需要派生密钥、是否使用安全会话、是否需要签名确认以及消息保护设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-124">The following code example defines the `SecurityAssertion`, `RequireDerivedKeys`, `EstablishSecurityContext`, and `MessageProtectionOrder` properties that specify the WSE turnkey assertion, whether derived keys are required, whether secure sessions are used, whether signature confirmations are required, and the message protection settings, respectively.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#3)]
         [!code-vb[c_WCFClientToWSEService#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#3)]  
  
    3.  <span data-ttu-id="c6320-125">重写 <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> 方法以设置绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c6320-125">Override the <xref:System.ServiceModel.Channels.Binding.CreateBindingElements%2A> method to set the binding properties.</span></span>  
  
         <span data-ttu-id="c6320-126">下面的代码示例通过获取 `SecurityAssertion` 和 `MessageProtectionOrder` 属性的值来指定传输协议、消息编码和消息保护设置。</span><span class="sxs-lookup"><span data-stu-id="c6320-126">The following code example specifies the transport, message encoding, and message protection settings by getting the values of the `SecurityAssertion` and `MessageProtectionOrder` properties.</span></span>  
  
         [!code-csharp[c_WCFClientToWSEService#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/wsehttpbinding.cs#2)]
         [!code-vb[c_WCFClientToWSEService#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/wsehttpbinding.vb#2)]  
  
3.  <span data-ttu-id="c6320-127">在客户端应用程序代码中，添加设置绑定属性的代码。</span><span class="sxs-lookup"><span data-stu-id="c6320-127">In the client application code, add code to set the binding properties.</span></span>  
  
     <span data-ttu-id="c6320-128">下面的代码示例指定 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端必须使用 WSE 3.0 `AnonymousForCertificate` 完整安全断言定义的消息保护和身份验证。</span><span class="sxs-lookup"><span data-stu-id="c6320-128">The following code example specifies that the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client must use message protection and authentication as defined by the WSE 3.0 `AnonymousForCertificate` turnkey security assertion.</span></span> <span data-ttu-id="c6320-129">此外，还需要安全会话和派生密钥。</span><span class="sxs-lookup"><span data-stu-id="c6320-129">Additionally, secure sessions and derived keys are required.</span></span>  
  
     [!code-csharp[c_WCFClientToWSEService#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_wcfclienttowseservice/cs/client.cs#4)]
     [!code-vb[c_WCFClientToWSEService#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_wcfclienttowseservice/vb/client.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="c6320-130">示例</span><span class="sxs-lookup"><span data-stu-id="c6320-130">Example</span></span>  
 <span data-ttu-id="c6320-131">下面的代码示例定义了一个自定义绑定，该绑定公开对应于 WSE 3.0 完整安全断言的各个属性的属性。</span><span class="sxs-lookup"><span data-stu-id="c6320-131">The following code example defines a custom binding that exposes properties that correspond to the properties of a WSE 3.0 turnkey security assertion.</span></span> <span data-ttu-id="c6320-132">之后，使用该自定义绑定（名为 `WseHttpBinding`）来指定与 WSSecurityAnonymous WSE 3.0 QuickStart 示例通信的 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] 客户端的绑定属性。</span><span class="sxs-lookup"><span data-stu-id="c6320-132">That custom binding, which is named `WseHttpBinding`, is then used to specify the binding properties for a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] client that communicates with the WSSecurityAnonymous WSE 3.0 QuickStart sample.</span></span>  
  
  
  
## <a name="see-also"></a><span data-ttu-id="c6320-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6320-133">See Also</span></span>  
 <xref:System.ServiceModel.Channels.Binding>  
 [<span data-ttu-id="c6320-134">与 WSE 互操作性</span><span class="sxs-lookup"><span data-stu-id="c6320-134">Interoperating with WSE</span></span>](http://msdn.microsoft.com/en-us/f6816861-96a0-45f9-8736-8e4e82cd3a41)
