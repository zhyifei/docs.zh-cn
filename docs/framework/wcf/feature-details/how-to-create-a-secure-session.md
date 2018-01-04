---
title: "如何：创建安全会话"
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
helpviewer_keywords: security [WCF], creating a session
ms.assetid: b6f42b5a-bbf7-45cf-b917-7ec9fa7ae110
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: cd4f91ef5389dd4b8ecb63c1148d3a86918f2d10
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-secure-session"></a><span data-ttu-id="0250a-102">如何：创建安全会话</span><span class="sxs-lookup"><span data-stu-id="0250a-102">How to: Create a Secure Session</span></span>
<span data-ttu-id="0250a-103">除[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)绑定、 中的系统提供绑定[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]自动使用安全会话中启用消息安全时。</span><span class="sxs-lookup"><span data-stu-id="0250a-103">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, the system-provided bindings in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] automatically use secure sessions when message security is enabled.</span></span>  
  
 <span data-ttu-id="0250a-104">默认情况下，安全会话不会在已回收的 Web 服务器中存在。</span><span class="sxs-lookup"><span data-stu-id="0250a-104">By default, secure sessions do not survive a Web server that is recycled.</span></span> <span data-ttu-id="0250a-105">建立安全会话时，客户端和服务将缓存与安全会话关联的密钥。</span><span class="sxs-lookup"><span data-stu-id="0250a-105">When a secure session is established, the client and the service cache the key that is associated with the secure session.</span></span> <span data-ttu-id="0250a-106">交换消息时，只交换已缓存密钥的标识符。</span><span class="sxs-lookup"><span data-stu-id="0250a-106">As the messages are exchanged, only an identifier to the cached key is exchanged.</span></span> <span data-ttu-id="0250a-107">如果回收了 Web 服务器，则也会回收缓存，因此 Web 服务器将无法检索该标识符的已缓存密钥。</span><span class="sxs-lookup"><span data-stu-id="0250a-107">If the Web server is recycled, the cache is also recycled, such that the Web server cannot retrieve the cached key for the identifier.</span></span> <span data-ttu-id="0250a-108">如果发生这种情况，将会引发异常并返回至客户端。</span><span class="sxs-lookup"><span data-stu-id="0250a-108">If this happens, an exception is thrown back to the client.</span></span> <span data-ttu-id="0250a-109">使用有状态安全上下文令牌 (SCT) 的安全会话可以在回收 Web 服务器后存在。</span><span class="sxs-lookup"><span data-stu-id="0250a-109">Secure sessions that use a stateful security context token (SCT) can survive a Web server being recycled.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0250a-110">在安全会话中，使用有状态 SCT，请参阅[如何： 为安全会话创建安全上下文令牌](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md)。</span><span class="sxs-lookup"><span data-stu-id="0250a-110"> using a stateful SCT in a secure session, see [How to: Create a Security Context Token for a Secure Session](../../../../docs/framework/wcf/feature-details/how-to-create-a-security-context-token-for-a-secure-session.md).</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-one-of-the-system-provided-bindings"></a><span data-ttu-id="0250a-111">通过使用系统提供的一个绑定指定服务使用安全会话</span><span class="sxs-lookup"><span data-stu-id="0250a-111">To specify that a service uses secure sessions by using one of the system-provided bindings</span></span>  
  
-   <span data-ttu-id="0250a-112">配置服务以使用支持消息安全的系统提供的绑定。</span><span class="sxs-lookup"><span data-stu-id="0250a-112">Configure a service to use a system-provided binding that supports message security.</span></span>  
  
     <span data-ttu-id="0250a-113">除[ \<basicHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)绑定，当系统提供的绑定配置为使用消息安全，[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]自动使用安全会话。</span><span class="sxs-lookup"><span data-stu-id="0250a-113">With the exception of the [\<basicHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) binding, when the system-provided bindings are configured to use message security, [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] automatically uses secure sessions.</span></span> <span data-ttu-id="0250a-114">下表列出了支持消息安全的系统提供的绑定以及消息安全是否是默认的安全机制。</span><span class="sxs-lookup"><span data-stu-id="0250a-114">The following table lists the system-provided bindings that support message security and whether message security is the default security mechanism.</span></span>  
  
    |<span data-ttu-id="0250a-115">系统提供的绑定</span><span class="sxs-lookup"><span data-stu-id="0250a-115">System-provided binding</span></span>|<span data-ttu-id="0250a-116">配置元素</span><span class="sxs-lookup"><span data-stu-id="0250a-116">Configuration element</span></span>|<span data-ttu-id="0250a-117">默认情况下是否启用消息安全</span><span class="sxs-lookup"><span data-stu-id="0250a-117">Message security on by default</span></span>|  
    |------------------------------|---------------------------|------------------------------------|  
    |<xref:System.ServiceModel.BasicHttpBinding>|[<span data-ttu-id="0250a-118">\<basicHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-118">\<basicHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md)|<span data-ttu-id="0250a-119">否</span><span class="sxs-lookup"><span data-stu-id="0250a-119">No</span></span>|  
    |<xref:System.ServiceModel.WSHttpBinding>|[<span data-ttu-id="0250a-120">\<wsHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-120">\<wsHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)|<span data-ttu-id="0250a-121">是</span><span class="sxs-lookup"><span data-stu-id="0250a-121">Yes</span></span>|  
    |<xref:System.ServiceModel.WSDualHttpBinding>|[<span data-ttu-id="0250a-122">\<wsDualHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-122">\<wsDualHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsdualhttpbinding.md)|<span data-ttu-id="0250a-123">是</span><span class="sxs-lookup"><span data-stu-id="0250a-123">Yes</span></span>|  
    |<xref:System.ServiceModel.WSFederationHttpBinding>|[<span data-ttu-id="0250a-124">\<wsFederationHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-124">\<wsFederationHttpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/wsfederationhttpbinding.md)|<span data-ttu-id="0250a-125">是</span><span class="sxs-lookup"><span data-stu-id="0250a-125">Yes</span></span>|  
    |<xref:System.ServiceModel.NetTcpBinding>|[<span data-ttu-id="0250a-126">\<netTcpBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-126">\<netTcpBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md)|<span data-ttu-id="0250a-127">否</span><span class="sxs-lookup"><span data-stu-id="0250a-127">No</span></span>|  
    |<xref:System.ServiceModel.NetMsmqBinding>|[<span data-ttu-id="0250a-128">\<netMsmqBinding ></span><span class="sxs-lookup"><span data-stu-id="0250a-128">\<netMsmqBinding></span></span>](../../../../docs/framework/configure-apps/file-schema/wcf/netmsmqbinding.md)|<span data-ttu-id="0250a-129">否</span><span class="sxs-lookup"><span data-stu-id="0250a-129">No</span></span>|  
  
     <span data-ttu-id="0250a-130">下面的代码示例使用配置来指定一个名为绑定`wsHttpBinding_Calculator`使用[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、 消息安全性，和安全会话。</span><span class="sxs-lookup"><span data-stu-id="0250a-130">The following code example uses configuration to specify a binding named `wsHttpBinding_Calculator` that uses the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions.</span></span>  
  
    ```xml  
    <bindings>  
      <WSHttpBinding>  
       <binding name = "wsHttpBinding_Calculator">  
         <security mode="Message">  
           <message clientCredentialType="Windows"/>  
         </security>  
        </binding>  
      </WSHttpBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="0250a-131">下面的代码示例指定[ \<wsHttpBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)、 消息安全性，和安全会话用于保护`secureCalculator`服务。</span><span class="sxs-lookup"><span data-stu-id="0250a-131">The following code example specifies that the [\<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md), message security, and secure sessions are used to secure the `secureCalculator` service.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#1)]
     [!code-vb[c_CreateSecureSession#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#1)]  
  
    > [!NOTE]
    >  <span data-ttu-id="0250a-132">可以关闭安全会话的[ <wsHttpBinding> ](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md)通过设置`establishSecurityContext`属性设为`false`。</span><span class="sxs-lookup"><span data-stu-id="0250a-132">Secure sessions can be turned off for the [<wsHttpBinding>](../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) by setting the `establishSecurityContext` attribute to `false`.</span></span> <span data-ttu-id="0250a-133">对于其他系统提供的绑定，只能通过创建自定义绑定来关闭安全会话。</span><span class="sxs-lookup"><span data-stu-id="0250a-133">For the other system-provided bindings, secure sessions can only be turned off by creating a custom binding.</span></span>  
  
### <a name="to-specify-that-a-service-uses-secure-sessions-by-using-a-custom-binding"></a><span data-ttu-id="0250a-134">通过使用自定义绑定来指定服务使用安全会话</span><span class="sxs-lookup"><span data-stu-id="0250a-134">To specify that a service uses secure sessions by using a custom binding</span></span>  
  
-   <span data-ttu-id="0250a-135">创建一个自定义绑定，该绑定指定由安全会话保护 SOAP 消息。</span><span class="sxs-lookup"><span data-stu-id="0250a-135">Create a custom binding that specifies that SOAP messages are protected by a secure session.</span></span>  
  
     [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="0250a-136">创建自定义绑定，请参阅[如何： 自定义系统提供的绑定](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)。</span><span class="sxs-lookup"><span data-stu-id="0250a-136"> creating a custom binding, see [How to: Customize a System-Provided Binding](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md).</span></span>  
  
     <span data-ttu-id="0250a-137">下面的代码示例使用配置来指定使用安全会话的消息的自定义绑定。</span><span class="sxs-lookup"><span data-stu-id="0250a-137">The following code example uses configuration to specify a custom binding that messages using a secure session.</span></span>  
  
    ```xml  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="customBinding_Calculator">  
          <security authenticationMode="SecureConversation" />  
          <secureConversationBootstrap authenticationMode="SspiNegotiated" />  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    ```  
  
     <span data-ttu-id="0250a-138">下面的代码示例创建一个自定义绑定，该绑定使用 <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> 身份验证模式启动安全会话。</span><span class="sxs-lookup"><span data-stu-id="0250a-138">The following code example creates a custom binding that uses the <xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate> authentication mode to bootstrap a secure session.</span></span>  
  
     [!code-csharp[c_CreateSecureSession#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_createsecuresession/cs/secureservice.cs#2)]
     [!code-vb[c_CreateSecureSession#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_createsecuresession/vb/secureservice.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="0250a-139">请参阅</span><span class="sxs-lookup"><span data-stu-id="0250a-139">See Also</span></span>  
 [<span data-ttu-id="0250a-140">WCF 绑定概述</span><span class="sxs-lookup"><span data-stu-id="0250a-140">WCF Bindings Overview</span></span>](../../../../docs/framework/wcf/bindings-overview.md)
