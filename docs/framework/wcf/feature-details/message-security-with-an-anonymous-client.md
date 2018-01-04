---
title: "匿名客户端的消息安全"
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
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
caps.latest.revision: "15"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: e8c10c9d4838a2b6c9d3a021d22d2dfd4dc865da
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-an-anonymous-client"></a><span data-ttu-id="bd80c-102">匿名客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="bd80c-102">Message Security with an Anonymous Client</span></span>
<span data-ttu-id="bd80c-103">下面的方案演示通过 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 消息安全进行保护的客户端和服务。</span><span class="sxs-lookup"><span data-stu-id="bd80c-103">The following scenario shows a client and service secured by [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] message security.</span></span> <span data-ttu-id="bd80c-104">设计目标是使用消息安全而非传输安全，以便将来可支持更加丰富的基于声明的模型。</span><span class="sxs-lookup"><span data-stu-id="bd80c-104">A design goal is to use message security rather than transport security, so that in the future it can support a richer claims-based model.</span></span> [!INCLUDE[crabout](../../../../includes/crabout-md.md)]<span data-ttu-id="bd80c-105">使用丰富的声明进行授权，请参阅[管理声明和使用标识模型的授权](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md)。</span><span class="sxs-lookup"><span data-stu-id="bd80c-105"> using rich claims for authorization, see [Managing Claims and Authorization with the Identity Model](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).</span></span>  
  
 <span data-ttu-id="bd80c-106">有关示例应用程序，请参阅[匿名消息安全](../../../../docs/framework/wcf/samples/message-security-anonymous.md)。</span><span class="sxs-lookup"><span data-stu-id="bd80c-106">For a sample application, see [Message Security Anonymous](../../../../docs/framework/wcf/samples/message-security-anonymous.md).</span></span>  
  
 <span data-ttu-id="bd80c-107">![消息与匿名客户端的安全](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span><span class="sxs-lookup"><span data-stu-id="bd80c-107">![Message security with an anynymous client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")</span></span>  
  
|<span data-ttu-id="bd80c-108">特征</span><span class="sxs-lookup"><span data-stu-id="bd80c-108">Characteristic</span></span>|<span data-ttu-id="bd80c-109">描述</span><span class="sxs-lookup"><span data-stu-id="bd80c-109">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="bd80c-110">安全模式</span><span class="sxs-lookup"><span data-stu-id="bd80c-110">Security Mode</span></span>|<span data-ttu-id="bd80c-111">消息</span><span class="sxs-lookup"><span data-stu-id="bd80c-111">Message</span></span>|  
|<span data-ttu-id="bd80c-112">互操作性</span><span class="sxs-lookup"><span data-stu-id="bd80c-112">Interoperability</span></span>|<span data-ttu-id="bd80c-113">仅 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd80c-113">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] only</span></span>|  
|<span data-ttu-id="bd80c-114">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="bd80c-114">Authentication (Server)</span></span>|<span data-ttu-id="bd80c-115">初始协商要求服务器身份验证，而不是客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="bd80c-115">Initial negotiation requires server authentication, but not client authentication</span></span>|  
|<span data-ttu-id="bd80c-116">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="bd80c-116">Authentication (Client)</span></span>|<span data-ttu-id="bd80c-117">无</span><span class="sxs-lookup"><span data-stu-id="bd80c-117">None</span></span>|  
|<span data-ttu-id="bd80c-118">完整性</span><span class="sxs-lookup"><span data-stu-id="bd80c-118">Integrity</span></span>|<span data-ttu-id="bd80c-119">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="bd80c-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="bd80c-120">保密性</span><span class="sxs-lookup"><span data-stu-id="bd80c-120">Confidentiality</span></span>|<span data-ttu-id="bd80c-121">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="bd80c-121">Yes, using shared security context</span></span>|  
|<span data-ttu-id="bd80c-122">传输</span><span class="sxs-lookup"><span data-stu-id="bd80c-122">Transport</span></span>|<span data-ttu-id="bd80c-123">HTTP</span><span class="sxs-lookup"><span data-stu-id="bd80c-123">HTTP</span></span>|  
  
## <a name="service"></a><span data-ttu-id="bd80c-124">服务</span><span class="sxs-lookup"><span data-stu-id="bd80c-124">Service</span></span>  
 <span data-ttu-id="bd80c-125">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="bd80c-125">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="bd80c-126">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bd80c-126">Do one of the following:</span></span>  
  
-   <span data-ttu-id="bd80c-127">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="bd80c-127">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="bd80c-128">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="bd80c-128">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="bd80c-129">代码</span><span class="sxs-lookup"><span data-stu-id="bd80c-129">Code</span></span>  
 <span data-ttu-id="bd80c-130">下面的代码演示如何创建使用消息安全的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="bd80c-130">The following code shows how to create a service endpoint that uses message security.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
 [!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]  
  
### <a name="configuration"></a><span data-ttu-id="bd80c-131">配置</span><span class="sxs-lookup"><span data-stu-id="bd80c-131">Configuration</span></span>  
 <span data-ttu-id="bd80c-132">以下配置可代替代码使用。</span><span class="sxs-lookup"><span data-stu-id="bd80c-132">The following configuration can be used instead of the code.</span></span> <span data-ttu-id="bd80c-133">服务行为元素用于指定用来向客户端验证服务身份的证书。</span><span class="sxs-lookup"><span data-stu-id="bd80c-133">The service behavior element is used to specify a certificate that is used to authenticate the service to the client.</span></span> <span data-ttu-id="bd80c-134">服务元素必须使用 `behaviorConfiguration` 属性指定行为。</span><span class="sxs-lookup"><span data-stu-id="bd80c-134">The service element must specify the behavior using the `behaviorConfiguration` attribute.</span></span> <span data-ttu-id="bd80c-135">绑定元素指定客户端凭据类型为 `None`，这将允许匿名客户端使用该服务。</span><span class="sxs-lookup"><span data-stu-id="bd80c-135">The binding element specifies that the client credential type is `None`, allowing anonymous clients to use the service.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="ServiceCredentialsBehavior">  
          <serviceCredentials>  
            <serviceCertificate findValue="contoso.com"   
                                storeLocation="LocalMachine"  
                                storeName="My" />  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service behaviorConfiguration="ServiceCredentialsBehavior"   
               name="ServiceModel.Calculator">  
        <endpoint address="http://localhost/Calculator"   
                  binding="wsHttpBinding"  
                  bindingConfiguration="WSHttpBinding_ICalculator"   
                  name="CalculatorService"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="bd80c-136">客户端</span><span class="sxs-lookup"><span data-stu-id="bd80c-136">Client</span></span>  
 <span data-ttu-id="bd80c-137">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="bd80c-137">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="bd80c-138">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bd80c-138">Do one of the following:</span></span>  
  
-   <span data-ttu-id="bd80c-139">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="bd80c-139">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="bd80c-140">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="bd80c-140">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="bd80c-141">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="bd80c-141">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="bd80c-142">例如：</span><span class="sxs-lookup"><span data-stu-id="bd80c-142">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="bd80c-143">代码</span><span class="sxs-lookup"><span data-stu-id="bd80c-143">Code</span></span>  
 <span data-ttu-id="bd80c-144">下面的代码创建客户端的一个实例。</span><span class="sxs-lookup"><span data-stu-id="bd80c-144">The following code creates an instance of the client.</span></span> <span data-ttu-id="bd80c-145">绑定使用消息模式安全，客户端凭据类型设置为 None。</span><span class="sxs-lookup"><span data-stu-id="bd80c-145">The binding uses message mode security, and the client credential type is set to none.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
 [!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]  
  
### <a name="configuration"></a><span data-ttu-id="bd80c-146">配置</span><span class="sxs-lookup"><span data-stu-id="bd80c-146">Configuration</span></span>  
 <span data-ttu-id="bd80c-147">下面的代码将配置客户端。</span><span class="sxs-lookup"><span data-stu-id="bd80c-147">The following code configures the client.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <wsHttpBinding>  
        <binding name="WSHttpBinding_ICalculator" >  
          <security mode="Message">  
            <message clientCredentialType="None" />  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
    <client>  
      <endpoint address="http://machineName/Calculator"  
        binding="wsHttpBinding"  
        bindingConfiguration="WSHttpBinding_ICalculator"   
        contract="ICalculator"  
        name="WSHttpBinding_ICalculator">  
        <identity>  
          <dns value="contoso.com" />  
        </identity>  
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="bd80c-148">请参阅</span><span class="sxs-lookup"><span data-stu-id="bd80c-148">See Also</span></span>  
 [<span data-ttu-id="bd80c-149">安全性概述</span><span class="sxs-lookup"><span data-stu-id="bd80c-149">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="bd80c-150">分布式应用程序安全</span><span class="sxs-lookup"><span data-stu-id="bd80c-150">Distributed Application Security</span></span>](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)  
 [<span data-ttu-id="bd80c-151">匿名消息安全</span><span class="sxs-lookup"><span data-stu-id="bd80c-151">Message Security Anonymous</span></span>](../../../../docs/framework/wcf/samples/message-security-anonymous.md)  
 [<span data-ttu-id="bd80c-152">服务标识和身份验证</span><span class="sxs-lookup"><span data-stu-id="bd80c-152">Service Identity and Authentication</span></span>](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="bd80c-153">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="bd80c-153">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
