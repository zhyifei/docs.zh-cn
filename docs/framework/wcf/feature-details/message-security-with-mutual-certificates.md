---
title: "使用相互证书的消息安全"
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
ms.assetid: 99d7a528-7ae4-4d39-a0f9-3066ea237de0
caps.latest.revision: "18"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 3d5e598fea118eb340b965d605f5fdeb9c479a4b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="message-security-with-mutual-certificates"></a><span data-ttu-id="fb6bc-102">使用相互证书的消息安全</span><span class="sxs-lookup"><span data-stu-id="fb6bc-102">Message Security with Mutual Certificates</span></span>
<span data-ttu-id="fb6bc-103">下面的方案演示使用消息安全模式保护的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 服务和客户端。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-103">The following scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] service and client secured using message security mode.</span></span> <span data-ttu-id="fb6bc-104">使用证书对客户端和服务进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-104">The client and the service are authenticated with certificates.</span></span>  
  
 <span data-ttu-id="fb6bc-105">本方案是可互操作的，因为它使用具有 X.509 证书令牌配置文件的 WS-Security。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-105">This scenario is interoperable because it uses WS-Security with the X.509 certificate token profile.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="fb6bc-106">本方案不对服务证书执行协商。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-106">This scenario does not perform negotiation of the service certificate.</span></span> <span data-ttu-id="fb6bc-107">在进行任何通信之前，必须先向客户端提供服务证书。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-107">The service certificate must be provided to the client in advance of any communication.</span></span> <span data-ttu-id="fb6bc-108">服务器证书可以随应用程序一起分发，也可以通过带外通信来提供。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-108">The server certificate can be distributed with the application or provided in an out-of-band communication.</span></span>  
  
 <span data-ttu-id="fb6bc-109">![消息安全使用相互证书](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span><span class="sxs-lookup"><span data-stu-id="fb6bc-109">![Message security with mutual certificates](../../../../docs/framework/wcf/feature-details/media/f4157312-b17c-416c-a5ee-fa7b54db211b.gif "f4157312-b17c-416c-a5ee-fa7b54db211b")</span></span>  
  
|<span data-ttu-id="fb6bc-110">特征</span><span class="sxs-lookup"><span data-stu-id="fb6bc-110">Characteristic</span></span>|<span data-ttu-id="fb6bc-111">描述</span><span class="sxs-lookup"><span data-stu-id="fb6bc-111">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="fb6bc-112">安全模式</span><span class="sxs-lookup"><span data-stu-id="fb6bc-112">Security Mode</span></span>|<span data-ttu-id="fb6bc-113">消息</span><span class="sxs-lookup"><span data-stu-id="fb6bc-113">Message</span></span>|  
|<span data-ttu-id="fb6bc-114">互操作性</span><span class="sxs-lookup"><span data-stu-id="fb6bc-114">Interoperability</span></span>|<span data-ttu-id="fb6bc-115">是，使用 WS-Security 和 X.509 证书令牌配置文件兼容的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-115">Yes, with WS-Security and X.509 certificate token profile compatible clients and services.</span></span>|  
|<span data-ttu-id="fb6bc-116">身份验证</span><span class="sxs-lookup"><span data-stu-id="fb6bc-116">Authentication</span></span>|<span data-ttu-id="fb6bc-117">服务器和客户端的相互身份验证。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-117">Mutual authentication of the server and client.</span></span>|  
|<span data-ttu-id="fb6bc-118">完整性</span><span class="sxs-lookup"><span data-stu-id="fb6bc-118">Integrity</span></span>|<span data-ttu-id="fb6bc-119">是</span><span class="sxs-lookup"><span data-stu-id="fb6bc-119">Yes</span></span>|  
|<span data-ttu-id="fb6bc-120">保密性</span><span class="sxs-lookup"><span data-stu-id="fb6bc-120">Confidentiality</span></span>|<span data-ttu-id="fb6bc-121">是</span><span class="sxs-lookup"><span data-stu-id="fb6bc-121">Yes</span></span>|  
|<span data-ttu-id="fb6bc-122">传输</span><span class="sxs-lookup"><span data-stu-id="fb6bc-122">Transport</span></span>|<span data-ttu-id="fb6bc-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="fb6bc-123">HTTP</span></span>|  
|<span data-ttu-id="fb6bc-124">绑定</span><span class="sxs-lookup"><span data-stu-id="fb6bc-124">Binding</span></span>|<xref:System.ServiceModel.WSHttpBinding>|  
  
## <a name="service"></a><span data-ttu-id="fb6bc-125">服务</span><span class="sxs-lookup"><span data-stu-id="fb6bc-125">Service</span></span>  
 <span data-ttu-id="fb6bc-126">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-126">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fb6bc-127">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fb6bc-127">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fb6bc-128">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-128">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="fb6bc-129">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-129">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="fb6bc-130">代码</span><span class="sxs-lookup"><span data-stu-id="fb6bc-130">Code</span></span>  
 <span data-ttu-id="fb6bc-131">下面的代码演示如何创建使用消息安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-131">The following code shows creates a service endpoint that uses message security.</span></span> <span data-ttu-id="fb6bc-132">服务请求一个证书来使自己通过身份验证。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-132">The service requires a certificate to authenticate itself.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#13)]
 [!code-vb[C_SecurityScenarios#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#13)]  
  
### <a name="configuration"></a><span data-ttu-id="fb6bc-133">配置</span><span class="sxs-lookup"><span data-stu-id="fb6bc-133">Configuration</span></span>  
 <span data-ttu-id="fb6bc-134">可以使用下面的配置，而不使用代码来创建同样的服务。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-134">The following configuration can be used instead of the code to create the same service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="serviceCredentialBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="Contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My"   
                                x509FindType="FindBySubjectName" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="serviceCredentialBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="InteropCertificateBinding"  
                  name="WSHttpBinding_ICalculator"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="InteropCertificateBinding">  
          <security mode="Message">  
            <message clientCredentialType="Certificate"  
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="fb6bc-135">客户端</span><span class="sxs-lookup"><span data-stu-id="fb6bc-135">Client</span></span>  
 <span data-ttu-id="fb6bc-136">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-136">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="fb6bc-137">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="fb6bc-137">Do one of the following:</span></span>  
  
-   <span data-ttu-id="fb6bc-138">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-138">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="fb6bc-139">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-139">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="fb6bc-140">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-140">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="fb6bc-141">例如：</span><span class="sxs-lookup"><span data-stu-id="fb6bc-141">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="fb6bc-142">代码</span><span class="sxs-lookup"><span data-stu-id="fb6bc-142">Code</span></span>  
 <span data-ttu-id="fb6bc-143">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-143">The following code creates the client.</span></span> <span data-ttu-id="fb6bc-144">安全模式设置为“消息”，客户端凭据类型设置为“证书”。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-144">The security mode is set to Message, and the client credential type is set to Certificate.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#20](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#20)]
 [!code-vb[C_SecurityScenarios#20](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#20)]  
  
### <a name="configuration"></a><span data-ttu-id="fb6bc-145">配置</span><span class="sxs-lookup"><span data-stu-id="fb6bc-145">Configuration</span></span>  
 <span data-ttu-id="fb6bc-146">下面配置客户端。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-146">The following configures the client.</span></span> <span data-ttu-id="fb6bc-147">必须使用指定的客户端证书[ \<t i a l >](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-147">A client certificate must be specified using the [\<clientCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/clientcertificate-of-clientcredentials-element.md).</span></span> <span data-ttu-id="fb6bc-148">此外，使用指定的服务证书[ \<defaultCertificate >](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md)。</span><span class="sxs-lookup"><span data-stu-id="fb6bc-148">Also, the service certificate is specified using the [\<defaultCertificate>](../../../../docs/framework/configure-apps/file-schema/wcf/defaultcertificate-element.md).</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <endpointBehaviors>  
        <behavior name="ClientCredentialsBehavior">  
          <clientCredentials>  
            <clientCertificate findValue="Cohowinery.com"   
                 storeLocation="CurrentUser"  
                 storeName="My"  
                 x509FindType="FindBySubjectName" />  
            <serviceCertificate>  
              <defaultCertificate findValue="Contoso.com"   
                                  storeLocation="CurrentUser"  
                                  storeName="TrustedPeople"  
                                  x509FindType="FindBySubjectName" />  
            </serviceCertificate>  
          </clientCredentials>  
        </behavior>  
      </endpointBehaviors>  
    </behaviors>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="Certificate"   
                     negotiateServiceCredential="false"  
                     establishSecurityContext="false" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"   
                behaviorConfiguration="ClientCredentialsBehavior"  
                binding="wsHttpBinding"   
                bindingConfiguration="WSHttpBinding_ICalculator"  
                contract="ICalculator"  
                name="WSHttpBinding_ICalculator">  
        <identity>  
          <certificate encodedValue="Encoded_Value_Not_Shown" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="fb6bc-149">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb6bc-149">See Also</span></span>  
 [<span data-ttu-id="fb6bc-150">安全性概述</span><span class="sxs-lookup"><span data-stu-id="fb6bc-150">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="fb6bc-151">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="fb6bc-151">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)  
 [<span data-ttu-id="fb6bc-152">如何： 创建和安装临时证书在 WCF 中实现传输安全在开发过程</span><span class="sxs-lookup"><span data-stu-id="fb6bc-152">How to: Create and Install Temporary Certificates in WCF for Transport Security During Development</span></span>](http://go.microsoft.com/fwlink/?LinkId=244264)
