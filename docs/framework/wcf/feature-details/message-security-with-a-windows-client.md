---
title: "Windows 客户端的消息安全"
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
ms.assetid: 01e7d0b8-10f9-45c3-a4c5-53d44dc61eb8
caps.latest.revision: "13"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: c480706fee27e7023eae5b493b0ca007b4757e97
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="message-security-with-a-windows-client"></a><span data-ttu-id="0cb54-102">Windows 客户端的消息安全</span><span class="sxs-lookup"><span data-stu-id="0cb54-102">Message Security with a Windows Client</span></span>
<span data-ttu-id="0cb54-103">此方案显示受消息安全模式保护的 [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] 客户端和服务器。</span><span class="sxs-lookup"><span data-stu-id="0cb54-103">This scenario shows a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] client and server secured by message security mode.</span></span> <span data-ttu-id="0cb54-104">客户端和服务使用 Windows 凭据进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0cb54-104">The client and service are authenticated using Windows credentials.</span></span>  
  
 <span data-ttu-id="0cb54-105">![消息安全的 Windows 客户端](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span><span class="sxs-lookup"><span data-stu-id="0cb54-105">![Message security with a Windows client](../../../../docs/framework/wcf/feature-details/media/1c8618d4-0005-4022-beb6-32fd087a8c3c.gif "1c8618d4-0005-4022-beb6-32fd087a8c3c")</span></span>  
  
|<span data-ttu-id="0cb54-106">特征</span><span class="sxs-lookup"><span data-stu-id="0cb54-106">Characteristic</span></span>|<span data-ttu-id="0cb54-107">描述</span><span class="sxs-lookup"><span data-stu-id="0cb54-107">Description</span></span>|  
|--------------------|-----------------|  
|<span data-ttu-id="0cb54-108">安全模式</span><span class="sxs-lookup"><span data-stu-id="0cb54-108">Security Mode</span></span>|<span data-ttu-id="0cb54-109">消息</span><span class="sxs-lookup"><span data-stu-id="0cb54-109">Message</span></span>|  
|<span data-ttu-id="0cb54-110">互操作性</span><span class="sxs-lookup"><span data-stu-id="0cb54-110">Interoperability</span></span>|<span data-ttu-id="0cb54-111">仅 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0cb54-111">[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] Only</span></span>|  
|<span data-ttu-id="0cb54-112">身份验证（服务器）</span><span class="sxs-lookup"><span data-stu-id="0cb54-112">Authentication (Server)</span></span>|<span data-ttu-id="0cb54-113">服务器和客户端的相互身份验证</span><span class="sxs-lookup"><span data-stu-id="0cb54-113">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="0cb54-114">身份验证（客户端）</span><span class="sxs-lookup"><span data-stu-id="0cb54-114">Authentication (Client)</span></span>|<span data-ttu-id="0cb54-115">服务器和客户端的相互身份验证</span><span class="sxs-lookup"><span data-stu-id="0cb54-115">Mutual authentication of the server and client</span></span>|  
|<span data-ttu-id="0cb54-116">完整性</span><span class="sxs-lookup"><span data-stu-id="0cb54-116">Integrity</span></span>|<span data-ttu-id="0cb54-117">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="0cb54-117">Yes, using shared security context</span></span>|  
|<span data-ttu-id="0cb54-118">保密性</span><span class="sxs-lookup"><span data-stu-id="0cb54-118">Confidentiality</span></span>|<span data-ttu-id="0cb54-119">是，使用共享安全上下文</span><span class="sxs-lookup"><span data-stu-id="0cb54-119">Yes, using shared security context</span></span>|  
|<span data-ttu-id="0cb54-120">传输</span><span class="sxs-lookup"><span data-stu-id="0cb54-120">Transport</span></span>|<span data-ttu-id="0cb54-121">NET.TCP</span><span class="sxs-lookup"><span data-stu-id="0cb54-121">NET.TCP</span></span>|  
|<span data-ttu-id="0cb54-122">绑定</span><span class="sxs-lookup"><span data-stu-id="0cb54-122">Binding</span></span>|<xref:System.ServiceModel.NetTcpBinding>|  
  
## <a name="service"></a><span data-ttu-id="0cb54-123">服务</span><span class="sxs-lookup"><span data-stu-id="0cb54-123">Service</span></span>  
 <span data-ttu-id="0cb54-124">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="0cb54-124">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0cb54-125">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0cb54-125">Do one of the following:</span></span>  
  
-   <span data-ttu-id="0cb54-126">使用代码（而不使用配置）创建独立服务。</span><span class="sxs-lookup"><span data-stu-id="0cb54-126">Create a stand-alone service using the code with no configuration.</span></span>  
  
-   <span data-ttu-id="0cb54-127">使用提供的配置创建服务，但不定义任何终结点。</span><span class="sxs-lookup"><span data-stu-id="0cb54-127">Create a service using the supplied configuration, but do not define any endpoints.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0cb54-128">代码</span><span class="sxs-lookup"><span data-stu-id="0cb54-128">Code</span></span>  
 <span data-ttu-id="0cb54-129">下面的代码演示如何创建一个使用消息安全来建立 Windows 计算机安全上下文的服务终结点。</span><span class="sxs-lookup"><span data-stu-id="0cb54-129">The following code shows how to create a service endpoint that uses message security to establish a secure context with a Windows machine.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#11)]
 [!code-vb[C_SecurityScenarios#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#11)]  
  
### <a name="configuration"></a><span data-ttu-id="0cb54-130">配置</span><span class="sxs-lookup"><span data-stu-id="0cb54-130">Configuration</span></span>  
 <span data-ttu-id="0cb54-131">下面的配置可代替代码用于设置服务：</span><span class="sxs-lookup"><span data-stu-id="0cb54-131">The following configuration can be used instead of the code to set up the service:</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service behaviorConfiguration=""  
               name="ServiceModel.Calculator">  
        <endpoint address="net.tcp://localhost:8008/Calculator"  
                  binding="netTcpBinding"  
                  bindingConfiguration="Windows"  
                  name="WindowsOverMessage"  
                  contract="ServiceModel.ICalculator" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="Windows">  
          <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client />  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="client"></a><span data-ttu-id="0cb54-132">客户端</span><span class="sxs-lookup"><span data-stu-id="0cb54-132">Client</span></span>  
 <span data-ttu-id="0cb54-133">下面的代码和配置应独立运行。</span><span class="sxs-lookup"><span data-stu-id="0cb54-133">The following code and configuration are meant to run independently.</span></span> <span data-ttu-id="0cb54-134">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="0cb54-134">Do one of the following:</span></span>  
  
-   <span data-ttu-id="0cb54-135">使用代码（和客户端代码）创建独立客户端。</span><span class="sxs-lookup"><span data-stu-id="0cb54-135">Create a stand-alone client using the code (and client code).</span></span>  
  
-   <span data-ttu-id="0cb54-136">创建不定义任何终结点地址的客户端。</span><span class="sxs-lookup"><span data-stu-id="0cb54-136">Create a client that does not define any endpoint addresses.</span></span> <span data-ttu-id="0cb54-137">而使用将配置名称作为参数的客户端构造函数。</span><span class="sxs-lookup"><span data-stu-id="0cb54-137">Instead, use the client constructor that takes the configuration name as an argument.</span></span> <span data-ttu-id="0cb54-138">例如：</span><span class="sxs-lookup"><span data-stu-id="0cb54-138">For example:</span></span>  
  
     [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]  
  
### <a name="code"></a><span data-ttu-id="0cb54-139">代码</span><span class="sxs-lookup"><span data-stu-id="0cb54-139">Code</span></span>  
 <span data-ttu-id="0cb54-140">下面的代码创建客户端。</span><span class="sxs-lookup"><span data-stu-id="0cb54-140">The following code creates a client.</span></span> <span data-ttu-id="0cb54-141">绑定设置为 Message 安全模式，客户端凭据类型设置为 `Windows`。</span><span class="sxs-lookup"><span data-stu-id="0cb54-141">The binding is to Message mode security, and the client credential type is set to `Windows`.</span></span>  
  
 [!code-csharp[C_SecurityScenarios#18](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#18)]
 [!code-vb[C_SecurityScenarios#18](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#18)]  
  
### <a name="configuration"></a><span data-ttu-id="0cb54-142">配置</span><span class="sxs-lookup"><span data-stu-id="0cb54-142">Configuration</span></span>  
 <span data-ttu-id="0cb54-143">下面的配置用于设置客户端属性。</span><span class="sxs-lookup"><span data-stu-id="0cb54-143">The following configuration is used to set the client properties.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<configuration>  
  <system.serviceModel>  
    <bindings>  
      <netTcpBinding>  
        <binding name="NetTcpBinding_ICalculator" >  
         <security mode="Message">  
            <message clientCredentialType="Windows" />  
          </security>  
        </binding>  
      </netTcpBinding>  
    </bindings>  
    <client>  
      <endpoint address="net.tcp://machineName:8008/Calculator"   
                binding="netTcpBinding"  
                bindingConfiguration="NetTcpBinding_ICalculator"  
                contract="ICalculator"  
                name="NetTcpBinding_ICalculator">          
      </endpoint>  
    </client>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="0cb54-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="0cb54-144">See Also</span></span>  
 [<span data-ttu-id="0cb54-145">安全性概述</span><span class="sxs-lookup"><span data-stu-id="0cb54-145">Security Overview</span></span>](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [<span data-ttu-id="0cb54-146">Windows Server App Fabric 的安全模型</span><span class="sxs-lookup"><span data-stu-id="0cb54-146">Security Model for Windows Server App Fabric</span></span>](http://go.microsoft.com/fwlink/?LinkID=201279&clcid=0x409)
